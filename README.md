# cse405

/////////////////Router-1/////////////////////

interface fa0/0
ip address 192.168.10.254  255.255.255.0
no shut
do wr
exit

interface se2/0
ip address 192.168.60.1  255.255.255.0
clock rate 64000
no shut
do wr
exit

interface se3/0
ip address 192.168.40.1  255.255.255.0
clock rate 64000
no shut
do wr
exit
//////////////////////////////////////////////

en
show ip route

//////////////////////////////////////////////

router ospf 1
network 192.168.10.0 0.0.0.255 area 1
network 192.168.40.0 0.0.0.255 area 1
network 192.168.60.0 0.0.0.255 area 1
exit




/////////////////Router-2/////////////////////

interface fa0/0
ip address 192.168.20.254  255.255.255.0
no shut
do wr
exit

interface se2/0
ip address 192.168.40.2  255.255.255.0
no shut
do wr
exit

interface se3/0
ip address 192.168.50.1  255.255.255.0
clock rate 64000
no shut
do wr
exit

//////////////////////////////////////////////

en
show ip route

//////////////////////////////////////////////

router ospf 2
network 192.168.20.0 0.0.0.255 area 1
network 192.168.40.0 0.0.0.255 area 1
network 192.168.50.0 0.0.0.255 area 1
exit


/////////////////Router-3/////////////////////

interface fa0/0
ip address 192.168.30.254  255.255.255.0
no shut
do wr
exit

interface se2/0
ip address 192.168.60.2  255.255.255.0
no shut
do wr
exit

interface se3/0
ip address 192.168.50.2  255.255.255.0
no shut
do wr
exit

//////////////////////////////////////////////

en
show ip route

//////////////////////////////////////////////

router ospf 3
network 192.168.30.0 0.0.0.255 area 1
network 192.168.50.0 0.0.0.255 area 1
network 192.168.60.0 0.0.0.255 area 1
exit
