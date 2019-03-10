# 2019-03-10 (cc) <paul4hough@gmail.com>
from alpine:3.9

label maintainer="<paul4hough@gmail.com>"

env PROFTP_VERSION 1.3.6

run true \
	&& apk add --no-cache --virtual .build-deps \
		gcc \
		libc-dev \
		make \
		openssl-dev \
		curl \
	&& curl -sfSL https://github.com/proftpd/proftpd/archive/v$PROFTP_VERSION.tar.gz -o proftpd.tar.gz \
	&& mkdir -p /usr/src \
	&& tar -zxC /usr/src -f proftpd.tar.gz \
	&& rm proftpd.tar.gz \
	&& cd /usr/src/proftpd-$PROFTP_VERSION \
	&& ./configure \
	&& make install \
	&& rm -rf /usr/src/proftpd-$PROFTP_VERSION

copy proftpd.conf /usr/local/etc/proftpd.conf

cmd ["proftpd","-n","-DANONYMOUS_FTP" ]
