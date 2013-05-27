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
Kemudian copy file shutDown ke dalam folder `/etc/init.d/`:

    cd /home/pi/RasberryPi-autoShutDown
    sudo cp shutDown /etc/init.d/

Setelah itu atur permision dari file shutDown dengan mengitikan perintah berikut ini:

    sudo chmod 775 /etc/init.d/shutDown
    
Kemudian hubungkan GPIO 7 (pin 26) ke rangkaian switch

    3,3V
     |
     |
    --- 
    | |
    | | Resistor 1K Ohm
    | |
    ---
     |
     +----------> GPIO 7 (pin 26)
     |
     + |
       | Tactile Switch
     + |
     |
     |
     |
    ---
    GND
    

Jalankan program shutDown:

    sudo /etc/init.d/shutDown
    
Tekan switch kurang lebih 5-7 detik, maka secara otomatis Raspberry Pi akan shutdown.


AutoRun on StartUp
------------------

*Buka file `rc.local`:

    sudo nano /etc/rc.local
    
Tambahan perintah `bin/bash /etc/init.d/shutDown` sebelum baris terkahir `exit 0`

    ...
    ...
    ...
    `bin/bash /etc/init.d/shutDown`
    
    `exit 0`
