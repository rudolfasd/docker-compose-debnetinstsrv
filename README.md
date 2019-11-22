# docker-compose-debnetinstsrv
Coompose designed for network installation of Debian.
Was used to install Buster hosts.


## Pre run
`cd /<somedir>`

`git clone https://github.com/rudolfasd/docker-compose-debnetinstsrv.git`

`cd ./docker-compose-debnetinstsrv`

`wget http://http.us.debian.org/debian/dists/buster/main/installer-amd64/current/images/netboot/netboot.tar.gz -O /tmp/netboot.tar.gz`<br>

`tar zxvf /tmp/netboot.tar.gz -C $(pwd)/tftp`

`for f in src/tftp/debian-installer/amd64/boot-screens/\*.modified; do cp "$f" "${f%%.modified}";done`

`cd ./src/tftp && ln -s debian-installer/amd64/bootnetx64.efi bootnetx64.efi && cd ../..`

## Run
`docker-compose up --build`
