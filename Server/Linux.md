# Linux

Restart Server
`sudo service apache2 restart`

Time zone:
`sudo dpkg-reconfigure tzdata`

Create a group and add users

```
Sudo groupadd [group name]
sudo usermod -g [group name] [user name]
```

Change password
`Passwd [username]`

Create user
`Useradd -G [group name] -d [home directory] [username]`

Give usergroup sudo powers

```
Sudo visudo
%[usergroup]  (tab)ALL=(ALL:ALL) ALL
```

Use these in the folder

```
sudo chgrp -R [Group name] .
Sudo chmod -R 775 .  
```

Pulls permissions for files
`Ls -l `

Server IP address
`ifconfig eth0 | grep inet | awk ‘{ print $2 }’`

Set home directory
`sudo usermod -d [path] -m [username]`

List all users
`cat /etc/passwd | cut -d: -f1`

OS Version
`lsb_release -a`

Install Screen
`yum install screen`

Access Mysql
`Mysql -u [username] -p`
this prompts for you to enter in the password
