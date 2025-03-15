public void Add(View v){
        EditText et1 =(EditText)findViewById(R.id.editTextNumber);
        EditText et2 =(EditText)findViewById(R.id.editTextNumber2);
        EditText et3 =(EditText)findViewById(R.id.editTextNumber3);

        int n1 = Integer.parseInt(et1.getText().toString());
        int n2 = Integer.parseInt(et2.getText().toString());
        int result = n1+n2;

        et3.setText("Total Value" + result);
    }
    public void Subtract(View v){
        EditText et1 =(EditText)findViewById(R.id.editTextNumber);
        EditText et2 =(EditText)findViewById(R.id.editTextNumber2);
        EditText et3 =(EditText)findViewById(R.id.editTextNumber3);

        int n1 = Integer.parseInt(et1.getText().toString());
        int n2 = Integer.parseInt(et2.getText().toString());
        int result = n1-n2;

        et3.setText("Subtract Value" + result);
    }
    public void Multiply(View v){
        EditText et1 =(EditText)findViewById(R.id.editTextNumber);
        EditText et2 =(EditText)findViewById(R.id.editTextNumber2);
        EditText et3 =(EditText)findViewById(R.id.editTextNumber3);

        int n1 = Integer.parseInt(et1.getText().toString());
        int n2 = Integer.parseInt(et2.getText().toString());
        int result = n1*n2;

        et3.setText("Multiply Value" + result);
    }
    public void Divide(View v){
        EditText et1 =(EditText)findViewById(R.id.editTextNumber);
        EditText et2 =(EditText)findViewById(R.id.editTextNumber2);
        EditText et3 =(EditText)findViewById(R.id.editTextNumber3);

        int n1 = Integer.parseInt(et1.getText().toString());
        int n2 = Integer.parseInt(et2.getText().toString());
        int result = n1/n2;

        et3.setText("Divide Value" + result);
    }
}





video 
package com.example.video;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.MediaController;
import android.widget.VideoView;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    MediaController control;
    VideoView videoView;
    @SuppressLint("MissingInflatedId")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        videoView=findViewById(R.id.videoView);
        control=new MediaController(this);
        videoView.setVideoPath("android.resource://"+ getPackageName()+"/"+R.raw.video);
    }
}


audio 
package com.example.musicplayer;

import android.media.MediaPlayer;
import android.os.Bundle;
import android.view.View;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {
    MediaPlayer mysound;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);
        mysound=MediaPlayer.create(MainActivity.this,R.raw.music);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }
    public void playit(View v){
        mysound.start();
    }
}