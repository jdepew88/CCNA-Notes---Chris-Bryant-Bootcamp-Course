**Switch Terminal Commands Notes**

en=enable

conf t= configure terminal

int= interface

most commands require priv exec mode / enable mode

usually passwd protected

default timeout is 5 min – you may want to make that longer in a lab environment

to edit the length of time go to global config mode (conf t)

and then enter into the console port line(similar to interface mode)

line con 0

SW1(config-line)#logging synchronous

logging synchronous prevents the console from providing log items to your attention while you are busy typing in another command (this is mainly a convenience setting so you do not get interrupted typing a long command)

SW1(config-line)#exec-timeout 30 (note:30 is the number of minutes before being logged out)

SW1(config-line)#exec-timeout 0 0 (this sets timeout to 0 minutes 0 seconds. Meaning it will never timeout)

Disable: Timestamps: conf t \> no service timestamps

Collision and Broadcast domains

Every port is its own *Collision domain*

Every VLAN is its own *broadcast domain* (abbr BC domain)

When a host in a VLAN Domain sends a broadcast and a switch receives it, a copy of that broadcast is sent to every switchport that is member of that *BC domain* except the port that received it in the first place

Switchport can be in either access or trunk mode

Access ports can only be assigned to one vlan

Trunkports belong to all vlans by default

Trunkports connect to other switchs

Initial Setup for Lab switches

Hostname – SW1 SW2 SW3

Enable secret cisco

No service timestamps

**int Console 0 setup (**aka console port settings)

SW#(Config-line)#logging synchronous

SW#(Config-line)#exec-timeout 0 0

**VLAN 1** settings int vlan 1

SW#(Config-if)#ip address 10.1.1.3 255.255.255.0

Interface Fa 0/1

SW#(Config-if)#switchport mode trunk (you would have to set encapsulation on newer switches)

SW#(Config-if)#no shut
