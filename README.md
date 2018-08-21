# lubuntu-shopware-stack
lubuntu-shopware-stack

lubuntu-shopware-stack.ova (parts < 25mb ). click the exe to glue it.

below you see a snapshot of https://piratenpad.de/p/lubuntu-bitnami-shopware from 20.08.2018 06:50


These materials are provides "as is" without warranty of any kind, either expressed or implied

youre here:
    https://piratenpad.de/p/lubuntu-bitnami-shopware
    https://github.com/sl5net/lubuntu-shopware-stack

19.08.2018 23:11 ... 31 installing (checkbox minimal installation) , check login se automatically

https://askubuntu.com/questions/63420/how-to-fix-virtualboxs-copy-and-paste-to-host-machine
/media/<user>/VBOXADDITIONS_x.x.x/)
Install it sudo sh ./VBoxLinuxAdditions.run
Reboot the virtual machine!
sudo reboot now
19.08.2018 23:38 - 19.08.2018 23:38 funktioniert :)
Lbuntu (neue Maschinen erhalten neue IDs)

19.08.2018 23:39 software entfernen 19.08.2018 23:45

sicherung machen : in der maschine: maschine > sicherungspunkt erstellen. ca 12 Sekunden

20.08.2018 00:05
https://bitnami.com/stack/shopware/installer
geht so nicht.

20.08.2018 00:13 versuch:
veränderung der vorlage:
chmod 755 bitnami-APPNAME-VERSION-linux.run
./bitnami-APPNAME-VERSION-linux.run
zu:
bitnami-shopware-5.4.6-0-linux-x64-installer.run
./bitnami-shopware-5.4.6-0-linux-x64-installer.run
phpmyadmin und shopware werden dadurch installiert
/home/se/shopware-5.4.6-0
admin / se
angeboten wird als 
hostadresse: 127.0.1.1
====> hier erstmal schnapshop
20.08.2018 00:24
192.168.178.29        se-VirtualBox.fritz.box   (gefunden mit netscan5.4_64bit.exe)
dauert wieder an bisschen. mal sehen ob ich dann so von aussen auf den shop komme.
CPU immerhin zwischen 40 und 70% auslastung.
20.08.2018 00:34 fertig. also hat auch noch mal 10min gedauert.
schön is :) er is auch lokal unter http://192.168.178.29:8080/ aufrufbar :)
total super :) als lokal un remote über 192.168.178.29:8080 aufrufbar. also wichtig diese einstellung :)

SyncThing konfigurieren.
/home/se/shopware-5.4.6-0/apps/shopware/htdocs
oder /home/se/shopware-5.4.6-0/apps/shopware/htdocs/themes
ich nehme /home/se/shopware-5.4.6-0/apps/shopware/htdocs/themes

20.08.2018 01:07 
Error on folder folder marker missing
ich hab halt im Zielfolder bissl gelöscht und dann auch die Ordnernamen noch mal schnell vertauscht.
Da is sicher ein folder folder marker verlohren gegnagen. Soll es halt einen neuen schreibn ... hmmmm
20.08.2018 01:08
https://forum.syncthing.net/t/error-on-folder-folder-marker-missing/12012
 20.08.2018 01:34 WorkAround: i deleted folder “htdocs” in B an let created all it new

20.08.2018 05:31 http://192.168.178.29:8080/phpmyadmin
For security reasons, this URL is only accessible using localhost (127.0.0.1) as the hostname.

sudo apt-get install mlocate === > findet nix. naja
mlocate httpd-app.conf
nano /home/se/shopware-5.4.6-0/apps/phpmyadmin/conf/httpd-app.conf 
# Allow from 127.0.0.1 <== old
Allow from all
# Require local <== old
Require all granted
but you need to reboot apache for http://192.168.178..../phpmyadmin/
/home/se/shopware-5.4.6-0/ctlscript.sh restart
Syntax OK hat funktioniert :)
übrigens geht auch: 
/home/se/shopware-5.4.6-0/manager-linux-x64.run
Syntax OK hat funktioniert :)
20.08.2018 06:21
Zugangs-Login-Daten liegen in: /home/se/shopware-5.4.6-0/apps/shopware/htdocs/config.php



phpstorm:
download innerhalb phpstorm dauert:
15.08.2018 21:43 - 18-08-15_21-40
und indexing dauert auch sehr lang:
Viellseicht so 10 min

danach einige dirs excluden.

optional zu syncThing installieren:
sudo apt-get install proftpd-basic
sudo apt-get install gadmin-proftpd
starte über SystemTools > GAD ....
/home/se/shopware-5.4.6-0/apps/shopware/htdocs
user=pas: sesese
sudo /etc/init.d/inetd restart <== 20.08.2018 07:58 funktioniert nicht

andere ftp alternative:
    https://de.wikihow.com/Einen-FTP-Server-in-Ubuntu-Linux-einrichten
sudo apt-get upgrade (20.08.2018 08:10 kann unter umständen ziemlich lange dauern ... Oops )
sudo apt-get install vsftpd
sudo nano /etc/vsftpd.conf

Bentzer einrichten:
sudo systemctl restart vsftpd

#######################################
ende
#######################################
#######################################


    
15.08.2018 21:57 deutsch demo daten installieren und aktivieren
15.08.2018 21:59 hat funktioniert :) http://192.168.178.24/

15.08.2018 22:02
neu theme von responisve: sLnetA 
select

15.08.2018 22:23: empfehlung zusätlzlich zur synchronisierung in phpstorm
in filezilla
dem synchronisierten verzeichniswechsel einschalten umd starten bei zb
...\apps\shopware\htdocs\themes\Frontend\SLnetA

16.08.2018 08:00
Lokal eine VirtualBox installiert (Bitnami Shopware Virtual Machine)
und eingerichtet (PHPMyAdmin, PHP-Zeugs usw. ). 
Problem: kein upload neu erstellter Dateien oder Ordner (upload gänderter Dateien geht) über
    sftp://bitnami@192.168.178.23/
Auf dem Debian hab ich leider nur die Konsole und eine englische Tastatur (also immer Y statt Z drücken usw.)
Mir an Tipp was ich machen oder wo ich fragen kann? Kann auch gerne diesese ViertualBox Box hochladen zum download.

Neuer Plan (16.08.2018 08:26):  https://manjaro.org/manjaro-preview-releases/

https://www.drupal.org/docs/develop/local-server-setup/linux-development-environments/xampp-for-linux

https://community.apachefriends.org/f/viewtopic.php?f=29&t=42011

problem ProFTPD keine upload rechte. https://community.apachefriends.org/f/viewtopic.php?f=17&t=69296&hilit=mysql+can%2527t+start&sid=5eccf6a88f6019e0d4e33a5ad41e7ff0
https://wiki.ubuntuusers.de/Archiv/ProFTPD/
https://stackoverflow.com/questions/3740152/how-do-i-set-chmod-for-a-folder-and-all-of-its-subfolders-and-files

https://www.google.de/search?q=proftpd+config+file&oq=proftpd.conf&aqs=chrome.1.69i57j0l5.3488j0j7&sourceid=chrome&ie=UTF-8


VirtualBox:/etc/proftpd$ sudo service syncthing start
Failed to start syncthing.service: Unit syncthing.service not found.


https://forum.syncthing.net/t/not-starting-in-lubuntu/11993

probaly here you find the config:
 nano /opt/lampp/etc/proftpd.conf 

https://wiki.ubuntuusers.de/XAMPP/
sudo /opt/lampp/lampp security
Dieser Befehl zeigt folgenden Dialog im Terminal an (aus Demonstrationsgünden wurde hier jeweils die Option "Nein" gewählt):

https://askubuntu.com/questions/63420/how-to-fix-virtualboxs-copy-and-paste-to-host-machine
/media/<user>/VBOXADDITIONS_x.x.x/)
Install it sudo sh ./VBoxLinuxAdditions.run
Reboot the virtual machine!

The following is not working:
To enable file sharing on a Lubuntu 10.10 machine, go to Preferences > Synaptic Package Manager and add the following:-
* samba
* system-config-samba


sudo chmod 755 xampp-linux-1.8.2.0-installer.run
sudo ./xampp-linux-1.8.2.0-installer.run
Login: admin / bitnami

sudo /opt/bitnami/ctlscript.sh restart apache

Everything alternative fsearch: 
https://alternativeto.net/software/fsearch/
https://launchpad.net/~christian-boxdoerfer/+archive/ubuntu/fsearch-daily
installed OK. aber wie starten?

alternative: locate Suchbegriff 
https://wiki.ubuntuusers.de/locate/
intallaton ging schnell und bin zufrieden :)
