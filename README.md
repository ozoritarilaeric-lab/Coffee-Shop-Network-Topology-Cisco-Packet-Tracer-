# Build-a-Coffee-Shop-Network-in-Cisco-Packet-Tracer

# Configuration for the Router
 1 subnet is currently in the pool
 Current index        IP address range                    Leased/Excluded/Total
 192.160.20.1         192.160.20.1     - 192.160.20.254    0    / 3     / 254

Pool GUEST_WIFI :
 Utilization mark (high/low)    : 100 / 0
 Subnet size (first/next)       : 0 / 0 
 Total addresses                : 254
 Leased addresses               : 0
 Excluded addresses             : 3
 Pending event                  : none

 1 subnet is currently in the pool
 Current index        IP address range                    Leased/Excluded/Total
 192.160.30.1         192.160.30.1     - 192.160.30.254    0    / 3     / 254
CoffeeShop-RTR#show runn
CoffeeShop-RTR#show running-config 
Building configuration...

Current configuration : 2148 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname CoffeeShop-RTR
!
!
!
enable secret 5 $1$mERr$Pq3/lr0agnISq0fxb9TUZ0
!
!
ip dhcp excluded-address 192.160.10.1 192.160.10.20
ip dhcp excluded-address 192.160.10.1 192.160.20.20
ip dhcp excluded-address 192.160.30.1 192.160.30.20
!
ip dhcp pool MANAGEMENT_OFFICE
 network 192.160.10.0 255.255.255.0
 default-router 192.160.10.1
 dns-server 0.0.0.0
ip dhcp pool POS
 network 192.160.20.0 255.255.255.0
 default-router 192.160.20.1
 dns-server 0.0.0.0
ip dhcp pool GUEST_WIFI
 network 192.160.30.0 255.255.255.0
 default-router 192.160.30.1
 dns-server 0.0.0.0
!
!
!
ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX152440X3-
!
!
!
!
!
!
!
!
!
!
!
no ip domain-lookup
!
!
spanning-tree mode pvst
!
!
!
!
!
!
interface GigabitEthernet0/0
 description TO_ISP
 no ip address
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 description TO_COFFEESHOP_SW
 no ip address
 duplex auto
 speed auto
!
interface GigabitEthernet0/1.10
 description MANAGEMENT_OFFICE_GATEWAY
 encapsulation dot1Q 10
 ip address 192.160.10.1 255.255.255.0
!
interface GigabitEthernet0/1.20
 description POS_GATEWAY
 encapsulation dot1Q 20
 ip address 192.160.20.1 255.255.255.0
!
interface GigabitEthernet0/1.30
 description GUEST_WIFI_GATEWAY
 encapsulation dot1Q 30
 ip address 192.160.30.1 255.255.255.0
 ip access-group GUEST_RESTRICTIONS in
!
interface GigabitEthernet0/1.99
 description NETWORK_MANAGEMENT_GATEWAY
 encapsulation dot1Q 99
 ip address 192.160.99.1 255.255.255.0
!
interface GigabitEthernet0/2
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
!
ip flow-export version 9
!
!
ip access-list extended GUEST_RESTRICTIONS
 deny ip 192.160.30.0 0.0.0.255 192.160.10.0 0.0.0.255
 deny ip 192.160.30.0 0.0.0.255 192.160.99.0 0.0.0.255
 permit ip 192.160.30.0 0.0.0.255 any
!
banner motd ^C


Unauthorized access is prohibited

^C
!
!
!
!
line con 0
 password 7 0802455D0A165445414A
 logging synchronous
 login
!
line aux 0
!
line vty 0 4
 login
!
!
!
end


CoffeeShop-RTR#
CoffeeShop-RTR#cop
CoffeeShop-RTR#copy runn
CoffeeShop-RTR#copy running-config star
CoffeeShop-RTR#copy running-config startup-config 
Destination filename [startup-config]? 
Building configuration...
[OK]
CoffeeShop-RTR#
CoffeeShop-RTR#
CoffeeShop-RTR#
CoffeeShop-RTR#
CoffeeShop-RTR#








CoffeeShop-RTR con0 is now available






Press RETURN to get started.


# Configuration of the Switch
                                                Fa0/24, Gig0/1, Gig0/2
10   MANAGEMENT_OFFICE                active    Fa0/1, Fa0/2, Fa0/3, Fa0/4
                                                Fa0/5
20   POS                              active    Fa0/6, Fa0/7, Fa0/8, Fa0/9
                                                Fa0/10
30   GUEST_WIFI                       active    Fa0/11
99   NETWORK_MANAGEMENT               active    
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active    
CoffeeShop-SW#show inter tru
CoffeeShop-SW#show inter trunk 


CoffeeShop-SW#show ip inter brief
Interface              IP-Address      OK? Method Status                Protocol 
FastEthernet0/1        unassigned      YES unset  up                    up 
FastEthernet0/2        unassigned      YES unset  up                    up 
FastEthernet0/3        unassigned      YES unset  down                  down 
FastEthernet0/4        unassigned      YES unset  down                  down 
FastEthernet0/5        unassigned      YES unset  down                  down 
FastEthernet0/6        unassigned      YES unset  up                    up 
FastEthernet0/7        unassigned      YES unset  up                    up 
FastEthernet0/8        unassigned      YES unset  down                  down 
FastEthernet0/9        unassigned      YES unset  down                  down 
FastEthernet0/10       unassigned      YES unset  down                  down 
FastEthernet0/11       unassigned      YES unset  up                    up 
FastEthernet0/12       unassigned      YES unset  down                  down 
FastEthernet0/13       unassigned      YES unset  down                  down 
FastEthernet0/14       unassigned      YES unset  down                  down 
FastEthernet0/15       unassigned      YES unset  down                  down 
FastEthernet0/16       unassigned      YES unset  down                  down 
FastEthernet0/17       unassigned      YES unset  down                  down 
FastEthernet0/18       unassigned      YES unset  down                  down 
FastEthernet0/19       unassigned      YES unset  down                  down 
FastEthernet0/20       unassigned      YES unset  down                  down 
FastEthernet0/21       unassigned      YES unset  down                  down 

CoffeeShop-SW#show run
CoffeeShop-SW#show running-config 
Building configuration...

Current configuration : 3002 bytes
!
version 12.2(37)SE1
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname CoffeeShop-SW
!
!
no profinet
enable secret 5 $1$mERr$Pq3/lr0agnISq0fxb9TUZ0
!
!
!
!
!
!
!
!
username admin privilege 15 secret 5 $1$mERr$Pq3/lr0agnISq0fxb9TUZ0
!
!
!
!
!
!

CoffeeShop-SW#
CoffeeShop-SW#
CoffeeShop-SW#
CoffeeShop-SW#
CoffeeShop-SW#
CoffeeShop-SW#








CoffeeShop-SW con0 is now available






Press RETURN to get started.












%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan99, changed state to up



Unauthorized access is prohibited.



User Access Verification

Password: 
Password: 
% Password:  timeout expired!
















Press RETURN to get started!



Unauthorized access is prohibited.



User Access Verification

Password: 
Password: 
% Password:  timeout expired!
















Press RETURN to get started!



Unauthorized access is prohibited.



User Access Verification

Password: 
Password: 
Password: 
% Password:  timeout expired!
















Press RETURN to get started!












