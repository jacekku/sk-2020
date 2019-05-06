sieci cheatsheet
================


polecenia
---------
|polecenie|opis|komentarz|
|:---------:|:----:|:------------------:|
|```ping {ip}```|sprawdza połączenie z adresem ip|@|
|```ip (a)ddress```| pokazuje konfigurację interfejsów sieciowych|@|
|```ip a add {ip} dev {(int)erface}```|wiąże adres ip z interfejsem|@|
|```ip a del {ip} dev {int}```|usuwa adres ip z interfejsu|@|
|```ip a flush {int}```|usuwa wszystkie adresy z interfejsu|@|
|```ip link set {int} up```|uruchamia interfejs|@|
|```ip link set {int} down```|zatrzymuje interfejs|@|
|```ip route```|pokazuje tablice routingu|@|
|```ip route add default via {ip}```|ustala defaultowy adres do wysłania pakietu|@|
|```ip route add {ip-route-to} via {ip-route-through}```|ustala trase dla adresu lub podsieci|
|```iptables -t nat -A POSTROUTING -s 192.168.64.192/27 -o enp0s3 -j MASQUERADE```| ustawianie maskarady|



pliki
-----
|lokalizacja|opis|komentarz|
|:---------:|:--:|:-------:|
|  /proc/sys/net/ipv4/ip_forward |ip forwarding|tymczasowe|
|   /etc/sysctl.conf  |     ip forwarding | stałe|
|   /etc/network/interfaces |    ustawienia interfejsów | stałe|
|/etc/default/isc-dhcp-server|isc-dhcp-server tu ustalamy plik oraz |
|/etc/dhcp/dhcpd.conf|konfiguracja w pliku|subnet 192.168.64.192 netmask 255.255.255.225 {option domain-name-servers 8.8.8.8, 1.1.1.1;option routers 192.168.64.193;range 192.168.64.201 192.168.64.223}|
