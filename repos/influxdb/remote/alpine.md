## `influxdb:alpine`

```console
$ docker pull influxdb@sha256:a15d2082eb02e88087b95ef7131766ad70a4dd3d3d653eaa7069fc369cde41ab
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `influxdb:alpine` - linux; amd64

```console
$ docker pull influxdb@sha256:be6ff2d6c62504be7f083d814265b8696e7099964b2e92ccd59207a968e6d7b0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **24.5 MB (24543558 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ba40ae935c32c21458c8d32c4cefa05a3abfe7faac3d185255f5e12e4b51f04`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["influxd"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:38 GMT
ADD file:6edc55fb54ec9fc3658c8f5176a70e792103a516154442f94fed8e0290e4960e in / 
# Tue, 09 Jan 2018 21:10:38 GMT
CMD ["/bin/sh"]
# Tue, 09 Jan 2018 21:31:21 GMT
RUN echo 'hosts: files dns' >> /etc/nsswitch.conf
# Tue, 09 Jan 2018 21:31:24 GMT
RUN apk add --no-cache tzdata bash
# Thu, 01 Feb 2018 00:40:39 GMT
ENV INFLUXDB_VERSION=1.4.3
# Thu, 01 Feb 2018 00:40:55 GMT
RUN set -ex &&     apk add --no-cache --virtual .build-deps wget gnupg tar ca-certificates &&     update-ca-certificates &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done &&     wget -q https://dl.influxdata.com/influxdb/releases/influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz.asc &&     wget -q https://dl.influxdata.com/influxdb/releases/influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     gpg --batch --verify influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz.asc influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     mkdir -p /usr/src &&     tar -C /usr/src -xzf influxdb-${INFLUXDB_VERSION}-static_linux_amd64.tar.gz &&     rm -f /usr/src/influxdb-*/influxdb.conf &&     chmod +x /usr/src/influxdb-*/* &&     cp -a /usr/src/influxdb-*/* /usr/bin/ &&     rm -rf *.tar.gz* /usr/src /root/.gnupg &&     apk del .build-deps
# Thu, 01 Feb 2018 00:40:56 GMT
COPY file:3ee2bc0321c2aa2451df7a508649c3a54f0eebc1ef9b8a24967c58105b4d3160 in /etc/influxdb/influxdb.conf 
# Thu, 01 Feb 2018 00:40:56 GMT
EXPOSE 8086/tcp
# Thu, 01 Feb 2018 00:40:56 GMT
VOLUME [/var/lib/influxdb]
# Thu, 01 Feb 2018 00:40:57 GMT
COPY file:098affa3d1b749dacb263ddacfd86a5de1f598d6ba1f7c789ce482c66ee9c80b in /entrypoint.sh 
# Thu, 01 Feb 2018 00:40:57 GMT
COPY file:8c68fc25e98c2a2f524d6b945934ef5ec3a3d95e8ac816c7f6e6d2783913da7a in /init-influxdb.sh 
# Thu, 01 Feb 2018 00:40:57 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 01 Feb 2018 00:40:57 GMT
CMD ["influxd"]
```

-	Layers:
	-	`sha256:605ce1bd3f3164f2949a30501cc596f52a72de05da1306ab360055f0d7130c32`  
		Last Modified: Tue, 09 Jan 2018 21:13:17 GMT  
		Size: 2.0 MB (1991747 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bfc8b91e98122366108d51bd0925304ee67ee4ec9ac28b15a1d3374e5fed982`  
		Last Modified: Tue, 09 Jan 2018 21:32:44 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62834f98d530d68f07f63088db7789b74c69f676d23de56ccdeb88da961f6367`  
		Last Modified: Tue, 09 Jan 2018 21:32:43 GMT  
		Size: 1.5 MB (1504273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:530b2090a4ef16620da7d821e68635c50fb11b751c95766bc5c981e9fa259c16`  
		Last Modified: Thu, 01 Feb 2018 00:42:44 GMT  
		Size: 21.0 MB (21045787 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f15056f4bc8a62b4010a8f03d75d1df4b1efd9ae9ef0f2aa981a61485dd48224`  
		Last Modified: Thu, 01 Feb 2018 00:42:42 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:293eb9ac3ea317788242d809d65ed4bb657e777b51b40e397b6b13295e289a7e`  
		Last Modified: Thu, 01 Feb 2018 00:42:39 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c37bb7352a21b5d51711a44e144577206e8524ba6b7bc102f9eacec2f41c83c7`  
		Last Modified: Thu, 01 Feb 2018 00:42:39 GMT  
		Size: 1.2 KB (1167 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
