# Deps

install raspian lite (stretch version not jessie)

after install log in (Default u:pi pw:raspberry)

run ```sudo raspi-config```

go to 5.interfacing options turn on SSH go to yes go to 4.localisation options set local and timezone   then finish

u can now turn off pi screen and ssh in from another computer or continue on the pi its self 

---------------------------------------------------------------------------------------------
first lets set the swap file

start off by ```sudo swapoff -a```

```sudo nano /etc/dphys-swapfile```

change it to ```CONF_SWAPSIZE=1024``` ctrl X then Y then enter

```sudo /etc/init.d/dphys-swapfile stop```

```sudo /etc/init.d/dphys-swapfile start```

now lets install deps

```sudo apt-get update```

```sudo apt-get install qt4-qmake libqt4-dev build-essential libboost-dev -y```

```sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-program-options-dev -y```

```sudo apt-get install libboost-thread-dev libssl-dev libminiupnpc-dev libqrencode-dev git -y```

we need to build the Berkeley DB ourselves

```wget http://download.oracle.com/berkeley-db/db-4.8.30.NC.tar.gz ```

```tar -xzvf db-4.8.30.NC.tar.gz```

```cd db-4.8.30.NC/build_unix/```

```../dist/configure --enable-cxx --disable-shared```

```make```

```sudo make install```

```cd ~```

now for more deps (its better to have them and not need them then to need them and not have them)

```sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3```

```sudo apt-get install software-properties-common```

```sudo apt-get update```

```sudo apt-get install libzmq3-dev```

```sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler```

```sudo apt-get install libboost-all-dev```

```sudo apt-get install libssl1.0```

have fun fixing errors if they arrive - 

Notes: allways check the doc readme in source for unix builds see if your missing any deps
       


