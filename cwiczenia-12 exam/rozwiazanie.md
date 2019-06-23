# Rozwiązanie
## WiFi

siec wifi ma pomiescic 800 hostow wiec potrzebujemy maski /22

`192.168.0.0/22`

## LAN
dla adresów LANowych weźmiemy sieć prywatną 

`10.0.0.0/8`

aby można było użyć odpowiadających adresów sieci dla laboratoriów np:

`10.0.9.0/26` dla sali 009

maska /26 zapewnia nam 62 adresy hostów na każdą salę.

## SALE
### Parter
---
009 - `10.0.9.0/26`

013 - `10.0.13.0/26`

014 - `10.0.14.0/26`

017 - `10.0.17.0/26`
### Piętro 1
---
115 - `10.0.115.0/26`

116 - `10.0.116.0/26`

117 - `10.0.117.0/26`

122 - `10.0.122.0/26`
### Piętro 2
---
201 - `10.0.201.0/26`

202 - `10.0.202.0/26`

203 - `10.0.203.0/26`

204 - `10.0.204.0/26`

## Diagram
![diagram](diagram.png)

### Diagram w programie GNS3
![diagram_working](diagram_working.png)



## Konfiguracja
* Wszystkie routery mają ustawiony ip forwarding w pliku `/etc/sysctl.conf`

* Ustawianie ip na interfejs `ip a add {ip} dev {interfejs}`
* Ustawianie maskarady `iptables -t nat -A POSTROUTING -s {ip obslugiwanej sieci} -o {interfejs wyjsciowy} -j MASQUERADE`
* Ustawianie routingu default `ip route add default via {ip}`


### Main Router
#### Interfejsy
polecenie `ip a`

![MR_ipa.png](MR_ipa.png)

#### Routing
polecenie `ip route`

![MR_routing.png](MR_routing.png)
#### Maskarady
polecenie `iptables -t nat -L`

![MR_masquerade.png](MR_masquerade.png)
#### Serwer DHCP dla sieci LAN
polecenia 

`apt-get install isc-dhcp-server`

`systemctl start isc-dhcp-server`

pliki 

`/etc/default/isc-dhcp-server`

`/etc/dhcp/dhcpd.conf`

![MR_dhcp.png](MR_dhcp.png)

### LAN router
#### Interfejsy
polecenie `ip a`

![LR_ipa.png](LR_ipa.png)

#### Routing
polecenie `ip route`

![LR_routing.png](LR_routing.png)
#### Maskarady
polecenie `iptables -t nat -L`

![LR_masquerade.png](LR_masquerade.png)

### K01
#### Interfejsy
polecenie `ip a`

![K01_ipa.png](K01_ipa.png)

#### Routing
polecenie `ip route`

![K01_routing.png](K01_routing.png)
#### Statyczny ip na interfejs
plik `/etc/network/interfaces`

![K01_static_interface.png](K01_static_interface.png)