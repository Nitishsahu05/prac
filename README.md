prac 1 - 
connection-
router ospf 1, in every router -

network ip 0.0.0.3 or 0.0.0.255 area 0





md5 ospf authentication-((Open Shortest Path First))

to go to config mode -
confit (then press enter 2 times)

router ospf 1 
area 0 authentication message-digest(to turn on message digest protocol on )
ex(to exit from router)

interface s0/0/0  ( go to s0/0/0)
ip ospf message digest key 1 md5 rohit(username and password set as md5(username) and rohit(password)

show ip ospf interface (to show if it is done or not )






ntp(network time protocol)
first go to any of the servers and in ntp update the calendar ) 
router 0-
ntp server 192.168.1.3
ntp update-calendar
ntp authenticate
ntp trusted-key 1
ntp authentication-key 1 md5 rohit   
ex
ex
en

show clock ( to show the current time and date)






syslog server -
in config-
service timestamps log datetime msec (kab user aaya or kitne time ruka )
logging host 192.168.1.5
ex

(can see in the server-syslog)






ssh (secure shell)
ip domain-name rohit.com
username rohit privilege 15 secret ro
line vty 0 4 ( connect devices from 0-5 total 5)
login local 
transport input ssh 
exit 
crypto key zeroize rsa
crypto key generate rsa
1024
show ip ssh 
exit
show ip ssh
config(come in config)
ip ssh time-out 90
ip ssh authentication-retries 2
ip ssh version 2
exit
show ip ssh 

now go to pc-c -> command prompt 
telnet 192.168.3.3 (it will show connecton timed out because it is secure shell , there is an password in it)
ssh -l rohit 192.168.3.1
pass:ro
r3

to access version 2 or connect router 3 to router 2 
ssh -v 2 -l rohit 10.2.2.1
pass: ro



Prac 3
config me jao
access-list 100 permit tcp 172.22.34.64 0.0.0.31 host 172.22.34.62
access-list 100 permit tcp 172.22.34.64 0.0.0.31 host 172.22.34.62 ?
access-list 100 permit tcp 172.22.34.64 0.0.0.31 host 172.22.34.62 eq ?
access-list 100 permit tcp 172.22.34.64 0.0.0.31 host 172.22.34.62 eq ftp 
access-list 100 permit icmp 172.22.34.64 0.0.0.31 host 172.22.34.62
interface g0/0
ip access-group 100 100 in

Go to PC 1
open command prompt
ping 172.22.34.62
ftp 172.22.34.62
username - cisco
password - cisco











