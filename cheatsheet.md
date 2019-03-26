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
|```ip route add {ip-route-to} via {ip-route-through}```|ustala trase dla adresu lub podsieci|@|


pliki
-----
|lokalizacja|opis|komentarz|
|:---------:|:--:|:-------:|
|  /proc/sys/net/ipv4/ip_forward |ip forwarding|tymczasowe|
|   /etc/sysctl.conf  |     ip forwarding | stałe|
|   /etc/network/interfaces |    ustawienia interfejsów | stałe|