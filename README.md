## dock-snarf

[![Test Build Status](https://travis-ci.org/pahoughton/dock-snarf.png)](https://travis-ci.org/pahoughton/dock-snarf)

bandaid artifact repository for ci docker images.

Gitlab's publish release, the prefered method for cd, is introduced in
version 1.11.7.  dock-snarf provides a secure, resilient bandiad
solution for any docker image tool to automantically publish releases
to a well known service.

The implementation exposes the upload service to the default docker
NAT. All images within that NAT have anonymous full access to the ftp
services. The docker host is the only other system that can modify the
artifact repository.

The nginx web server provides unrestricted read access to all
artifacts.

Both the uploader(proftpd) and artifact(nginx) services share the
artifact volume.

## features

anonymous ftp up/down load from local containers
http artifacts http://host/artifacts/cca/maul/agate/agate-0.3.3.amd64.tar.gz

## usage

chown -R 21:21 /opt/artifacts
docker run -v /opt/artifacts:/var/html artifacts
docker run -v /opt/artifacts:/var/ftp uploader

## build
```
cd proftpd && docker build -t uploader .
cd nginx && docker build -t artifacts .
docker --help
```

## puppet deploy

```.pp
class snarf {
    # setup /opt/artifacts filesystem

    docker::run { 'uploader' : }
    docker::run { 'artifacts' : }

}

```
## contribute

https://github.com/pahoughton/dock-snarf

## licenses

2019-03-10 (cc) <paul4hough@gmail.com>

[![LICENSE](http://i.creativecommons.org/l/by/4.0/80x15.png)](http://creativecommons.org/licenses/by/4.0/)
