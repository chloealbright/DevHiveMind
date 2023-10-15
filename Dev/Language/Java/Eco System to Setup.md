Spring boot  
  
  
- Run tests  
- Create an executable JAR file  
- Run the JAR file with Gradle/Maven  
  
  
  
FXML  
setup paths  
Maven  
Gradle  
JAVA  
setup docker  
JDK environment variable v 11  
  
Set up Apache tomcat





	can install these instead from deb  
	sudo apt-get install default-jdk  
	  
	sudo apt install openjdk-8-jdk  
	  
	sudo apt install openjdk-11-jdk  
	sudo apt install openjdk-19-jdk  
	  
	  
	sudo apt install gradle  
	  
	  
	  
	  
	for maven & gradle download extract mv to opt chown -R  
	  
	sudo chown -R $USER:$USER /opt/javafx-sdk-19  
	  
	  
	jenv  
	echo 'export PATH="$HOME/.jenv/bin:$PATH"' >> ~/.bashrc  
	$ echo 'eval "$(jenv init -)"' >> ~/.bashrc  
	  
	  
	javafx vm agrugment  
	--module-path /opt/javafx-sdk-19/lib --add-modules=javafx.controls,javafx.fxml  
	  
	  
	wget [https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.70/bin/apache-tomcat-9.0.70.tar.gz](https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.70/bin/apache-tomcat-9.0.70.tar.gz)  
	  
	tar -zxf apache-tomcat-9.0.70.tar.gz  
	sudo mv apache-tomcat-9.0.70/ /opt/  
	sudo chown -R $USER:$USER /opt/apache-tomcat-9.0.70/  
	cd /opt/apache-tomcat-9.0.70/conf && sudo nano tomcat-users.xml  
	  
	cd .. /bin && ./[startup.sh](http://startup.sh/)  
	firefox localhost:8080  
	  
	  
	or  
	  
	sudo apt install tomcat9 tomcat9-admin  
	sudo systemctl enable tomcat9  
	sudo ufw allow from any to any port 8080 proto tcp  
	firefox localhost:8080  
	  
	firefox 127.0.0.1:8080

# Tomcat setup

sudo wget  [https://downloads.apache.org/tomcat/tomcat-8/v8.5.57/bin/apache-tomcat-8.5.57.tar.gz](https://downloads.apache.org/tomcat/tomcat-8/v8.5.57/bin/apache-tomcat-8.5.57.tar.gz)

sudo wget archive.apache.org/dist/tomcat/tomcat-8/v8.0.9/bin/apache-tomcat-8.0.9.tar.gz

wget [http://www-eu.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz](http://www-eu.apache.org/dist/tomcat/tomcat-9/v9.0.10/bin/apache-tomcat-9.0.10.tar.gz)

wget [https://downloads.apache.org/tomcat/tomcat-9/v9.0.37/bin/apache-tomcat-9.0.37.tar.gz](https://downloads.apache.org/tomcat/tomcat-9/v9.0.37/bin/apache-tomcat-9.0.37.tar.gz)

sudo tar xzvf apache-tomcat-9*tar.gz -C /opt/tomcat --strip-components=1