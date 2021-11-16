<pre>version: "3.5"
services:
  wildfly1:
    build:
        context: .
        args:
          WILDFLY_NAME: wildfly_1
          CLUSTER_PW: secret_password
    image: wildfly_1
    ports:
    - 8082:8080
    networks:
      wildfly_network:
  wildfly2:
    build:
        context: .
        args:
          WILDFLY_NAME: wildfly_2
          CLUSTER_PW: secret_password
    image: wildfly_2
    ports:
    - 8083:8080
    networks:
      wildfly_network:
  wildfly3:
    build:
        context: .
        args:
          WILDFLY_NAME: wildfly_3
          CLUSTER_PW: secret_password
    image: wildfly_3
    ports:
    - 8084:8080
    networks:
      wildfly_network:
  www:
    build: www/.
    ports:
        - "80:80"
    volumes:
        - ./www:/var/www/html
    links:
        - db
    networks:
        - default
  db:
    image: mysql:8.0
    ports:
        - "3306:3306"
    command: --default-authentication-plugin=mysql_native_password
    environment:
        MYSQL_DATABASE: dbname
        MYSQL_USER: admin
        MYSQL_PASSWORD: test
        MYSQL_ROOT_PASSWORD: test
    volumes:
        - ./dump:/docker-entrypoint-initdb.d
        - ./conf:/etc/mysql/conf.d
        - persistent:/var/lib/mysql
    networks:
        - default
  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    links:
        - db:db
    ports:
        - 8000:80
    environment:
        MYSQL_USER: admin
        MYSQL_PASSWORD: test
        MYSQL_ROOT_PASSWORD: test
volumes:
  persistent:


networks:
  wildfly_network:
    ipam:
      driver: default

      </pre>
