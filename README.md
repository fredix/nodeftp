nodeftp
=======

this is the nodecast ftp server. To use it you need to launch with ncw https://github.com/nodecast/ncw
NCW will connect to your NCS instance, it will receive the new ftp user's accounts and send them to nodeftp


```bash
 ncw --worker-type=service --worker-name=ftp --ncs-ip=NCS_IP --ncs-port=5569 --node-uuid=nodeuuid --node-password=nodepassword --directory=/var/lib/ncs/ftp --stdout=true --exec="nodeftp --base-directory=/var/lib/nodeftp --ftp-server-port=2122"
```

