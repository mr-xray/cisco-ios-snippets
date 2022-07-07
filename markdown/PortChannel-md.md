# Port-Channel

* Egal zwischen welchen **2 Devices** (Switch, Router, AP, ...)
* Auf Layer 2 PortChannel
* Auf Layer 3 Etherchannel
  * `no switchport` dann routed
  * Kann auch gemixed sein auf beiden Seiten &rarr; 1x `switchport` und 1x `no switchport` 
  * Layer 3 mit IP macht kein Sinn &rarr; Geht nicht mehr wenn irgendein Layer3-Error ist
  * Equal Cost Multiload Sharing default von Cisco
  * 

## 3 Modi

* LACP sehr langsam
* PAGP
* NON / ON

Nur zwischen mehr als 2 Devices wenn sie sich als 1 verhalten:

* STP-freie Topologien

* Stack 1-8 Devices &rarr; 1 Device übernimmt Kontrolle und programmiert alle anderen, verhält sich wie 1 Switch z.B.
* VSS 2 Devices
* SVW 2 Devices
* VPC auf Nexus



* EtherChannel
  * Jedes Device entscheidet für sich wo geschickt wird
  * By Default, balanced aufgrund von Hashing-Algorithmus src-mac oder src-ip
    * Hash aus Mac oder IP wird berechnet und einer Leitung 1 Hash zugeordnet
* Pro Device Etherchannel global tunebar
* `show etherchannel load-balance`
* `port-channel load-balanace`
  * `src-dest-ip` macht Sinn
  * `src-dst-mixed-ip-port` geht auch
  * Für non-ip `src-dst-ip`
* Port-Channel eig. nur für Redundanzzwecke
* Wenn ich Layer 2 Etherchannel hab aber Layer 3 Kommunikation haben will dann über VLANs