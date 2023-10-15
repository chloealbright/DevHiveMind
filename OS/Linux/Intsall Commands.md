	sudo apt install cmake



	sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg [https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg](https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg)  
	  
	echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg arch=amd64] [https://brave-browser-apt-release.s3.brave.com/](https://brave-browser-apt-release.s3.brave.com/) stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list  
	  
	sudo apt update  
	  
	sudo apt install brave-browser


wget -qO- [https://repo.vivaldi.com/archive/linux_signing_key.pub](https://repo.vivaldi.com/archive/linux_signing_key.pub) | gpg --dearmor | sudo dd of=/usr/share/keyrings/vivaldi-browser.gpg  
  
  
  
echo "deb [signed-by=/usr/share/keyrings/vivaldi-browser.gpg arch=$(dpkg --print-architecture)] [https://repo.vivaldi.com/archive/deb/](https://repo.vivaldi.com/archive/deb/) stable main" | sudo dd of=/etc/apt/sources.list.d/vivaldi-archive.list  
  
  
sudo apt update && sudo apt install vivaldi-stable



