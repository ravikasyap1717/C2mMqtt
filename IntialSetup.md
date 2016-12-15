# PlasmaMQTT

To build against the latest C development branch, First, clone the C library repository, checkout the develop branch and build in-place (you don't need to install).

 git clone https://git.eclipse.org/r/paho/org.eclipse.paho.mqtt.c
 cd paho.mqtt.c
 git branch develop
 make
 export LD_LIBRARY_PATH=$PWD/build/output
 cd ..

Then clone the C++ library at the same directory level as the C library, and build the C++ library with the DEVELOP flag set:

 git clone https://git.eclipse.org/r/paho/org.eclipse.paho.mqtt.cpp
 cd paho.mqtt.cpp
 make DEVELOP=1


Then Go C2M Example Folder 

Change ADDRESS in Example with C2M MQTT IP and PORT (127.0.0.1:1883)
 cd Example
 make or  make DEVELOP=1

Run Command :

C2M Subscribe:
	$ ./C2M_Sub

C2M Publish :
	$ ./C2M_Pub

For Linking Library :
 Use export LD_LIBRARY_PATH= "your library location"

For Parmanet linking add library path :
	sudo nano /etc/ld.so.conf.d/libc.conf
	
Add your library path :

/home/ravi/Desktop/paho_mqtt/MQTTCPP/paho.mqtt.c/build/output
/home/ravi/Desktop/paho_mqtt/MQTTCPP/paho.mqtt.cpp/lib

==========================================================
For including file in git
	git clone  https://github.com/ravikasyap1717/C2mMqtt.git 
 git submodule add -b develop https://github.com/eclipse/paho.mqtt.c.git
 git commit -m "paho C library"
 git submodule add -b develop https://github.com/eclipse/paho.mqtt.cpp.git
 git commit -m "paho CPP library"
