---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
sudo systemctl start syncthing@jac  
  
sudo systemctl enable syncthing@jac  
  
  
If you have a device with other devices connected and want to connect a third device that you want to give access to that device and the devices it's connected to check introducer  
  
  
  
https://youtu.be/PSx-BkMOPF4



[Unit]  
Description=SyncThing Continuous File Synchronization  
  
[Service]  
ExecStart=/path/to/syncthing  
Restart=always  
User=your_username  
Environment=HOME=/home/your_username  
  
[Install]  
[WantedBy=multi-user.target](http://wantedby%3Dmulti-user.target/)  
  
  
sudo apt update  
sudo apt install syncthing  
syncthing  
clear  
sudo nano /etc/systemd/system/syncthing.service  
sudo systemctl daemon-reload  
sudo systemctl enable syncthing  
sudo systemctl start syncthing