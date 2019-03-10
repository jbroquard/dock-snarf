## snarf-dock

[![Test Build Status](https://travis-ci.org/pahoughton/snarf-dock.png)](https://travis-ci.org/pahoughton/snarf-dock)

docker image with proftp and nginx.

## features

anonymous ftp up/down load from local containers
http artifacts http://host/artifacts/cca/maul/agate/agate-0.3.3.amd64.tar.gz

## usage

docker run -v snarf:/opt/snarf snarf

### recommended
#### http://github.com/pahoughton/voldr-dock
docker run -v snarf:/opt/snarf -name snarf-voldr voldr
#### http://github.com/pahoughton/http-mirror-dock
docker run -v snarf:/opt/snarf -name snarf-mirror http-mirror

## contribute

https://github.com/pahoughton/snarf-dock

## licenses

2019-03-10 (cc) <paul4hough@gmail.com>

[![LICENSE](http://i.creativecommons.org/l/by/4.0/80x15.png)](http://creativecommons.org/licenses/by/4.0/)
