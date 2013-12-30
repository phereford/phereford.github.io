---
layout: post
title: "Dogecoin and Ruby"
date: 2013-12-30 06:14:14 -0500
comments: true
categories: [Dogecoin, Ruby]
---

*Note:* If you like this post, please feel free to leave some Doge at DJ2KQgTmKofcUdB2qY2p6pcbaZMcfmh9PU.

In this post, I will just talk about the basics of being able to communicate to
the dogecoin network using Ruby. In order to do this, you must first be able to
compile the [dogecoin source dode](http://github.com/dogecoin/dogecoin). The
repo has instructions mentioning how to compile per operating system. If on debian
you could also reference [How To Compile Doigecoind](http://p.hereford.io/blog/2013/12/27/how-to-compile-dogecoind/).

## Starting out
You need to have the dogecoind daemon running.
```
> ./dogecoind -daemon
```

### Ruby
We are going to use a gem called [bitcoin-client](https://github.com/sinisterchipmunk/bitcoin-client).
After you have installed the gem or included it in your gemfile, it's time to
have some fun in the console. You will need to get the USER and PASS from your
dogecoin.conf file. The arguments are rpcuser and rpcpassword.
```
client = Bitcoin('USER', 'PASS', host: '127.0.0.1', port: 22555)
client.balance # => Balance of user
```

## And that's all folks
That is seriously it! Isn't that awesome! Thank you sinisterchipmunk for your 
awesome gem.

*Note:* If you like this post, please feel free to leave some Doge at DJ2KQgTmKofcUdB2qY2p6pcbaZMcfmh9PU.
