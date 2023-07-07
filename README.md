### Dokumentation LB2
## Inhaltsverzeichnis
- [1. Einleitung](#1-einleitung)
- [2. Voraussetzungen](#2-voraussetzungen)
- [3. Beschreibung der Umgebung](#3-beschreibung-der-umgebung)
- [4. Vorgehen](#4-vorgehen)

# 1. Einleitung
Im Modul 300 wird im Umfang der LB2 ein Projekt mit Docker Umgesetzt. Der Service besteht aus 2 Webservern, welche eine Unterschiedliche Websiten anzeigen. Davor wird ein Nginx LoadBalancer geschaltet, der Anfragen auf dem Host auf [Localhost:8080](localhost:8080) beantwortet. Die einzelnen Webserver sind nicht mehr direkt erreichbar. Die Webserver werden mit Docker ```Compose up --build -d``` gestartet.

# 2. Voraussetzungen
Vom Github repository [aiannelli/LB2](https://github.com/aiannelli-tbz/LB2) können dan alle Daten bezogen werden.
Als Basis dafür wird ein Vagrant File aus einer vorherigen [Aufgabe](https://gitlab.com/mbe99/docker-work) verwendet. Diese VM verfügt bereits über einen shared Folder und Port weiterleitungen darunter auch ```80 --> 8080```. Auch ist Docker bereits installiert. Um die VM zu Starten muss im Arbeitsverzeichnis ```vagrant up``` ausgeführt werden.
Vom Github repository [aiannelli/LB2](https://github.com/aiannelli-tbz/LB2) können dan alle Daten bezogen werden.

# 3. Beschreibung der Umgebung
Die Umgebung besteht aus 3 Docker Containern. 2 Webservern und einem LoadBalancer. Die Webserver sind mit Apache2 auf port 80 mit dem inetrenen Docker-Netzwerk verbunden. Der LoadBalancer ist mit Nginx aufgesetzt. Die Webserver sind nicht direkt erreichbar, sondern nur über den LoadBalancer. Der LoadBalancer ist vom Host aus über den Port 8080 erreichbar.
![Netzplan der Umgebung](images/LB2_M300.PNG)

# 4. Vorgehen 
