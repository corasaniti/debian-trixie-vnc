## A Debian Trixie  Docker Image with x-server
A Debian Trixie Docker Image with x-server, Openbox, VNC server, SSH server and other package installed
```
pwgen, curl, iputils-ping, lsb-release, screenfetch, fastfetch, exa, nano, xterm
```

#### Build Image From Dockerfile and Run from locally build
```
git clone https://github.com/corasaniti/debian-trixie-vnc.git
cd debian-trixie-vnc
docker build -t debian-trixie-vnc .
docker run -d -it \
	--name trixie-vnc \
	--hostname trixie-vnc \
	-p 5900:5900 -p 22:22 \
	-e SSHPW=choose-password \
	-e RESOLUTION=1024x768 \
	debian-trixie-vnc

```

#### Alternatively Pull and Run Container from Docker Registry
``` 
docker run -d -it -p 22:22 -p 5900:5900 \
	--name trixie-vnc \
	--hostname trixie-vnc \
	-e SSHPW=choose-password \
	-e RESOLUTION=1024x768 \
	corpie/debian-trixie-vnc:latest
                    
```

#### SSH
You can login via ssh with the username root and the password you have chosen.

#### VNC
Choose video resolution such as 1024x768 (for monitors in 4: 3 format) or 1920x1080 for HD monitors and connect via VNC client with username "root" (no password required)
