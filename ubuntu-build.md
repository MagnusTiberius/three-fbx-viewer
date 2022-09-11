howto: setup environment in ubuntu

1. sudo adduser three
2. sudo adduser three sudo
3. mkdir src
4. cd src
5. git clone https://github.com/MagnusTiberius/three-fbx-viewer
6. cd ~
7. sudo nano ~/runtree.sh

#!/bin/bash
cd ~/src/three-fbx-viewer
pwd
npm run dev


8. sudo nano /etc/systemd/system/runthree.service

[Unit]
Description=example systemd service unit file.
After=syslog.target network.target

[Service]
Type=simple
Restart=always
RestartSec=1
ExecStart=/bin/bash /home/three/runthree.sh
User=three

[Install]
WantedBy=multi-user.target


9. sudo systemctl daemon-reload
10. sudo systemctl start runthree.service
11. sudo systemctl enable runthree.service
12. sudo systemctl status runthree.service
