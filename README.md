# TP5

## Préparation des VM

création a partir de la VM patron de 3 nouvelle VM, serveur1, client1 et client2. Parametrage des VM dans VirtualBox (interface host-only en 2eme carte) et GNS3 (ajout dans preferences + 2 carte reseau)

## Préparation de routeurs CISCO

Import de l'iso puis ajout de 2 routeurs dans GNS3, routeur1 et routeur2

## Lancement et configuration du Lab

Remplir toute les checklists puis:

Ping serveur1 par client1 : `ping -c 4 server1`

PING server1 (10.5.1.10) 56(84) bytes of data.
64 bytes from server1 (10.5.1.10): icmp_seq=1 ttl=62 time=22.9 ms                                                                   
64 bytes from server1 (10.5.1.10): icmp_seq=2 ttl=62 time=25.2 ms                                                                
64 bytes from server1 (10.5.1.10): icmp_seq=3 ttl=62 time=35.1 ms                                                              
64 bytes from server1 (10.5.1.10): icmp_seq=4 ttl=62 time=28.6 ms                                                               

--- server1 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3010ms
rtt min/avg/max/mdev = 22.961/28.007/35.141/4.590 ms
 3005ms
rtt min/avg/max/mdev = 38.164/41.702/43.773/2.157 ms


Ping serveur1 par client2 : `ping -c 4 server1`

PING server1 (10.5.1.10) 56(84) bytes of data.
64 bytes from server1 (10.5.1.10): icmp_seq=1 ttl=62 time=43.7 ms
64 bytes from server1 (10.5.1.10): icmp_seq=2 ttl=62 time=41.8 ms
64 bytes from server1 (10.5.1.10): icmp_seq=3 ttl=62 time=43.0 ms
64 bytes from server1 (10.5.1.10): icmp_seq=4 ttl=62 time=38.1 ms

--- server1 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3005ms
rtt min/avg/max/mdev = 38.164/41.702/43.773/2.157 ms


Ping client1 par serveur1 : `ping -c 4 client1`

PING client1 (10.5.2.10) 56(84) bytes of data.
64 bytes from client1 (10.5.2.10): icmp_seq=1 ttl=62 time=34.4 ms
64 bytes from client1 (10.5.2.10): icmp_seq=2 ttl=62 time=34.5 ms
64 bytes from client1 (10.5.2.10): icmp_seq=3 ttl=62 time=32.3 ms
64 bytes from client1 (10.5.2.10): icmp_seq=4 ttl=62 time=40.8 ms

--- client1 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3016ms
rtt min/avg/max/mdev = 32.328/35.555/40.807/3.169 ms


Ping client2 par serveur1  : `ping -c 4 client2`

PING client2 (10.5.2.11) 56(84) bytes of data.
64 bytes from client2 (10.5.2.11): icmp_seq=1 ttl=62 time=24.5 ms
64 bytes from client2 (10.5.2.11): icmp_seq=2 ttl=62 time=29.9 ms
64 bytes from client2 (10.5.2.11): icmp_seq=3 ttl=62 time=38.1 ms
64 bytes from client2 (10.5.2.11): icmp_seq=4 ttl=62 time=40.2 ms

--- client2 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3002ms
rtt min/avg/max/mdev = 24.563/33.220/40.205/6.303 ms

## DHCP

`systemctl status dhcpd` 

`● dhcpd.service - DHCPv4 Server Daemon  
   Loaded: loaded (/usr/lib/systemd/system/dhcpd.service; disabled; vendor preset: disabled)  
   Active: active (running) since Mon 2019-02-25 20:37:08 CET; 1min 7s ago  
     Docs: man:dhcpd(8)  
           man:dhcpd.conf(5)  
 Main PID: 3443 (dhcpd)  
   Status: "Dispatching packets..."  
   CGroup: /system.slice/dhcpd.service  
           └─3443 /usr/sbin/dhcpd -f -cf /etc/dhcp/dhcpd.co...`
