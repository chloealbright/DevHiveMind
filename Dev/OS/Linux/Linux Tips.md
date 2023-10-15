use snap or flathub to get the latest version of software especially for the non-rolling release of Linux deb are essentially an older version of the software for stability 

Linux Wifi 

--------------------- 

Need to keep clamv database updated to connect to the internet but firewall can block updates so disable first than re-enable  

wine 

--------- 

winehq-staging: this is the most recent testing wine version. 

ppa 

------ 

dont use ppa not needed most of the times 

 Avoid updating kernel unless you have hardware issues 

On arch update once A week and make a backup 

PPA is for getting updates before reaching software store 

research PPA sources to make sure there trusted 

When making Debian Distrito flash drive with Rufus use dd not recommend option 

pop os Wayland is for touch screens 

uefi on Linux can be a problem and in general'





## Linux Commands and tips 

list hidden files in terminal - ls –a 

mount iso - sudo mount /dev/cdrom /mnt 

IP Address – ifconfig 

Terminal control for audio - type in terminal alsamixer 

fix the screen rotation in Ubuntu using terminal 

xrandr -o normal 

bang bang command !!  the command is a shortcut to repeat the previous command you entered in your terminal. example sudo !! 

[https://winaero.com/find-files-linux-terminal/](https://winaero.com/find-files-linux-terminal/)  

bin directory is for system programs not personal ones 

.desktop files go here - /home/jac/.local/share/applications/ 

Dolphin services-  /home/jac/.local/share/kservices5/ServiceMenus 

icon location- /home/jac/.local/share/icons 

-------------------------------------change password----------------------- 

suod -s  

passwd jac 

-------------------------------------permissions----------------------- 

chmod options mode filename 

options: -R (recursive- meaning the same permissions will be applied to the subfolders and files ), -f (force the mode you pick even if there are error messages), -v (verbose output a diagnostic for every file processed) 

mode:  read(r), write(w), execute(x) 

chmod a+rwx file-A  - a is for all user to get rwx 

ls -l 

User: Owner,Group,Other=  example of permission dwx(d21)d is directory -rw(-41) "-" a file  r(4) w(2) x(1) 

chmod command example- chmod -R 774 filename each number correlates to the three user   

7 is all three permission combined 6 is rw 5 is rx and 3 is wx and you could just use each individual number to give one permission like r(4) w(2) x(1) 

Symbolic method 

chmod references + mode filename 

references: u(owner of file),g( group members of  file)  o(other user)  a(ugo all references) 

chmod u+x some file will grant only the owner of that file execution permissions whereas chmod +x some file is the same as chmod a+x some file. 

operator: +(adds mode to specific user) -(removes mode from user) = (exact mode to user example u=o now owner and other has same permissions) 

mode:  read(r), write(w), execute(x) 

groups username - to list group 

[http://www.yolinux.com/TUTORIALS/LinuxTutorialManagingGroups.html](http://www.yolinux.com/TUTORIALS/LinuxTutorialManagingGroups.html)  

--------------------------------------------------Extraction------------------- 

[https://help.ubuntu.com/community/BackupYourSystem/TAR](https://help.ubuntu.com/community/BackupYourSystem/TAR)  

Move to directory you want to install from 

xf is for extracting  

sudo tar -xvzf ~/Downloads/ideaIC-2019.1.3.tar.gz 

sudo tar -xf ~/Downloads/flutter_linux_v1.5.4-hotfix.2-stable.tar.xz 

Nano ~/desktop/file.txt  don't need to change directory creates file in the specified location  which is desktop without changing to the directory 

extracting a JAR file: To extract the files from a .jar file , we can use:    jar xf jarfilename 

------------File Management------------------------------------------ 

before copying or moving a dir you need to mkdir first then cp -r or mv -r or replace -r with -f if you encounter a problem 

mv move file dir 

mv -r filedirectory/ newfiledirectorypath/ 

Copy file with other files use cp -r filedirectory/ newfiledirectorypath/ 

also same is probably true when moving files 

To rename file is the same process just use  mv oldfile.txt newfilename.txt 

Move up a directory and rename 

mv oldfile.txt ../newfilename.txt 

           mv oldfiledir/ ../upnewfiledir 

removing file in terminal deletes forever 

The touch command is the easiest way to create new, empty files. It is also used to change the timestamps 

touch filename 

open filename to open file 

----------------------- source command---------------------------- 

source ~/filename is the same as 

"./ filename" is the same as "source filename"  

so just use "./ filename" 

or sh file  

sh ./ filename 

Linux Command help-  curl cheat.sh 

---------------------------------------------------Bashrc----------------------- 

.bashrc  is basically system shell where you can add paths for other shells to run when you launch terminal or add paths that make it possible to run certain shells also you can add alias like 

alias ls='ls --color=auto -l' 

which makes commands like ls run ls -l instead  

------------------------------------------packages---------------------------- 

dpkg –list 

sudo apt-get --purge remove gimp  

sudo apt-get remove gimp 

sudo apt-get autoremove 

sudo apt-get clean                                                 

clears out the local repository of retrieved package files.It removes everything but the lock file from /var/cache/apt/archives/ and /var/cache/apt/archives/partial/. 

// gimp is example If you don’t want to remove the configuration files, simply leave out the “--purge” command, as shown in the following command. 

// As discussed in this article, programs installed in Linux depend on other packages to function. When you uninstall a program, there may be packages that the uninstalled program depended upon that are no longer used. To remove any unused packages, use the “autoremove” command, as shown in the following command. 

If you’re short on space, you can use the “clean” command to remove downloaded archive files, as shown below. 

list of packages installed locally. 

dpkg --get-selections | grep -v deinstall 

save that list of installed packages on your desktop 

dpkg --get-selections | grep -v deinstall > ~/Desktop/packages 

will generate a list of installed applications in txt file 

sudo dpkg --get-selections > installed-applications.txt 

command will give you a list of manually installed packages 

apt-mark showmanual 

backup of packages currently installed by using following command. 

dpkg --get-selections > list.txt 

sudo dpkg --get-selections "*" >/home/jac/Documents/my_packages.txt 

sudo dpkg --set-selections < /media/disk/my_packages.txt 

sudo apt-get -u dselect-upgrade