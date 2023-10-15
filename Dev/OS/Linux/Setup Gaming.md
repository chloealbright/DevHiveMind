```bash
sudo aptitude install dxvk lutris 

sudo aptitude -y install lutris 

Wine Install  

sudo dpkg --add-architecture i386  

wget -nc [https://dl.winehq.org/wine-builds/winehq.key](https://dl.winehq.org/wine-builds/winehq.key) 

sudo apt-key add winehq.key 

sudo apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ bionic main' 

sudo aptitude update 

sudo apt install --install-recommends winehq-stable 

sudo aptitude install libgnutls30:i386 libldap-2.4-2:i386 libgpg-error0:i386 libxml2:i386 libasound2-plugins:i386 libsdl2-2.0-0:i386 libfreetype6:i386 libdbus-1-3:i386 libsqlite3-0:i386 

install game mode 

sudo aptitude install  gamemode 

Open lutris app 

click on lutris icon in left corner and go to preferences then system options 

add environmental variables to enable game mode 

first go to terminal type: 

find /usr -iname libgamemode* 

copy third line that looks like this -  /usr/lib/x86_64-linux-gnu/libgamemodeauto.so.0 in environmental variables add the key  LD_PRELOAD and paste the value in which is /usr/lib/x86_64-linux-gnu/libgamemodeauto.so.0 (try crtl + v to paste if you cant paste by mouse) also backspace special character  

Gpu optimization: [https://github.com/lutris/lutris/wiki/Performance-Tweaks](https://github.com/lutris/lutris/wiki/Performance-Tweaks) 

Depending on gpu paste the given key which is in bold and paste the value in the environmental variables then save 

AMD Gpu: key - mesa_glthread value - true 

Nvidia Gpu: key -  __GL_THREADED_OPTIMIZATION value - 1 Next key - __GL_SHADER_CACHE and the value – 1 

Esync setup  

[https://github.com/lutris/lutris/wiki/How-to:-Esync](https://github.com/lutris/lutris/wiki/How-to:-Esync)  

in terminal - ulimit -Hn  to check if eysnc is enabled 

then edit 

sudo nano  /etc/systemd/system.conf  

sudo nano /etc/systemd/user.conf  

sudo nano /etc/security/limits.conf 

with vi command or nano(easier) while you are admin and add this line or un-comment it if it already exist DefaultLimitNOFILE=524288 

then reboot and check if enabled with  - ulimit -Hn   

Drivers try especially for amd 

[https://github.com/lutris/lutris/wiki/Installing-drivers](https://github.com/lutris/lutris/wiki/Installing-drivers)
```