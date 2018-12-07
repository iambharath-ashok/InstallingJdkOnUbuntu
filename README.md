# Installing Jdk On Ubuntu

How to install Jdk on Ubuntu

1. OpenJdk
	-  	To install latest open jdk in the ubuntu host
		
		
			sudo apt install default-jre
			sudo apt-get install default-jdk
		
			javac -version
			java -version
			
	-	Installing Specific version of OpenJdk
	
			sudo apt install openjdk-8-jdk
			
	-	Installing Jdk 10/11

		sudo apt install openjdk-11-jdk
		
		apt-cache search jdk
		
		export JAVA_HOME=/usr/lib/jvm/java-8-openjdk
		export PATH=$PATH:$JAVA_HOME/bin
		
			
	
2.	Oracle Jdk

	-  Installing Oracle Jdk 8 on the Ubuntu Host

			sudo add-apt-repository ppa:webupd8team/java
				 
			sudo apt-get update
			
			sudo apt-get install oracle-java8-installer
			
			sudo apt-get install oracle-java8-set-default
			
			java -version
	
	- 	Installing Oracle Jdk 7 	

			sudo add-apt-repository ppa:webupd8team/java
			
			sudo apt-get update
			
			sudo apt-get install oracle-java7-installer


3.	Managing Java

	- 	We can have multiple versions of java installed on one server
	-	We can which one to use as default by command line using update-alternatives
		
		sudo update-alternatives --config java 
		
			-	will list the java intalled on the host
			
		sudo update-alternatives --config javac


4.	Setting JAVA_HOME


	- 	Edit /etc/enviroment file
			sudo nano /etc/environment
	
	-	At the end of the file add a new line 
	
			JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64/bin/"
		
	-	Reload the /etc/enviroment file 

			source /etc/enviroment
			
			echo $JAVA_HOME
			
	
5.	Setting default Jdk Manually with advanced

	- 	Add the following System variable at the end of /etc/profile
	
	-	sudo nano /etc/profile
	
			Press Control+C to enter into command mode
			Press ^+X to Exit
			Press "Y" to save the changes
	- 	Reload the profile
			
			. /etc/profle
			
	-	Letting Ubuntu know where our JDK/JRE is located
	
		sudo update-alternatives --install "/usr/bin/java" "java" "<Directory where JAVA has been extracted>/bin/java" 1
		sudo update-alternatives --install "/usr/bin/javac" "javac" "<Directory where JAVA has been extracted>/bin/javac" 1
		sudo update-alternatives --install "/usr/bin/javaws" "javaws" "<Directory where JAVA has been extracted>/bin/javaws" 1
			
			
	- 	 Telling Ubuntu that our installation i.e., jdk1.8.0_05 must be the default Java.		
		
		sudo update-alternatives --set java <Directory where JAVA has been extracted>/bin/java
		sudo update-alternatives --set javac <Directory where JAVA has been extracted>/bin/javac
		sudo update-alternatives --set javaws <Directory where JAVA has been extracted>/bin/javaws
			
	
		java -version
			
		
