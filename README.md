RaspberryPi-autoShutDown
========================


Software pendukung
------------------
* Pastikan pada Raspberry Pi sudah terdapat library WiringPi.
* Jika belum, dapat ikuti instalasi library WiringPi melalui link berikut ini  
[wiringPi](http://wiringpi.com/download-and-install/)

Setelah proses instalasi library selesai, secara default library WiringPi ada di 
`/home/pi/wiringPi/`


Download and Install
--------------------
`git clone git://github.com/InnovativeElectronics/RaspberryPi-autoShutDown.git`

Setelah proses download selesai, maka di lokasi `/home/pi/` terdapat folder `RasberryPi-autoShutDown`.
Kemudian copy file shutDown ke dalam folder `/etc/init.d/` :

  cd /home/pi/RasberryPi-autoShutDown
  sudo cp shutDown /etc/init.d/



