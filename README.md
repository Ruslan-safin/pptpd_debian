# README #

### Deploy PPTPd on Debian ###

* Version 15.07.16

### How do I get set up? ###

* Install required software: `apt-get install pptpd`
* Copy config files
* Enable ip forwarding: `echo 1 > /proc/sys/net/ipv4/ip_forward`
* Enable ip forwarding: `echo "net.ipv4.ip_forward=1" >> /etc/sysctl.conf`
* Enable GRE:  `iptables -A INPUT -p gre -j ACCEPT`
* Enable NAT:  `iptables -t nat -A POSTROUTING -s 10.0.0.0/12 -j`
* Config MTU:  `iptables -A FORWARD -p tcp -m tcp --tcp-flags SYN,RST SYN -j TCPMSS --clamp-mss-to-pmtu`

### Who do I talk to? ###

* Repo owner CyberManiac