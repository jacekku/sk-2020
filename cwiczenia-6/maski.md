Struktura adresu IP
-------------------

Adres ip ```192.168.100.192```
Maska   ```255.255.255.0```

Adres sieci
-----------

1. Adres ip do postaci binarnej
2. Maska do postaci binarnej
3. bitwise and binarnego ip oraz binarnej maski

Adres rozgłoszeniowy
-----------

1. Oblicz adres sieci
2. Zaneguj maskę
3. bitwise or negacji maski oraz adresu sieci


Podział na równą ilość podsieci
-------------------------------

```2^S >= n```

Wyszukaj najmniejszą potęge dwójki spełniającą warunek

Chcemy 7 -> 2^3 >= 7

Maska -> 255.255.255.11100000 -> 255.255.255.224 -> /27


Wprowadzenie
------------

------------------------------
| dziesiętnie |  binarnie   | 
| --------- |:-------------| 
| ``10``  |  ``00001010``| 
| ``92``  | ``01011100``| 
| ``37``  | ``00100101``| 
| ``240`` | ``11110000``| 
| ``192`` | ``11000000``| 
| ``255`` | ``11111111``| 
| ``128`` | ``10000000``| 
| ``168`` | ``10101000``| 


------------------------------
| binarnie |  dziesiętnie   | 
| --------- |:-------------| 
| ``00100000``  |  | 
| ``11111000``  | | 
| ``10100000``  | | 
| ``00110000`` | | 
| ``10101100`` | | 
| ``01000000`` | | 
| ``11111100`` | | 
| ``01100010`` | | 
 
Notacja CIDR
------------
 
------------------------------
| maska |  /(X) x - liczba bitów   | 
| --------- |:-------------| 
| ``255.255.255.0``   | ``8+8+8+0 =/24``| 
| ``255.128.0.0``     | ``8+1+0+0 =/9``| 
| ``255.255.252.0``   | ``8+8+?+0 =/??``| 
| ``255.255.254.0``   | ``8+8+7+0 =/23``| 
| ``255.255.255.240`` | ``8+8+8+4 =/28``| 
| ``255.240.0.0``     | ``8+4+0+0 =/12``| 

------------------------------
| CIDR |  Maska   | 
| --------- |:-------------| 
| ``/8``    | 255.0.0.0| 
| ``/20``   | | 
| ``/30``   | | 
| ``/16``   | | 
| ``/27``   | | 
| ``/11``   | | 


Liczba hostów
-------------

------------------------------
| sieć |  liczba   | 
| --------- |:-------------| 
| ``10.0.0.0/8``    | | 
| ``172.16.0.0/16``   | | 
| ``192.168.1.0/24``   | | 
| ``192.168.1.0/27``   | | 
| ``192.168.1.0/29``   | | 
| ``192.168.1.0/31``   | | 

* liczba 0 w masce?


Parametry na podstawie adresu
-----------------------------

Mając dany adres hosta i maskę znajdź:
  * adres sieci
  * początkowy adres hosta w sieci
  * liczbę hostów w zadanej podsieci ```2^(32 bity - bity maski maska) - 2 (siec i broadcast)```
  * końcowy zakres adresu hosta w sieci
  * adres rozgłoszeniowy
  
  ------------------------------
| Parametr |  wartość   | 
| --------- |:-------------| 
| ``ip``    | 192.168.1.145| 
| ``maska``   | 255.255.255.128 | 
| ``adres sieci``   | |
| ``liczba hostów``   | |
| ``host - min``   | | 
| ``host - max``   | | 
| ``broadcast``   | | 
 
Zadanie
------------

0. Znajdz wszystkie parametry sieci dla hosta o adresie 172.16.128.64 / 16
  
------------------------------
| Parametr |  wartość   | 
| --------- |:-------------| 
| ``ip``    | 192.168.1.145| 
| ``maska``   | 255.255.255.128 | 
| ``adres sieci``   | |
| ``liczba hostów``   | |
| ``host - min``   | | 
| ``host - max``   | | 
| ``broadcast``   | | 

1.
  * Podziel sieć ```192.168.1.0``` na 16 równych podsieci
  
----------------------------------------------------------
| Adres sieci |  zakres hostów   | Adres Rozgłoszeniowy |
| --------- |:-------------|  :---------------|
| ``192.168.1.0``    | | |
| ````   | | |
| ````   | | |
| ````   | | |
| ````   | | |
| ````   | | |

2. 
  * Podziel sieć ``172.16.0.0/16`` na 6 równych podsieci.

3. 
  * Podziel sieć ``192.168.1.0/24``, tak aby każda podsieć miała 11 użytkowników.

4. 
  * Podziel sieć ``10.0.0.0/8`` na 5 podsieci. 
    * Podsieć A ma posiadać 100 000 użytkowników,
    * B – 10 000 użytkowników
    * C – 3 000 użytkowników
    * D – 500 użytkowników
    * E – 2 użytkowników.
    
