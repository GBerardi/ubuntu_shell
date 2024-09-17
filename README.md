# Ubuntu shell

## Content
- [clean shell](#clean-shell)
- [ls for big folders](#ls-for-big-folders)
- [install deb files](#install-deb-files-from-shell)
- [ssh tunnel](#ssh-tunnel)
- [setup bashrc](#setup-bashrc)
- [space checks](#space-checks)

## Commands

### clean shell
```
ctrl + L
```

### ls for big folders
```
# ls without order, first 10 elements
ls -U | head -10
```

### install deb files from shell
```
sudo dpkg -i nomefile.deb
```

### ssh tunnel
```
# example: you start a tensorboard on pincopallo remote server and on port remoteport, you can't access it
# from your local machine but you can access it with ssh from your local machine, you can do a forward to
# make the service on pincopallo:remoteport available at 127.0.0.1:6006 from local browser
ssh gberardi@pincopallo -N -f -L localport:127.0.0.1:remote_port
```

### space checks

check folders space
```
# options: -h human readable, -s no subfolders
du -sh <folder-name>
```

check disks space
```
df -h
```

## Setup bashrc

### 1) define an alias in ~/.bashrc
Venv activation
```
alias script1='source /home/gberardi/dev/venv-name/.venv-name/bin/activate'
```

### 2) define a function in ~/.bashrc (callable from shell)
Port forwarding (local tensorboard from remote), $1 and $2 are local and remote ports
```
tunnel(){
        ssh "username@server" "-N" "-f" "-L" "$1:127.0.0.1:$2"
}
```
