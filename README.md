# Eramba Community Edition

Copy certificates into `certs` folder.
 * `domain.tld.cert` the public [self]signed certificate.
 * `domain.tld.key` the private key.
 * Copy the archived enterprise sources as `./enterprise/eramba_latest.tgz`

Adjust `default-ssl.conf` and `database.php` with your data. Launch as:

    docker container run \
            -v $(pwd)/default-ssl.conf:/etc/apache2/sites-enabled/default-ssl.conf \
            -v $(pwd)/database.php:/var/www/html/app/Config/database.php \
            -v $(pwd)/certs:/certs \
            -p 80:8080 \
            -p 443:8443 \
        tuxmealux/eramba-community:latest

In oreder to properly work it requires a mariadb backend (which is not present), you can get everything ready to run using this [docker-compose](https://github.com/staypirate/eramba-grc/tree/enterprise) file.