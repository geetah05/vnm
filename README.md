## Virtual Neuro Machine

how to build:
```
docker build -t vnm:latest . 
```

how to start local:
```
docker run --name vnm -p 6080:80 -v C:/vnm:/vnm vnm:latest 
open in browser: http://localhost:6080
```

how to start with perfect screen resolution for VNC Viewer:
```
docker run --name vnm -e RESOLUTION=1920x980 -p 6080:80 -p 5900:5900 -v C:/vnm:/vnm vnm:latest 
open in VNC viewer:  http://localhost:5900

```

how to stop:
```
docker stop vnm
docker rm vnm
```

architecture
- vnm: docker container with singularity and all modifications of application menu based on  https://github.com/fcwu/docker-ubuntu-vnc-desktop
- transparent-singularity: scripts to install neuro-sub-containers, installers are called by application menu entries
- caid: build scripts for neuro-sub-containers, including testing of containers
- neuro-docker: provides recipes for containers