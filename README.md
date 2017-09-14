[![Layers](https://images.microbadger.com/badges/image/roelbindels/php-cron.svg)](https://microbadger.com/images/roelbindels/php-cron "Get your own image badge on microbadger.com") [![Docker Pulls](https://img.shields.io/docker/pulls/roelbindels/php-cron.svg)](https://hub.docker.com/r/roelbindels/php-cron/)

#  Docker PHP Cron Image
Docker Hub: https://hub.docker.com/r/roelbindels/php-cron

Docker containers to run php applications triggered by a cron job with a specific version of PHP (5.3 -> 7.2) installed
with main PHP extensions (curl, pdo, gd, etc ....) as well as XDebug.

It's mainly made for development purposes but can also be used as Production.

The aim of these containers is to be used with docker-compose and especially with
[our Stakkr Stack](https://github.com/edyan/stakkr).

## Usage
Add the following plugin to your stakkr environment:
```yaml
$ cd plugins/
$ git clone https://github.com/inetprocess/stakkr-phpcron.git phpcron
$ stakkr refresh-plugins
$ cd ..
```

## PHP version
To use a specific PHP version, append the version number to the image name.

Eg: `image: roelbindels/phpcron:5.6`

The following PHP versions are available:

* PHP 7.2 (stretch slim + sury packages)
* PHP 7.1 (stretch slim + sury packages)
* PHP 7.0 (stretch slim)
* PHP 5.6 (jessie slim)
* PHP 5.5 (wheezy slim)
* PHP 5.4 (wheezy slim)
* PHP 5.3 (squeeze stable)

## Other Specific versions
### edyan/5.6-git
That's exactly the same container than the 5.6 + `git` and `openssh-client` installed.
Useful for Continuous integration with Gitlab.


### edyan/5.6-libreoffice
That's exactly the same container than the 5.6 + the packages git and libreoffice 5 installed.
We use it for internal purpose, when we need to test tools with libreoffice (Generate PDF for instance)
