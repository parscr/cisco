Basic Switch Configuration.

enter privileged EXEC mode
```
Switch> enable
Switch# 
```
Configuring a Hostname
```
Switch# configure terminal
Switch(config)# hostname Sw-Floor-1
Sw-Floor-1(config)#
```

Configure Passwords 
Console password
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line console 0
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```
privileged EXEC password
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# enable secret class
Sw-Floor-1(config)# exit
Sw-Floor-1#
```
Virtual terminal (vty) ssh/telnet password
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line vty 0 15
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```
Encrypt passwords
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# service password-encryption
Sw-Floor-1(config)#
```
Use the show running-config command to verify that passwords are now encrypted
```
Sw-Floor-1# show running-config
```
Configure a Banner
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# banner motd #Authorized Access Only#
```
Save Configuration Files to NVRAM
```
Sw-Floor-1#copy running-config startup-config
Sw-Floor-1#show startup-config
```
Configure Switch virtual interfaces (SVIs)
To access a switch remotely, an IP address and a subnet mask must be configured on the SVI
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# interface vlan 1
Sw-Floor-1(config-if)# ip address 192.168.1.20 255.255.255.0
Sw-Floor-1(config-if)# no shutdown
```
