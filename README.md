# docker-compose模板及个人备份仓库

## 新项目模板
```
services:
    name:
        image: "author/name:latest"
        container_name: name
        restart: always
        environment:
            - PUID=1000 
            - PGID=10 
            #- USER_ID=0
            #- GROUP_ID=0
            - TZ=Asia/Shanghai 
        ports:
            - "3000:3000" 
        network_mode: bridge
        volumes:
            - './config:/config'
            - '/volume1/TV:/media/TV' 
            - '/volume2/Movie:/media/movie'  
```

## Clash-verge

```
services:
  clash-verge-rev:
    container_name: clash-verge-rev
    image: ghcr.io/azicen/clash-verge-rev:latest
    environment:
     - PUID=0 
     - PGID=0 
     - TZ=Asia/Shanghai
     - VNC_PORT=5901
     - NOVNC_PORT=6081
     - VNC_GEOMETRY=1920x1080
    volumes:
      - ./config:/config/.local/share/io.github.clash-verge-rev.clash-verge-rev
    ports:
      - "5901:5901"
      - "6081:6081"
      - "7897:7897"
      - "9097:9097"
    restart: always
    network_mode: bridge
```
