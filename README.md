# wp-apache-dev-docker-image
WordPress com Apache, para rápido desenvolvimento.

```
 wordpress:
    image: webfatorial/wp-apache-dev
    environment:
      - DOTENV=false
      - DB_HOST=mysql
      - DB_NAME=wordpress
      - DB_PASSWORD=root
      - DB_USER=root
      - DB_USER_HOST=mysql
      - DB_PREFIX=wp_prefix_
      - DISABLE_WP_CRON=true
      - DOMAIN_CURRENT_SITE=dev.site.com
      - WP_ENV=development
      - WP_HOME=http://dev.site.com
      - WP_SITEURL=http://dev.site.com/wp
    ports:
      - 80:80
    volumes:
      - .:/var/www/html
    command: sh -c "composer install && apache2-foreground"
```
