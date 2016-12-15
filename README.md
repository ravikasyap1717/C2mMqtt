# C2mMqtt


cd Desktop
git clone https://github.com/ravikasyap1717/C2mMqtt.git

cd C2mMqtt

git submodule update --init

cd paho.mqtt.c
git checkout develop
make
cd ..

cd paho.mqtt.cpp
make DEVELOP=1
cd ..

cd Example
make

Run Command :

C2M Subscribe:
	$ ./C2M_Sub

C2M Publish :
	$ ./C2M_Pub

sudo nano /etc/ld.so.conf.d/libc.conf
/home/ravi/Desktop/C2mMqtt/paho.mqtt.c/build/output
/home/ravi/Desktop/C2mMqtt/paho.mqtt.cpp/lib
sudo ldconfig
