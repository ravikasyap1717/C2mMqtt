# C2mMqtt

This is independnt c and c++ Paho Mqtt library to build C2M Mqtt Example.
In this no need to presinstall any library.Paho c++ library is depend on paho c library or it is a wrapper of paho c Mqtt.
So, for use for Paho Mqtt CPP library, We need to object file of MQTT C and CPP.
For that I am compiling the Source code of Paho C C++ Mqtt Socuce file and Keeping all object file in a folder.
and for compiling C2M soucrce code,we have to link with that C,C++ MQTT Object code.

Clone this Url :
	
	git clone https://github.com/ravikasyap1717/C2mMqtt.git

Move this Specific Folder :

	cd C2mMqtt
subclone for C and CPP Paho MQTT Source code :

	git submodule update --init

Move in PAHO C and C++ Folder and check Branch develop

	cd paho.mqtt.c
	git checkout develop

compile source code to generate object code :

	make
	cd ..
	
Do same in PAHO C++

	cd paho.mqtt.cpp

	make DEVELOP=1

	cd ..

Run C2M Example :

	cd Example
	make

Run Command :

C2M Subscribe:

	$ ./C2M_Sub

C2M Publish :

	$ ./C2M_Pub

for linking the library,set your object file location in this location :

	sudo nano /etc/ld.so.conf.d/libc.conf
	
	like :
	
	/home/ravi/Desktop/C2mMqtt/paho.mqtt.c/build/output

	/home/ravi/Desktop/C2mMqtt/paho.mqtt.cpp/lib

run ldconfig :

	sudo ldconfig
