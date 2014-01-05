# A Simple Script for Starting and Stopping Apache and MySQL on *buntu

This is a simple wrapper to control Apache and MySQL on my development machine.

Installing LAMP for *buntu using apt-get is easy:

    sudo apt-get install lamp-server^

## Preventing Apache and MySQL from initializing on startup

These steps are taken from:

  http://www.techytalk.info/configure-mysql-not-to-start-at-boot-ubuntu-linux/

1. First remove Apache from startup

    sudo update-rc.d -f apache2 remove

2. MySQL just a little more effort. Edit the mysql.conf file:

    gksudo sublime /etc/init/mysql.conf

And comment out any lines that have 'start on', for example:

    start on runlevel [2345]

Finally, to use this script make it executable, and move it to a universal
location:

    chmod +x lamp
    sudo mv lamp /usr/bin/lamp
