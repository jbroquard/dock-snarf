## snarf/proftpd

[![Test Build Status](https://travis-ci.org/pahoughton/snarf.png)](https://travis-ci.org/pahoughton/snarf)

proftp open docker image

## features

* anonymous ftp
* subnet access

## usage

docker build -t uploader .
sudo chwon -R 21:21 /opt/artifacts
docker run -v /opt/artifacts:/var/ftp uploader
curl -T yourfile ftp://uploader/
curl -o yourfile ftp://uploader/yourfile

## contribute

https://github.com/pahoughton/snarf

## licenses

2019-03-10 (cc) <paul4hough@gmail.com>

[![LICENSE](http://i.creativecommons.org/l/by/4.0/80x15.png)](http://creativecommons.org/licenses/by/4.0/)
