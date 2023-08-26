##### Push ssh-key to server
```
ssh-keygen -t rsa -b 4096 -f hostname (add -o if server support openssh)
ssh-copy-id -i ~/.ssh/hostname.pub user@hostname
```
##### After reinstallation of ssh on server to remove old keys
```
ssh-keygen -R [server ip]
ssh-keygen -R [server dns]
```
