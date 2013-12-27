---
layout: post
title: "How To Comple Dogecoind"
date: 2013-12-27 05:53
comments: true
sharing: true
published: true
categories:  [Dogecoin, Mining]
---
*Note:*
If you enjoyed this article, please send me some Doge at DJ2KQgTmKofcUdB2qY2p6pcbaZMcfmh9PU

I had many failed attempts at compiling dogecoind on ubuntu. I really like
ubuntu butit just wouldn't work to compile dogecoind. Instead, I went to degian
7.0 32-bit. After switcthing to this specific environment, I ran the following commands:

## Setting up the Debian environment with the required dependencies
```
sudo su root # You have to ssh as admin
apt-get update
apt-get upgrade
apt-get install ntp git build-essential libssl-dev libdb-dev libdb++-dev libboost-all-dev libqrencode-dev

wget http://miniupnp.free.fr/files/download.php?file=miniupnpc-1.8.tar.gz
tar -zxf download.php\?file\=miniupnpc-1.8.tar.gz
cd miniupnpc-1.8/
make
make install
cd ..
rm -rf miniupnpc-1.8 download.php\?file\=miniupnpc-1.8.tar.gz
```

## Downloading dogecoin from github and compile it
```
git clone https://github.com/dogecoin/dogecoin

cd dogecoin/src
make -f makefile.unix USE_UPNP=1 USE_QRCODE=1
strip dogecoind
```

## To run the process
```
./dogecoind # This should error and give you a username and password to put into dogecoin.conf

vi ~/.dogecoin/dogecoin.conf

# If you aren't familiar with vi, press a for append. Then paste the following
daemon=1
rpcuser=<USER GIVEN>
rpcpassword=<PASS GIVEN>
# Press escape, then :wq, enter. This will save and exit

./dogecoind
```

## For the lazy
Here is an ami id to an amazon AMI I made that just has dogecoind compiled: ```ami-66447723```
*Edit:* Having issues publishing my AMI. Will work on that.

*Note:* When you ssh into an instance with this ami, you will need to use the
admin user and not the root user. I didn't realize this since I use Ubuntu the
majority of the time.
here.
  
## Addendum
I didn't create this AMI using best practices. Your dogecoind process should be
run by someone else other than root or admin.

*Note:* If you enjoyed this post, feel free to send some Doge to: DJ2KQgTmKofcUdB2qY2p6pcbaZMcfmh9PU
