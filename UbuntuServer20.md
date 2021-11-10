
Install latest version of nodejs
source https://github.com/nodesource/distributions/blob/master/README.md
Alternative with nvm source https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04


```sh
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt-get install -y nodejs
```

To run file as service. Example for ProgramName, ProgramName.service  
Copy the file to /etc/systemd/system  
source https://www.shubhamdipt.com/blog/how-to-create-a-systemd-service-in-linux/
Settings can be found https://www.freedesktop.org/software/systemd/man/systemd.service.html

    [Unit]
    Description=ProgramName
     
    [Service]
    ExecStart=node /opt/ProgramName/ProgramName.js
    Restart=always
    User=nobody
    # Note Debian/Ubuntu uses 'nogroup', RHEL/Fedora uses 'nobody'
    Group=nogroup
    Environment=PATH=/usr/bin:/usr/local/bin
    Environment=NODE_ENV=production
    WorkingDirectory=/opt/ProgramName/
    
    [Install]
    WantedBy=multi-user.target

Reload the service files to include the new service.
```sh
sudo systemctl daemon-reload
```

Start your service
```sh
sudo systemctl start your-service.service
```
To check the status of your service
```sh
sudo systemctl status example.service
```
To enable your service on every reboot
```sh
sudo systemctl enable example.service
```

To disable your service on every reboot
```sh
sudo systemctl disable example.service
```
