# FadeCandyServer
Instructions on setting up the fadecandy server on a raspberry pi (any model)


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




