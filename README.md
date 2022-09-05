Keycloak
========

To get help configuring Keycloak via the CLI, run:

on Linux/Unix:
Need to install java 11:
    $ sudo add-apt-repository ppa:openjdk-r/ppa
    $ sudo apt update 
    $ sudo apt-get install openjdk-11-jre
Need to install ssl url:
    $ mkdir /mnt/cert/
    $ cd /mnt/cert/
    $ openssl genrsa 2048 > host.key
    $ openssl req -new -x509 -nodes -sha256 -days 365 -key host.key -out host.cert
Move source code to opt directory:
    $ mv /opt/keycloak-19.0.1
    $ sudo chmod chmod +x /opt/keycloak-19.0.1

To try Keycloak out in development mode, run: 

on Linux/Unix:

    $ bin/kc.sh start-dev
To try Keycloak out in Production  mode, run:
change host name in conf/keycloak.conf this file: 
    $ export KEYCLOAK_ADMIN=admin
    $ export KEYCLOAK_ADMIN_PASSWORD=Admin@321
    $ bin/kc.sh build
    $ bin/kc.sh start
After the server boots, open https://server-ip:8443  in your web browser. The welcome page will indicate that the server is running.

