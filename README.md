# FadeCandyServer
Instructions on setting up the fadecandy server on a raspberry pi (any model)

[FadeCandy GitHub](https://github.com/scanlime/fadecandy)

[FadeCandy Server](https://github.com/scanlime/fadecandy/tree/master/server)

Have freshly imaged pi with access to terminal.

Start with
```
sudo apt-get update
sudo apt-get install screen
```


Then in your home directory, type:
```
sudo git clone https://github.com/scanlime/fadecandy
cd /fadecandy/server
sudo make submodules
sudo make
```

When that finishes, you can start the server with 
```
sudo ./fcserver
or 
./fcserver
```

Get your IP address from the Pi
```
ifconfig
```

###Important 

By default the fadecandy server only listens on the local loopback (127.0.0.1:7890)
To be able to reach the fadecandy server from another device on the network, you'll need alter or use a different config file.

```
{
    "listen": [null, 7890],
    "verbose": true,

    "color": {
        "gamma": 2.5,
        "whitepoint": [1.0, 1.0, 1.0]
    },

    "devices": [
        {
            "type": "fadecandy",
            "map": [
                [ 0, 0, 0, 512 ]
            ]
        }
    ]
}
```
The null is the important part here, allowing whatever IP the Pi is given to be used as the server IP. 

More information on Configuration Files can be found [here](https://github.com/scanlime/fadecandy/blob/master/doc/fc_server_config.md).


