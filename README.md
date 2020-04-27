# Eramba Community Edition

Copy certificates into `certs` folder.
 * `domain.tld.cert` the public [self]signed certificate.
 * `domain.tld.key` the private key.

Adjust `default-ssl.conf.example` and rename it `default-ssl.conf`, do the same with `database.php.example` and rename it `database.php`. Launch as:

    docker container run --rm -v $(pwd)/certs:/certs -p 80:8080 -p 443:8443 tuxmealux/eramba-community:latest

In oreder to properly work it requires a mariadb backend, you can get everything ready to run [here](https://github.com/staypirate/eramba-grc).