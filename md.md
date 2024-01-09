```bash
docker volume create volume
```
```bash
docker volume ls
```
```bash
docker run --name hello-world -v volume:/usr/share/nginx/html -p 8080:80 nginx:alpine
```
```bash
docker ps
```
```bash
docker cp index.html hello-world:/usr/share/nginx/html
```
```bash
docker rm -f hello-world
```
