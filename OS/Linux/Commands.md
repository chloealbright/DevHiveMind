opens file explorer  from terminal 

^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ 

----------------------------------------------------- 

nemo Downloads 

open atom by typing  

atom 

appname filename 

atom file.txt 

or  

file in dir 

atom 'Folder name' /filename 

---------------------------------------------- 

Other terminal commands 

--------------------------------------------  

ls -al 

better 

lsblk 

for drives 

ip a  

get ip  

man  tar 

for manual more detail 

or 

tar --help  

quick references 

like  

ls --help 

man ls 

lspci  

list devices 

lspci | grep VGA 

list gpu 

unzip zipfile 

other 

---------------------- 

cat /etc/apt/sources.list 

ls /etc/apt/sources.list.d/ 

ls /etc/apt/sources.list.d/google-chrome.list 

sudo rm -rf /etc/apt/sources.list.d/team-xbmc-ubuntu-ppa-eoan.list 

apt-cache showpkg timeshift 

sudo dpkg --get-selections > installed-applications.txt 

sudo apt-get -y update 

man apt-get update -y 

sudo dpkg --set-selections < /home/jac/Downloads/my_packages.txt 

sudo apt-get dselect-upgrade 

sudo apt-get -u dselect-upgrade 

CHMOD 

----------------- 

sudo apt-get --purge remove google-play-music-desktop-player 

chmod +x adds the execute permission for all users to the existing permissions. 

chmod 755 sets the 755 permission for a file. 

755 means full permissions for the owner and read and execute permission for others. 

Chmod 755 (chmod a+rwx,g-w,o-w) sets permissions so that, (U)ser / owner can read, can write and can execute. (G)roup can read, can't write and can execute. (O)thers can read, can write and can execute. 

Chmod 757 (chmod a+rwx,g-w) sets permissions so that, (U)ser / owner can read, can write and can execute. (G)roup can read, can't write and can execute. (O)thers can read, can write and can execute. 

chmod +x setdata.sh 

./setdata.sh 

2019-12-15T06:04:28.115-0500 connected to: localhost 

2019-12-15T06:04:28.116-0500 dropping: stockdb.stocks 

2019-12-15T06:04:28.137-0500 imported 142 documents 

https://chmodcommand.com/chmod-777/













go to etc from any location 

pushd /etc 

goes back to directory you came from 

popd  

Run for temp root access 

sudo -s  instead of su 

This lets you switch to another user 

Sudo - username 

This command adds ls output to bottom of txt file but if you use a single ">" 

the content of the file would be overwritten   

ls -al / >> lsoutput.txt 

ls –aR 

command can be used to display all the files including hidden files in your current working directory and all subdirectories of your current working directory 

history |less 

sudo updatedb lets you use locate command 

whatis whatis 

whatis (1)           - display one-line manual page descriptions 

whatis apropos 

whatis locate 

locate fstab 

which firefox  

killall firefox 

wget (1)             - The non-interactive network downloader. 

file .wget-hsts get description on file type 

echo (1)             - display a line of text 

echo $0              $0 is a special parameter in Bash 

lets you know what shell your running 

head filename displays like 10 lines by default 

or head -3 filename only 3 lines 

tails - output the last part of files 

sort long_file.txt  

uniq              - report or omit repeated lines 

grep finds string in file 

grep 'string' filename 

compares to files 

diff my_diff_A.txt my_diff_B.txt 

ls /bin/* 

ls /bin/ls 

mkdir from workspace dir in root folder 

mkdir /root/workspace/cst3523/shells 

mkdir ./cst3523/shells 

mkdir cst3523/shells 

mkdir ~/../../root/workspace/cst3523/shells 

cd cst3523 && mkdir shells 

mkdir ../workspace/cst3523/shells 

adding alias 

echo 'alias' tb="'nc termbin.com" ' >> .bashrc 

installled tcsh in muon 

/bin/tcsh 

  echo $0 

  /bin/tcsh 

  echo $0 

sleep 240 & 

jobs 

sleep 120 

sleep 600 

jobs 

bg 

jobs 

fg 

jobs 

fg than crtl + c to cancel sleep 

jobs 

echo foo 

^foo^bar 

the power sign re-runs the command and replaces the foo with bar 

or sudo apt update 

^update^upgrade 

if there multiple you can change globally 

echo foo bar foo 

usually ^foo^bar this will only change the first foo 

this changes all the foo  

exclamtion point is related to command history 

history than !543 would run that command on the list 

!!  

runs the last command ran 

you could also do 10 commands back 

!-10 

or  

!cd which runs last cd command runed 

same for last ssh command 

!ssh 

same for something like  

!ls 

CTRL+R  in terminal allows you to search through terminal history  

^foo^bar^:& or do fc -s foo=bar 

alternative to head 

sed 1q Downloads/my_diff_A.txt 

tldr ls 

chmod u+x file 

u is user  

a is all