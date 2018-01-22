Brief definition:
    `iptables is a commad-line firewall utility that uses policy chains to allow or block traffic`

Instalation:
    `sudo apt-get install iptables`


Polish text notes for better understanding
------------------------------------------

Typy łańcuchów reguł stosowanych dla pakietów:

    * INPUT - ruch przychodzący
    * OUTPUT - ruch wychodzący
    * FORWARD - ruch trasowany - przechodzący przez lokalną maszynę

> iptables -A : dołączenie reguły do istniejących

Sprawdzenie konfiguracji iptables
--------------------------
            iptables -L
            iptables -L | grep policy
            iptables -L -n -v
            iptables -L INPUT -n -v
            iptables -L OUTPUT -n -v --line-numbers

* -L : lista reguł
* -v : szczegółowe informacje
* -n : wyświetl adresy IP, nie DNS (przyśpiesza wyświetlenie reguł)

Akceptacja każdego ruchu
----------------------------
_iptables --policy INPUT ACCEPT_
_iptables --policy OUTPUT ACCEPT_
_iptables --policy FORWARD ACCEPT_

Blokowanie każdego ruchu
-----------------------------------
_iptables --policy INPUT DROP_
_iptables --policy OUTPUT DROP_
_iptables --policy FORWARD DROP_


Blokowanie połączeń z jednego adresu IP
----------------------------------------

iptables -A INPUT -s 10.10.10.10 -j DROP            

