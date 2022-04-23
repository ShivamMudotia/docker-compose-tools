opencart
========

[OpenCart][1] is designed feature rich, easy to use, search engine
friendly and with a visually appealing interface.

## docker-compose.yml

```yaml
version: "3.8"

services:

  opencart:
    image: vimagick/opencart
    ports:
      - "8000:80"
    volumes:
      - /var/www
    depends_on:
      - mysql
    restart: unless-stopped

  mysql:
    image: mysql
    volumes:
      - ./data:/var/lib/mysql
    environment:
      - MYSQL_ROOT_PASSWORD=root
      - MYSQL_DATABASE=opencart
    restart: unless-stopped
```

[1]: http://www.opencart.com/index.php
