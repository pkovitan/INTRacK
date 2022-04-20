# INTRacK

# Install Node.JS
curl -sL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource_setup.sh
nano /tmp/nodesource_setup.sh
sudo bash /tmp/nodesource_setup.sh
sudo apt install nodejs
node -v
16.14.2

# Install npm
sudo apt install npm
npm -v
8.5.0

# Install Node-Red
sudo npm install -g --unsafe-perm node-red
node-red -v
Node-Red version : v2.2.2
Node.js version : 16.14.2
linux 5.4.0-107-generic x64 LE

# Run on Startup
sudo nano /etc/systemd/system/nodered.service

Write KU
[Unit]
Description=Node-RED
After=syslog.target network.target

[Service]
ExecStart=/usr/bin/node-red --max-old-space-size=128 -v
Restart=on-failure
KillSignal=SIGINT

# log output to syslog as 'node-red'
SyslogIdentifier=node-red
StandardOutput=syslog

# non-root user to run as
WorkingDirectory=/home/korkarn/
User=korkarn
Group=korkarn

# if using a root user
#WorkingDirectory=/root/
#User=root
#Group=root

[Install]
WantedBy=multi-user.target

sudo systemctl enable nodered.service

sudo reboot


# Check NodeRed.Service
sudo systemctl status nodered.service


# Install Mosquitto
$ sudo apt update 
$ sudo apt install -y mosquitto
$ sudo systemctl status mosquitto

Mosquitto V3.1/V3.1.1

