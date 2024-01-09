```yaml
version: '3.8'

services:
  service1:
    image: nginx:alpine
    ports:
      - "80:80"
  service2:
    image: alpine

networks:
  mynetwork:
```
```html
<!DOCTYPE html>
<html>
<head>
    <title>The best website ever!</title>
</head>
<body>
    <h1>Welcome to the website!</h1>
</body>
</html>
```
```bash
docker-compose up -d --force-recreate
```
```yaml
version: '3.8'
services:
 service1:
  build: .
  ports:
  - "80:80"
```
```dockerfile
FROM httpd
COPY ./index.html /usr/local/apache2/htdocs/
```
```yaml
version: '3.8'

services:
 api:
 build:
 context: .
 dockerfile: dockerfile_api
 container_name: api
 networks:
 - app

 web:
 build:
 context: .
 dockerfile: dockerfile_web
 ports:
 - "80:80"
 networks:
 - app

networks:
 app:
```
