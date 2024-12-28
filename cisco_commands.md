## VLAN Configuration
### Access switches 

```
hostname <hostname>

```

#### At all L2 switches:
```

en
conf t


vlan 99
name BlackHole
int range gig0/1-2
switchport mode access
switchport access vlan 99
shutdown
```

#### L2 switch1:
```

vlan 10
name Finance
exit

int range fa0/1-24
switchport mode access
switchport access vlan 10
```

#### At L2 switch2:
```

vlan 20
name HR
exit

int range fa0/1-24
switchport mode access
switchport access vlan 20
```

#### At L2 switch3:
```

vlan 30
name Admin
exit

int range fa0/1-24
switchport mode access
switchport access vlan 30
```

#### At L2 switch4:
```

vlan 40
name Procurement
exit

int range fa0/1-24
switchport mode access
switchport access vlan 40
```

#### At L2 switch5:
```

vlan 50
name CivilEngineering
exit

int range fa0/1-24
switchport mode access
switchport access vlan 50
```

#### At L2 switch6:
```


vlan 60
name MechanicalEngineering
exit

int range fa0/1-24
switchport mode access
switchport access vlan 60
```

#### At L2 switch7:
```

vlan 70
name ElectricalEngineering
exit

int range fa0/1-24
switchport mode access
switchport access vlan 70
```

#### At L2 switch8:
```

vlan 80
name LabBuilding2
exit

int range fa0/1-24
switchport mode access
switchport access vlan 80
```

#### At L2 switch9:
```

vlan 90
name ComputerScience
exit

int range fa0/1-24
switchport mode access
switchport access vlan 90
```

#### At L2 switch10:
```


vlan 100
name Physics
exit

int range fa0/1-24
switchport mode access
switchport access vlan 100
```

#### At L2 switch11:
```


vlan 110
name Mathematics
exit

int range fa0/1-24
switchport mode access
switchport access vlan 110
```

#### At L2 switch12:
```


vlan 120
name LabBuilding3
exit

int range fa0/1-24
switchport mode access
switchport access vlan 120
```

#### At L2 switch13:
```


vlan 130
name ITDepartment
exit

int range fa0/1-24
switchport mode access
switchport access vlan 130
```

#### At L2 switch14:
```


vlan 140
name DataCenter
exit

int range fa0/1-24
switchport mode access
switchport access vlan 140
```

#### At L2 switch15:
```


vlan 150
name MaleHostel
exit

int range fa0/1-24
switchport mode access
switchport access vlan 150
```

#### At L2 switch16:
```


vlan 160
name FemaleHostel
exit

int range fa0/1-24
switchport mode access
switchport access vlan 160
```

### Distribution switches

#### At all L3 switches:
```
en
conf t
int range gig1/0/3-13
switchport mode access

vlan 10
name Finance
vlan 20
name HR
vlan 30
name Admin
vlan 40
name Procurement
vlan 50
name CivilEngineering
vlan 60
name MechanicalEngineering
vlan 70
name ElectricalEngineering
vlan 80
name LabBuilding2
vlan 90
name ComputerScience
vlan 100
name Physics
vlan 110
name Mathematics
vlan 120
name LabBuilding3
vlan 130
name ITDepartment
vlan 140
name DataCenter
vlan 150
name MaleHostel
vlan 160
name FemaleHostel
exit

int range gig1/0/1-2
no switchport

do wr
```

#### L3 switch1:
```
int gig1/0/3
switchport access vlan 10

int gig1/0/4
switchport access vlan 20

int gig1/0/5
switchport access vlan 30

int gig1/0/6
switchport access vlan 40

int gig1/0/7
switchport access vlan 50

int gig1/0/8
switchport access vlan 60

int gig1/0/9
switchport access vlan 70

int gig1/0/10
switchport access vlan 80

int gig1/0/11
switchport access vlan 90

int gig1/0/12
switchport access vlan 100

int gig1/0/13
switchport access vlan 110
```

#### L3 switch2:
```
int gig1/0/3
switchport access vlan 10

int gig1/0/4
switchport access vlan 20

int gig1/0/5
switchport access vlan 30

int gig1/0/6
switchport access vlan 40

int gig1/0/7
switchport access vlan 50

int gig1/0/8
switchport access vlan 60

int gig1/0/9
switchport access vlan 120

int gig1/0/10
switchport access vlan 130

int gig1/0/11
switchport access vlan 140

int gig1/0/12
switchport access vlan 150

int gig1/0/13
switchport access vlan 160
```

#### L3 switch3:
```
int gig1/0/3
switchport access vlan 70

int gig1/0/4
switchport access vlan 80

int gig1/0/5
switchport access vlan 90

int gig1/0/6
switchport access vlan 100

int gig1/0/7
switchport access vlan 110

int gig1/0/8
switchport access vlan 120

int gig1/0/9
switchport access vlan 130

int gig1/0/10
switchport access vlan 140

int gig1/0/11
switchport access vlan 150

int gig1/0/12
switchport access vlan 160
```


## IP Addressing
### Assign IP addresses to L3 switch and router interfaces
#### At L3 switch1:
```
int gig1/0/1
ip address 172.16.4.1 255.255.255.252
no shutdown
exit
int gig1/0/2
ip address  172.16.4.5 255.255.255.252
no shutdown
exit
do wr
```
#### At L3 switch2:
```
int gig1/0/1
ip address 172.16.4.9 255.255.255.252
no shutdown
exit
int gig1/0/2
ip address 172.16.4.13 255.255.255.252
no shutdown
exit
```
#### At L3 switch3:
```
int gig1/0/1
ip address 172.16.4.17 255.255.255.252
no shutdown
exit
int gig1/0/2
ip address 172.16.4.21 255.255.255.252
no shutdown
int gig1/0/13
ip address 172.16.4.26 255.255.255.252
no shutdown
exit
```
#### At Router1:
```
int gig0/0
ip address 172.16.4.2 255.255.255.252
no shutdown
exit
int gig0/1
ip address 172.16.4.10 255.255.255.252
no shutdown
exit
int gig0/2
ip address 172.16.4.18 255.255.255.252
no shutdown
exit
do wr
```
#### At Router2:
```
int gig0/0
ip address 172.16.4.6 255.255.255.252
no shutdown
exit
int gig0/1
ip address 172.16.4.14 255.255.255.252
no shutdown
exit
int gig0/2
ip address 172.16.4.22 255.255.255.252
no shutdown
exit
do wr
```

#### Border Router
```
int gig0/0
ip address 172.16.4.25 255.255.255.252
no shutdown
int se0/3/0
ip address 172.16.4.29 255.255.255.252
no shutdown
exit
```

#### Main Campus Router
```
int se0/2/1
ip address 172.16.4.30 255.255.255.252
no shutdown
int se0/2/0
ip address 105.12.32.16 255.255.255.252
no shutdown

```

#### Server Configuration for IP Addressing at Main Campus
Set static web and email server IP addresses 105.12.32.22/29 and 105.12.32.23/29 respectively
Gateway: 105.12.32.21
Network: 105.12.32.20/29
Set SMIS and ERP server IP addresses 172.16.255.2 and 172.16.255.3 respectively
Gateway: 172.16.255.1
Network: 172.16.255.0/24

#### Main Campus Switch: VLAN Configuration
```
en
conf t
vlan 10
name Internal
exit
vlan 20
name Global
exit
```
#### Main Campus Router
```
en
conf t
int gig0/0.10
encapsulation dot1q 10
ip address 172.16.255.1 255.255.255.0
exit
int gig0/0.20
encapsulation dot1q 20
ip address 105.12.32.25 255.255.255.248
exit
```



## OSPF Configuration
### At L3 switch1:
```
ip routing
router ospf 10
network 172.16.0.0 0.0.0.15 area 0
network 172.16.0.16 0.0.0.15 area 0
network 172.16.0.32 0.0.0.15 area 0
network 172.16.0.48 0.0.0.15 area 0
network 172.16.0.64 0.0.0.31 area 0
network 172.16.0.96 0.0.0.31 area 0
network 172.16.0.128 0.0.0.31 area 0
network 172.16.1.0 0.0.0.127 area 0
network 172.16.0.160 0.0.0.31 area 0
network 172.16.0.192 0.0.0.31 area 0
network 172.16.0.224 0.0.0.31 area 0
network 172.16.4.0 0.0.0.3 area 0
network 172.16.4.4 0.0.0.3 area 0
do wr
```
### At L3 switch2:
```
ip routing
router ospf 10
router-id 2.2.2.2
network 172.16.0.0 0.0.0.15 area 0
network 172.16.0.16 0.0.0.15 area 0
network 172.16.0.32 0.0.0.15 area 0
network 172.16.0.48 0.0.0.15 area 0
network 172.16.0.64 0.0.0.31 area 0
network 172.16.0.96 0.0.0.31 area 0
network 172.16.1.128 0.0.0.127 area 0
network 172.16.2.0 0.0.0.63 area 0
network 172.16.2.64 0.0.0.15 area 0
network 172.16.3.0 0.0.0.127 area 0
network 172.16.3.128 0.0.0.127 area 0
network 172.16.4.8 0.0.0.3 area 0
network 172.16.4.12 0.0.0.3 area 0
do wr
```
### At L3 switch3:
```
ip routing
router ospf 10
router-id 3.3.3.3
network 172.16.0.128 0.0.0.31 area 0
network 172.16.1.0 0.0.0.127 area 0
network 172.16.0.160 0.0.0.31 area 0
network 172.16.0.192 0.0.0.31 area 0
network 172.16.0.224 0.0.0.31 area 0
network 172.16.1.128 0.0.0.127 area 0
network 172.16.2.0 0.0.0.63 area 0
network 172.16.2.64 0.0.0.15 area 0
network 172.16.3.0 0.0.0.127 area 0
network 172.16.3.128 0.0.0.127 area 0
network 172.16.4.16 0.0.0.3 area 0
network 172.16.4.20 0.0.0.3 area 0
network 172.16.4.24 0.0.0.3 area 0
do wr
```

### At Router1:
```
router ospf 10
router-id 4.4.4.4
network 172.16.4.0 0.0.0.3 area 0
network 172.16.4.8 0.0.0.3 area 0
network 172.16.4.16 0.0.0.3 area 0
network 172.16.4.24 0.0.0.3 area 0
do wr
```

### At Router2:
```
router ospf 10
router-id 5.5.5.5
network 172.16.4.4 0.0.0.3 area 0
network 172.16.4.12 0.0.0.3 area 0
network 172.16.4.20 0.0.0.3 area 0
network 172.16.4.24 0.0.0.3 area 0
do wr
```

### At Main Campus Router:
```
router ospf 10
router-id 7.7.7.7
network 172.16.4.28 0.0.0.3 area 0
network 172.16.4.32 0.0.0.3 area 0
network 172.16.255.0 0.0.0.255 area 0
network 105.12.32.24 0.0.0.7 area 0
do wr
```

### At Border Router:
```
router ospf 10
router-id 6.6.6.6
network 172.16.4.32 0.0.0.3 area 0
network 105.12.32.16 0.0.0.3 area 0
do wr
```

### Static Routing at ISP
```
! Static routes for 172.16.0.0/16 networks
ip route 172.16.0.0 255.255.255.240 105.12.32.17
ip route 172.16.0.16 255.255.255.240 105.12.32.17
ip route 172.16.0.32 255.255.255.240 105.12.32.17
ip route 172.16.0.48 255.255.255.240 105.12.32.17
ip route 172.16.0.64 255.255.255.224 105.12.32.17
ip route 172.16.0.96 255.255.255.224 105.12.32.17
ip route 172.16.0.128 255.255.255.224 105.12.32.17
ip route 172.16.0.160 255.255.255.224 105.12.32.17
ip route 172.16.0.192 255.255.255.224 105.12.32.17
ip route 172.16.0.224 255.255.255.224 105.12.32.17
ip route 172.16.1.0 255.255.255.128 105.12.32.17
ip route 172.16.1.128 255.255.255.128 105.12.32.17
ip route 172.16.2.0 255.255.255.192 105.12.32.17
ip route 172.16.2.64 255.255.255.240 105.12.32.17
ip route 172.16.3.0 255.255.255.128 105.12.32.17
ip route 172.16.3.128 255.255.255.128 105.12.32.17
ip route 172.16.4.0 255.255.255.252 105.12.32.17
ip route 172.16.4.4 255.255.255.252 105.12.32.17
ip route 172.16.4.8 255.255.255.252 105.12.32.17
ip route 172.16.4.12 255.255.255.252 105.12.32.17
ip route 172.16.4.16 255.255.255.252 105.12.32.17
ip route 172.16.4.20 255.255.255.252 105.12.32.17
ip route 172.16.4.24 255.255.255.252 105.12.32.17
ip route 172.16.4.28 255.255.255.252 105.12.32.17
ip route 172.16.4.32 255.255.255.252 105.12.32.17
ip route 172.16.255.0 255.255.255.0 105.12.32.17

! Static route for 105.12.32.24/29 network
ip route 105.12.32.24 255.255.255.248 105.12.32.17
```

#### Redistribute static routes to OSPF
On routers and L3 switches
```
router ospf 10
redistribute static subnets
```



## Configure static IP addresses to Data Center Devices
Done using GUI
#### Configuration
Ip address: 172.16.2.67
Subnet mask: 255.255.255.240
Default gateway: 172.16.2.65
DNS server: 172.16.2.68

## Configure DHCP 
#### DHCP Server
Turn services on
Set default pool  0 0 0 0
Configure pools as per IP table and vlans


#### DHCP Relay

```
en
conf t

int vlan 10
no shutdown
ip address 172.16.0.1 255.255.255.240
ip helper-address 172.16.2.67
exit

int vlan 20
no shutdown
ip address 172.16.0.17 255.255.255.240
ip helper-address 172.16.2.67
exit

int vlan 30
no shutdown
ip address 172.16.0.33 255.255.255.240
ip helper-address 172.16.2.67
exit

int vlan 40
no shutdown
ip address 172.16.0.49 255.255.255.240
ip helper-address 172.16.2.67
exit

int vlan 50
no shutdown
ip address 172.16.0.65 255.255.255.224
ip helper-address 172.16.2.67
exit

int vlan 60
no shutdown
ip address 172.16.0.97 255.255.255.224
ip helper-address 172.16.2.67
exit

int vlan 70
no shutdown
ip address 172.16.0.129 255.255.255.224
ip helper-address 172.16.2.67
exit

int vlan 80
no shutdown
ip address 172.16.1.1 255.255.255.128
ip helper-address 172.16.2.67
exit


int vlan 90
no shutdown
ip address 172.16.0.161 255.255.255.224
ip helper-address 172.16.2.67
exit

int vlan 100
no shutdown
ip address 172.16.0.193 255.255.255.224
ip helper-address 172.16.2.67
exit

int vlan 110
no shutdown
ip address 172.16.0.225 255.255.255.224
ip helper-address 172.16.2.67
exit

int vlan 120
no shutdown
ip address 172.16.1.129 255.255.255.128
ip helper-address 172.16.2.67
exit

int vlan 130
no shutdown
ip address 172.16.2.1 255.255.255.192
ip helper-address 172.16.2.67
exit

int vlan 140
no shutdown
ip address 172.16.2.65 255.255.255.240
ip helper-address 172.16.2.67
exit

int vlan 150
no shutdown
ip address 172.16.3.1 255.255.255.128
ip helper-address 172.16.2.67
exit

int vlan 160
no shutdown
ip address 172.16.3.129 255.255.255.128
ip helper-address 172.16.2.67
exit

do wr
```

#### Additional DHCP config(optional - in case dhcp server failure)
On SW1
```
service dhcp
ip dhcp pool Finance
network 172.16.0.0 255.255.255.240
default-router 172.16.0.1
dns-server 172.16.2.68
exit

ip dhcp pool HumanResource
network 172.16.0.16 255.255.255.240
default-router 172.16.0.17
dns-server 172.16.2.68
exit

ip dhcp pool Admin
network 172.16.0.32 255.255.255.240
default-router 172.16.0.33
dns-server 172.16.2.68
exit

ip dhcp pool Procurement
network 172.16.0.48 255.255.255.240
default-router 172.16.0.49
dns-server 172.16.2.68
exit

ip dhcp pool CivilEngineering
network 172.16.0.64 255.255.255.224
default-router 172.16.0.65
dns-server 172.16.2.68
exit

ip dhcp pool MechanicalEngineering
network 172.16.0.96 255.255.255.224
default-router 172.16.0.97
dns-server 172.16.2.68
exit

ip dhcp pool LabBuilding3
network 172.16.1.128 255.255.255.128
default-router 172.16.1.129
dns-server 172.16.2.68
exit

ip dhcp pool ITDepartment
network 172.16.2.0 255.255.255.192
default-router 172.16.2.1
dns-server 172.16.2.68
exit

ip dhcp pool DataCenter
network 172.16.2.64 255.255.255.240
default-router 172.16.2.65
dns-server 172.16.2.68
exit

ip dhcp pool MaleHostel
network 172.16.3.0 255.255.255.128
default-router 172.16.3.1
dns-server 172.16.2.68
exit

ip dhcp pool FemaleHostel
network 172.16.3.128 255.255.255.128
default-router 172.16.3.129
dns-server 172.16.2.68
exit


ip dhcp pool Electrical
network 172.16.0.128 255.255.255.224
default-router 172.16.0.129
dns-server 172.16.2.68
exit

ip dhcp pool LabBuilding2
network 172.16.1.0 255.255.255.128
default-router 172.16.1.1
dns-server 172.16.2.68
exit

ip dhcp pool ComputerScience
network 172.16.0.160 255.255.255.224
default-router 172.16.0.161
dns-server 172.16.2.68
exit

ip dhcp pool Physics
network 172.16.0.192 255.255.255.224
default-router 172.16.0.193
dns-server 172.16.2.68
exit

ip dhcp pool Mathematics
network 172.16.0.224 255.255.255.224
default-router 172.16.0.225
dns-server 172.16.2.68
exit

do wr 

```




### Access Control List: Border Router
#### Facebook and YouTube
```
access-list 101 deny ip any 157.240.192.0 0.0.0.255
access-list 101 deny ip 172.16.3.0 0.0.0.127 208.65.153.0 0.0.0.255
access-list 101 deny ip 172.16.3.128 0.0.0.127 208.65.153.0 0.0.0.255
access-list 101 deny ip 172.16.1.0 0.0.0.127 208.65.153.0 0.0.0.255
access-list 101 deny ip 172.16.1.128 0.0.0.127 208.65.153.0 0.0.0.255
access-list 101 permit ip any any
int se0/3/0
ip access-group 101 in

```

### Access Control List: Main Campus Router
#### SMIS and ERP
```
access-list 103 permit ip 172.16.0.0 0.0.0.15 172.16.255.2 0.0.0.0
access-list 103 permit ip 172.16.0.32 0.0.0.15 172.16.255.2 0.0.0.0
access-list 103 permit ip 172.16.2.0 0.0.0.63 172.16.255.2 0.0.0.0
access-list 103 permit ip 172.16.3.0 0.0.0.127 172.16.255.2 0.0.0.0
access-list 103 permit ip 172.16.3.128 0.0.0.127 172.16.255.2 0.0.0.0
access-list 103 permit ip 172.16.1.0 0.0.0.255 172.16.255.2 0.0.0.0
access-list 103 permit ip 172.16.0.0 0.0.0.15 172.16.255.3 0.0.0.0
access-list 103 permit ip 172.16.0.32 0.0.0.15 172.16.255.3 0.0.0.0
access-list 103 permit ip 172.16.2.0 0.0.0.63 172.16.255.3 0.0.0.0
access-list 103 deny ip any 172.16.255.3 0.0.0.0
access-list 103 deny ip any 172.16.255.2 0.0.0.0
int gig0/0.10
ip access-group 103 out
```

#### Email and Web
```
access-list 105 permit ip any 105.12.32.26 0.0.0.0
access-list 105 permit ip any 105.12.32.27 0.0.0.0
access-list 105 deny ip any any
int gig0/0.20
ip access-group 105 out
```

### NAT
#### At border router
```
ip nat inside source list 1 interface se0/3/0 overload
access-list 1 permit 172.16.0.0 0.0.0.15
access-list 1 permit 172.16.0.16 0.0.0.15
access-list 1 permit 172.16.0.32 0.0.0.15
access-list 1 permit 172.16.0.48 0.0.0.15
access-list 1 permit 172.16.0.64 0.0.0.31
access-list 1 permit 172.16.0.96 0.0.0.31
access-list 1 permit 172.16.0.128 0.0.0.31
access-list 1 permit 172.16.1.0 0.0.0.127
access-list 1 permit 172.16.0.160 0.0.0.31
access-list 1 permit 172.16.0.192 0.0.0.31
access-list 1 permit 172.16.0.224 0.0.0.31
access-list 1 permit 172.16.1.128 0.0.0.127
access-list 1 permit 172.16.2.0 0.0.0.63
access-list 1 permit 172.16.2.64 0.0.0.15
access-list 1 permit 172.16.3.0 0.0.0.127
access-list 1 permit 172.16.3.128 0.0.0.127
int se0/3/1
ip nat inside
int se0/3/0
ip nat outside
```




