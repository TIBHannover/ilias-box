# Vagrant - Ansible – Ilias – Edu Sharing



## Installieren von Ilias mit Vagrant

Für die Installation muss Git, Vagrant und VirtualBox installiert werden.
Klonen Sie unter https://git.tib.eu/boxes/ilias-box die Vagrant-Box. Alternativ kann man auch ein Zip-File runterladen und es entpacken. Wechseln Sie in diesen Projektordner.
Ilias kann in der Kommandozeile mit dem Befehl sudo vagrant up installiert werden. Dieser Vorgang dauert etwa 10 Minuten. 
Das Ansible-Skript muss nicht extra gestartet werden, dies läuft über die Provision von Vagrant. Ilias wird in der Version 5.2 installiert, da sonst das Edu-Sharing Plug-In nicht funktioniert.


## Konfigurieren von Ilias

Als erstes kommt ein Prüffenster, hier sollte alles in Ordnung sein.
Die Verzeichnisse für die Konfiguration sind bereits durch Ansible erstellt. Im Webmenü müssen diese noch eingetragen werden. 
Zum einen das Working-Directory /home/vagrant/ilias und /home/vagrant/ilias/ilias.log. Die Zeitzone sollte Berlin sein, diese kann man einfach auswählen. 
Der Rest ist voreingestellt. Auf „save“ klicken. Ganz unten ist noch das Master Passwort einzugeben. Nun kann man eine beliebige Client-Id vergeben

Das Passwort für den Nutzer Ilias ist 12345678, das sollte vor der Installation geändert werden!, d.h. bevor Sie Vagrant starten.
Nach einem Klick auf „save“ sollte folgendes Fenster erscheinen:
Setzen Sie das Häckchen und wählen Sie utf8 als Charset aus, bitte nichts anderes.
Nach der Datenbankinstallation kommt eine Übersicht in der es notwendig sein kann auch Hotfixes für die Datenbank einzuspielen.
In dem hier gezeigten Beispiel wurde der Nutzer ilias auf der Datenbank eingerichtet und 65 Hotfixes eingespielt.
Als nächtes wird die Sprache eingerichtet:

Ein weiterer Schritt besteht in der Angabe weiter Informationen über den Client. Rote Sternchen sind Pflichtfelder. 

Klicken Sie auch hier auf „save“ und danach auf „next“.
Falls Sie einen Proxy benötigen kann dieser hier eingerichtet werden.
Wer sich registrieren möchte kann das in diesem Schritt tun.
Als letztes zeigt Ilias Ihnen den Default-Login, wenn Sie auf „login“ klicken werden aufgefordert ein neues Passwort zu setzen.
Danach ist Ilias einsatzbereit.

### Konfigurieren von Ilias mit Edu Sharing

Das Edu-Sharing Plug-In liegt in der Version 0.0.6 vor:

Unter „Action“ findet man die Auswahl „Install“ und „Information“. In der Regel sollte das Plug-In nach dem hochfahren von Vagrant installiert sein. 