nodeftp
=======

this is the nodecast ftp server. To use it you need to launch with ncw https://github.com/nodecast/ncw
NCW will connect to your NCS instance, it will receive the new ftp user's accounts and send them to nodeftp



## INSTALL

first, install some debs :


```bash
sudo apt-get install g++ make autoconf libboost-all-dev libqt4-dev
```

next, get submodule libraries :

```bash
git submodule update --init
```


make the libqxt library

```bash
cd externals/libqxt
./configure
make
sudo make install
```


make the nodeftp :

```bash
qmake
make
mkdir $HOME/bin
cp nodeftp $HOME/bin
sudo mkdir /var/lib/nodeftp
sudo chown $USER:$USER /var/lib/nodeftp
```

## USE

Create a node with the NCS web interface or the HTTP API ( https://github.com/nodecast/ncs )

and launch the service

```bash
ncw --worker-type=service --worker-name=ftp --ncs-ip=NCS_IP --ncs-port=5569 --node-uuid=nodeuuid --node-password=nodepassword --directory=/var/lib/ncs/ftp --stdout=true --exec="nodeftp --base-directory=/var/lib/nodeftp --ftp-server-port=2121"
```

