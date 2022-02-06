##### Push ssh-key to server
```
ssh-keygent -t dsa -b 2048 -f hostname
ssh-copy-id -i ~/.ssh/hostname.pub user@host
```
##### After reinstallation of ssh on server to remove old keys
```
ssh-keygen -R [server ip]
ssh-keygen -R [server dns]
```
