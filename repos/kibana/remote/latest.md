## `kibana:latest`

```console
$ docker pull kibana@sha256:c1fc1b298c71418d0485bb00ff1c829a6bbae2b401dfb0ba6e6799624a65fc2e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `kibana:latest` - linux; amd64

```console
$ docker pull kibana@sha256:82876f24d69ebc3710adab63225362aae71a6740daeb82871eda0e2bd70200ee
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.5 MB (128545793 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9ef680b9e227a0c0e3818adb5393284f825a907c46b8c06a7b9f6dab093e3491`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["kibana"]`

```dockerfile
# Tue, 12 Dec 2017 01:41:12 GMT
ADD file:1dd78a123212328bdc72ef7888024ea27fe141a72e24e0ea7c3c92b63b73d8d1 in / 
# Tue, 12 Dec 2017 01:41:12 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 02:17:07 GMT
RUN groupadd -r kibana && useradd -r -m -g kibana kibana
# Tue, 12 Dec 2017 02:17:29 GMT
RUN apt-get update && apt-get install -y 		apt-transport-https 		ca-certificates 		wget 		libfontconfig 		libfreetype6 	--no-install-recommends && rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 02:17:29 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 02:17:34 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Tue, 12 Dec 2017 02:17:34 GMT
ENV TINI_VERSION=v0.9.0
# Tue, 12 Dec 2017 02:17:36 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini.asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -rf "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Tue, 12 Dec 2017 02:17:39 GMT
RUN set -ex; 	key='46095ACC8548582C1A2699A9D27D666CD88E42B4'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/elastic.gpg; 	rm -rf "$GNUPGHOME"; 	apt-key list
# Tue, 12 Dec 2017 02:17:40 GMT
RUN echo 'deb https://artifacts.elastic.co/packages/5.x/apt stable main' > /etc/apt/sources.list.d/kibana.list
# Tue, 06 Feb 2018 00:12:35 GMT
ENV KIBANA_VERSION=5.6.7
# Tue, 06 Feb 2018 00:13:01 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y --no-install-recommends kibana=$KIBANA_VERSION 	&& rm -rf /var/lib/apt/lists/* 		&& sed -ri "s!^(\#\s*)?(server\.host:).*!\2 '0.0.0.0'!" /etc/kibana/kibana.yml 	&& grep -q "^server\.host: '0.0.0.0'\$" /etc/kibana/kibana.yml 		&& sed -ri "s!^(\#\s*)?(elasticsearch\.url:).*!\2 'http://elasticsearch:9200'!" /etc/kibana/kibana.yml 	&& grep -q "^elasticsearch\.url: 'http://elasticsearch:9200'\$" /etc/kibana/kibana.yml
# Tue, 06 Feb 2018 00:13:02 GMT
ENV PATH=/usr/share/kibana/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 06 Feb 2018 00:13:02 GMT
COPY file:9a3ed3a1655d5afa631fded5211f1c33f5f49f1d1e0e0d9a031c9e8601111f05 in / 
# Tue, 06 Feb 2018 00:13:02 GMT
EXPOSE 5601/tcp
# Tue, 06 Feb 2018 00:13:03 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 06 Feb 2018 00:13:03 GMT
CMD ["kibana"]
```

-	Layers:
	-	`sha256:f49cf87b52c10aa83b4f4405800527a74400fb19ea1821d209293bc4d53966aa`  
		Last Modified: Tue, 12 Dec 2017 01:47:59 GMT  
		Size: 52.6 MB (52599697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e8acb2289dd361eed17251ca684daf0ab1e69d64e943084b3769a4cc3fbee69`  
		Last Modified: Tue, 12 Dec 2017 02:19:29 GMT  
		Size: 4.4 KB (4404 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d495c79e5bf4b4520dd83263bc19e532cef5dac7a3b42017422152f618a91027`  
		Last Modified: Tue, 12 Dec 2017 02:19:34 GMT  
		Size: 22.4 MB (22405928 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:81c8b36796225fe238e52a9370d7bb38890b788ff8a47526265afcbf27ee6776`  
		Last Modified: Tue, 12 Dec 2017 02:19:28 GMT  
		Size: 500.7 KB (500663 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a4eff393768ebbebb5da20b195e1fd324c5e874dd755311ab525e2a59c9af5b`  
		Last Modified: Tue, 12 Dec 2017 02:19:26 GMT  
		Size: 7.3 KB (7289 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fa4e981b17da66cbc702a13821b838737fc18691ec9363d06031320fb29dfc2`  
		Last Modified: Tue, 12 Dec 2017 02:19:26 GMT  
		Size: 1.4 KB (1450 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e23852241c5bc05b36b6bd619199f95f18c1857d157c24de2cd1fe8e9473990a`  
		Last Modified: Tue, 12 Dec 2017 02:19:26 GMT  
		Size: 224.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b299cfe0c41fb2303cfd7b89054afb5da24f2f731214f93bfd8028df956c9ff4`  
		Last Modified: Tue, 06 Feb 2018 00:27:02 GMT  
		Size: 53.0 MB (53025801 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6214f0c37767d3dcd2fc0a5c7732ce89a536ace1636ac3234de95e3fc4fa9dcb`  
		Last Modified: Tue, 06 Feb 2018 00:26:29 GMT  
		Size: 337.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
