## Create new service or edit service config
### Create / Open service config file using an editor
```
sudo vim /etc/systemd/system/NodeServer.service
```

### Write / Update configurations for that service
```
[Unit]
Description=My Node Server
After=multi-user.target

[Service]
ExecStart=/usr/bin/node /home/ec2-user/lotr/server.js
Restart=always
RestartSec=10
StandardOutput=syslog
StandardError=syslog
SyslogIdentifier=my-node-server
User=ec2-user
EnvironmentFile=/home/ec2-user/lotr/app.env

[Install]
WantedBy=multi-user.target
```
This [website](https://medium.com/@benmorel/creating-a-linux-service-with-systemd-611b5c8b91d6) might help to get details of some variables

### if created first time then enable it and start it
```
sudo systemctl enable NodeServer.service
sudo systemctl start NodeServer.service
```
### if updating it
```
sudo systemctl daemon-reload
sudo systemctl restart NodeServer.service
```
### to check status
```
sudo systemctl status NodeServer.service
```
### get logs of a service
```
sudo journalctl -u NodeServer.service
# -n <num of lines>
sudo journalctl -u NodeServer.service -n 20
# -f follow
sudo journalctl -u NodeServer.service -n 20 -f
```

