# confluence 6.6.0 for docker
* confluence6.6.0
* mysql >= 5.7

docker-compose.yml
```yml
version: '2'
services:
  confluence:
    restart: always
    image: ikerlin/confluence:6.6.0
    ports:
      - 8090:8090
    volumes: 
      - ./confluence_data:/var/atlassian/application-data/confluence
    depends_on:
      - confluence_mysql
    links:
      - confluence_mysql
  confluence_mysql:
      restart: always
      image: mysql:5.7
      ports:
        - "3307:3306"
      volumes:
        - ./mysql:/var/lib/mysql
        - ./mysql_conf.d:/etc/mysql/conf.d
      environment:
        MYSQL_ROOT_PASSWORD: 123456
```