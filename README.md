
# Werkstattauftrag W07-Webmin
<br>

# Inhaltsverzeichnis
 - [Autoren](#1-autoren-versionierung-des-dokumentes)
 - [Einfuerung](#2-einfuehrung)
 - [Hardware-Software](#3-benoetigte-hard--und-software)
 - [Installationsanleitung](#4-installationsanleitung)
 - [Qualitaetskontrolle](#5-qualitaetskontrolle)
 - [Error-Handling](#6-error-handling)
 - [Quellen](#7-quellen)
 - [Opensource Lizenz](#8-opensource-lizenz)





# 1. Autoren, Versionierung des Dokumentes
Autoren: Jonah Gutknecht, Thomas Züger<br>
Version: 1.0
<br>



# 2. Einfuehrung 
   - Beschreibung: Durch die Installation von Webmin kann durch die Web-App Systemkonfigurationen von Unix Systemen verwaltet werden. <br>
   - Zeitaufwand: Die Installation von WEBMIN (Werkstatt Auftrag 07) ist bis am 28.09.2021 um 11:05 abgeschlossen.<br>
   - Stolpersteine: Das RaspberryPI Linux image wurde von vorgehenden Schüler übernommen, wodurch möglicherweise wichtige Config-Files bereits angepasst wurden.<br>

# 3. Benoetigte Hard- und Software
   - Hardware Materialliste<br>
  1x RaspberryPI v4 (inkl. Stromkabel)<br>
  1x HDMI zu DVI Adapter<br>
  1x HDMI zu miniHDMI Adapter<br>
  1x Externer Bildschirm<br>
  1x Tastatur<br>
  1x Maus<br>
  <br>

   - Software Anforderungen<br>
1x RaspberryPI LInux Image<br>
1x Webmin (aktuellste Version)<br>


# 4. Installationsanleitung
 (Didaktisch reduzierte Anleitung. Lernende sollen eine eigene Lösungswege realisieren)
 Auf dem RaspberryPI WLAN einrichten.
 Für die Installation von WEBMIN werden zusätzliche Libaries verwendet. Mit folgendem Befehl können diese eingerichtet werden.
 <code>sudo apt-get install libnet-ssleay-perl libio-socket-ssl-perl</code>

**Installation Webmin**
Installation der aktuellsten WEBMIN Version 1.981
cd wget http://prdownloads.sourceforge.net/webadmin/webmin-1.981-
minimal.tar.gz

Entpacken der heruntergeladenen .tar.gz Datei:
tar -zxvf webmin-1.981 minimal.tar.gz

In den Ordner mit dem installiertem Setup wechseln und anschliessend die Setup Datei ausführen.
cd webmin-1.881
sudo ./setup.sh

Bei dem Setup kann alles auf default gelassen werden. Empfehlenswert ist das Wechseln des Passwortes. 
![Bild](/Bilder/change_password.png)

Nach der Installation von Webmin wird die Adresse von Webmin angezeigt. 
![Bild](/Bilder/webmin_installation_finished.png)

Default Benutzer: admin
Gesetztes Passwort: 12345

**Webmin konfigurieren**

Im Webmin Browserfenster können unter dem Punkt «Webmin
Configuration» und dann «Webmin Modules» weiter Module installiert werden.

Mit den drei Punkten auf der rechten Seite können zusätzliche Module installiert werden.
![Bild](/Bilder/webmin_additionally_modules.png)

Wähle das "useradmin" Modul an und gehe unten links auf "Install"
![Bild](/Bilder/install_useradmin.png)

Unter Standard module sollte nun "useradmin" stehen. Anschliessend kann auf "Install Module" geklickt werden.
![Bild](/Bilder/install_module.png)

Im Hauptmenu auf "System" und dann auf "User and Groups". In diesem Menu können nun neue User erstellt werden.
![Bild](/Bilder/create_user.png)

**Admin User Erstellen**

Weiter unten bei "Group Membership" kann der User noch in die Admin Gruppe genommen werden, damit dieser auch Admin Rechte hat.
![Bild](/Bilder/group_membership.png)
Zum Schluss ganz unten noch auf "create" klicken.

Anschliessend sieht man den erstellten Benutzer in der Liste
![Bild](/Bilder/created_user.png)

**User erstellen**

Hier wird noch ein normaler User Account erstellt.
![Bild](/Bilder/create_user_account.png)

Diesen User einfach in der Gruppe "Users" lassen.
![Bild](/Bilder/group_membership2.png)

**Admin User deaktivieren**
Falls der Admin deaktiviert werden soll, kann einfach der Admin Account ausgewählt und auf "Disable selected" geklickt werden.
![Bild](/Bilder/admin_user_deactivate.png)

In der Benutzerliste wird der deaktiviert Account jetzt Kursiv angezeigt.
![Bild](/Bilder/disabled.png)



# 5. Qualitaetskontrolle
Folgende Commands können ausgeführt werden um zu testen, ob alles richtig funktioniert.

**Status von Webmin überprüfen:**<br>
sudo service webmin status

**Webmin re/starten:**<br>
sudo /etc/webmin/start

**sudo service:**<br>
webmin restart

**Webmin stoppen:**<br>
sudo service webmin stop

**Konfiguration überprüfen:**<br>
cd /etc/webmin (Ordner von config files)


# 6. Error-Handling 

Wir hatten bei der Installation von Webmin keine grösseren Probleme


# 7. Quellen
Anleitung Installation Webmin
https://bscw.tbz.ch/bscw/bscw.cgi/31513531?op=preview&back_url=27527809

RaspberryPI OS
https://www.raspberrypi.org/software/

# 8. OpenSource Lizenz

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/ch/"><img alt="Creative Commons Lizenzvertrag" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/3.0/ch/88x31.png" /></a><br />Dieses Werk ist lizenziert unter einer <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/ch/">Creative Commons Namensnennung - Nicht-kommerziell - Weitergabe unter gleichen Bedingungen 3.0 Schweiz Lizenz</a>

 

- - -