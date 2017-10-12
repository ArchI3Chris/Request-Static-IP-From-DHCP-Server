# Request Static IP Address From DHCP Server

Recently I got a new Internet connection. The old modem/router did allow the use of static IP addresses. The new one doesn't. And by that I mean, not only the settings. It doesn't even accept IP 
addresses given by the host settings. And disabling the DHCP Server results in no device being able to connect at all. After testing a number of options, I've found this solution.

# What It Does

Even though the DHCP Server accept any settings, the script just asks nicely for the IP address you want for the host. And in my case the router does accept the request and assigns the requested IP 
address.

# Manual

In the dhclient.conf file enter the desired IP address. Of course make sure it is a valid one. You want get something 10.10.10.10, if you are on a 192.168.1.x network. You'll know where ;)  And in the 
dhc file enter the network interface you use to connect with the DHCP server. If you don't know, "ip addr" should give you a clue. Make sure the permissions are set correctly for dhc to be an 
executable (chmod +x dhc). Then run dhc. I guess you have to run it as sudo/root. I always do. So, I don't know if it works for a normal user.

# Requirements

* Linux
* dhclient

I don't know if there is a solution for Windows or if it works for MAC too.
