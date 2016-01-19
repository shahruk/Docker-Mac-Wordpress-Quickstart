### Docker MAC OSX Wordpress Quickstart ###

1. Launch Docker Quickstart Terminal. Note the IP address given to you. Edit your hosts file with `sudo nano /etc/hosts`. Add this to the bottom of your hosts file:

    `<ipaddressfromdockerwithoutbrackets>   mywordpresssite.dev`

2. Navigate to  folder (Must be under /Users/<username> due to boot2docker for Mac restrictions) and run `docker-compose up`
3. Visit **[http://mywordpresssite.dev:8081](http://mywordpresssite.dev:8081)** and login to phpMyAdmin as root/root. Note the IP address at the top for Server. (e.g. Server: **172.17.0.2:3306**). Copy **resources/wp-config-starter.php** to **wordpress/wp-config.php**. Edit wordpress/wp-config.php and set your DB_HOST to that IP.

   `define('DB_HOST', '172.17.0.2:3306')`

4. Visit **[http://mywordpresssite.dev:8080](http://mywordpresssite.dev:8080)**. Wordpress is already installed and working.

-How do I get the latest backup?
Run the WP Migrate DB tool on the Dev server. Use the Docker profile. Import this into phpMyAdmin, or replace resources/mysql/wordpress-starter.sql, stop your docker container, then run docker-compose up.

-How do I delete all my docker instances and start with a fresh copy?
1. `docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)`
2. `docker-compose up`