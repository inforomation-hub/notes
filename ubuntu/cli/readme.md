# General Commands

## Install chromium
```bash
sudo apt install --assume-yes chromium-browser
```

## Find a file
```bash
find /path/ -iname filenam*
# https://vitux.com/how-to-find-files-on-the-ubuntu-command-line/
```

## Install chrome
```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt install ./google-chrome-stable_current_amd64.deb
```


## Virtual display
```bash
DISPLAY=:1 xvfb-run <command>
```

## install nodejs version 14 on ubuntu: ([ref](https://computingforgeeks.com/install-node-js-14-on-ubuntu-debian-linux/))
```bash
sudo apt update
curl -sL https://deb.nodesource.com/setup_14.x | sudo bash -
sudo apt -y install nodejs
```

## redirect output to file: ([ref](https://askubuntu.com/questions/625224/how-to-redirect-stderr-to-a-file))
```bash
# Redirect stdout to one file and stderr to another file:

command > out 2>error

# Redirect stdout to a file (>out), and then redirect stderr to stdout (2>&1):

command >out 2>&1
# Redirect both to a file (this isn't supported by all shells, bash and zsh support it, for example, but sh and ksh do not):
command &> out
```

## kill screen session
```
screen -XS <session-id> quit
```

## Check porcesses running on port
```
sudo lsof -i -P -n | grep LISTEN
```
