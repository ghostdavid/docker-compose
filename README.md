# docker-compose模板及个人备份仓库

## 模板
```
services:
    name:
        image: "author/name:latest"
        container_name: name
        restart: always
        environment:
            - PUID=1000 
            - PGID=10 
            - TZ=Asia/Shanghai 
        ports:
            - "3000:3000" 
        network_mode: bridge
        volumes:
            - './config:/config'
            - '/volume1/TV:/media/TV' 
            - '/volume2/Movie:/media/movie'  
```

