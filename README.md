# Ubuntu shell

## Commands

### clean shell
```
ctrl + L
```

### install .deb files from shell
```
sudo dpkg -i nomefile.deb
```

## Setup ~/.bashrc

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
