## `redis:latest`

```console
$ docker pull redis@sha256:42e145fc86543c5ee3d8f50ad491adc1a452318b115301cc44c405676f9dd19b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redis:latest` - linux; amd64

```console
$ docker pull redis@sha256:e992a63e634b8ef3084ba6cacf25acd4bd19f2ac0b6d80f129764a9015daf595
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **39.4 MB (39395693 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:de560ba5403e09ed7e6807a78f10895180bf3172052b60d0c72f1197afe66b60`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 01:41:34 GMT
ADD file:e7ac45803c3ab9b7023933b75f5a88eda1f3edca97c7e462401860777cf312f7 in / 
# Tue, 12 Dec 2017 01:41:35 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 07:11:57 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 07:11:57 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 07:12:20 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Feb 2018 00:46:49 GMT
ENV REDIS_VERSION=4.0.8
# Tue, 06 Feb 2018 00:46:49 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Tue, 06 Feb 2018 00:46:50 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Tue, 06 Feb 2018 00:47:41 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Feb 2018 00:47:43 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Feb 2018 00:47:43 GMT
VOLUME [/data]
# Tue, 06 Feb 2018 00:47:43 GMT
WORKDIR /data
# Tue, 06 Feb 2018 00:47:44 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 06 Feb 2018 00:47:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Feb 2018 00:47:44 GMT
EXPOSE 6379/tcp
# Tue, 06 Feb 2018 00:47:44 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:c4bb02b17bb4b034c95a948c99c762cf0486a45f45441a052208d7750f1b413b`  
		Last Modified: Tue, 12 Dec 2017 01:48:52 GMT  
		Size: 30.1 MB (30114519 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:58638acf67c5d1d65732b562d5a7f5525b9788155cc10d4cd96c3d5380fadf04`  
		Last Modified: Tue, 12 Dec 2017 07:17:40 GMT  
		Size: 2.1 KB (2086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f98d108cc38bde856021760374435ab87fa2ef7c4317cd18fd7b7ded7af506a3`  
		Last Modified: Tue, 12 Dec 2017 07:17:40 GMT  
		Size: 981.7 KB (981699 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6ce5793a20719af0b00fef297867501a2657d8fb07061c202b32149c2f78612`  
		Last Modified: Tue, 06 Feb 2018 01:03:00 GMT  
		Size: 8.3 MB (8296886 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3fc67899101b7563cadb4b31e59692fa17ed62a9a86a79d893c30701ab075336`  
		Last Modified: Tue, 06 Feb 2018 01:02:58 GMT  
		Size: 99.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b55db4b27fa54de5d368e5ec1b53b38918e53c51bc751e45ea06a68e7cc38cfb`  
		Last Modified: Tue, 06 Feb 2018 01:02:59 GMT  
		Size: 404.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm variant v5

```console
$ docker pull redis@sha256:82ccd6f80a6460d3dbbab4e23192e861c106be6d3383446065e1428a29192610
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **37.6 MB (37592143 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7fffcf1e3c1222899750cda51b72e156d3e1420f30dd27351d3a6261ebe1b033`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 20:57:33 GMT
ADD file:29d0e44ebcc6f8dc2cfbc86c5034380677d263e9eec27a22ba045e0810836f81 in / 
# Tue, 12 Dec 2017 20:57:34 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 23:14:35 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 23:14:35 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 23:15:21 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Feb 2018 15:09:32 GMT
ENV REDIS_VERSION=4.0.8
# Tue, 06 Feb 2018 15:09:32 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Tue, 06 Feb 2018 15:09:32 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Tue, 06 Feb 2018 15:10:42 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Feb 2018 15:10:43 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Feb 2018 15:10:43 GMT
VOLUME [/data]
# Tue, 06 Feb 2018 15:10:43 GMT
WORKDIR /data
# Tue, 06 Feb 2018 15:10:44 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 06 Feb 2018 15:10:44 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Feb 2018 15:10:44 GMT
EXPOSE 6379/tcp
# Tue, 06 Feb 2018 15:10:44 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:51e696f556166d0e25b3b27c824c4aafbddd5adcfd3f5186c09707f7baa3b312`  
		Last Modified: Tue, 12 Dec 2017 21:07:41 GMT  
		Size: 28.4 MB (28423526 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0206b9cb3a70c21180f01a2532fe2c5a436a48e5fc5d8b939ba69b7d61c80a3a`  
		Last Modified: Tue, 12 Dec 2017 23:18:09 GMT  
		Size: 2.1 KB (2075 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f18f2f5d7b2619f7683612c23f23c54c1f09a9ac9f5714f36e1ff47dffac347`  
		Last Modified: Tue, 12 Dec 2017 23:18:13 GMT  
		Size: 971.2 KB (971228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25635b92d7102aff70fa10be6f4e984bd2b437df2d4a2fc270cf15d4ad85416c`  
		Last Modified: Tue, 06 Feb 2018 15:10:58 GMT  
		Size: 8.2 MB (8194778 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4475ae5eef34cfa997fe92213ec620c1cc3446db2ca4bde030e655929f6d85e`  
		Last Modified: Tue, 06 Feb 2018 15:10:55 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e798f17357153eb4b9535b974c0ebb56743a4774dbfb294d9fd95dfe103cc6f6`  
		Last Modified: Tue, 06 Feb 2018 15:10:55 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm variant v7

```console
$ docker pull redis@sha256:7cf526a2f8056e04b50140020ebedaa73539fae967d5f04004fa34c1d4a9a859
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **35.2 MB (35177313 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e7ce38f3ed4df984db03edd68c19324debfffed00f120af3086e455b0e923c11`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 13:27:47 GMT
ADD file:1f5de474caa19da14d698a3f9c3d161abfa1e19e258a596d64f3dfc9e2f17686 in / 
# Tue, 12 Dec 2017 13:27:47 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 16:40:56 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 16:40:56 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 16:41:50 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Feb 2018 01:27:32 GMT
ENV REDIS_VERSION=4.0.8
# Tue, 06 Feb 2018 01:27:32 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Tue, 06 Feb 2018 01:27:32 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Tue, 06 Feb 2018 01:28:31 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Feb 2018 01:28:32 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Feb 2018 01:28:32 GMT
VOLUME [/data]
# Tue, 06 Feb 2018 01:28:32 GMT
WORKDIR /data
# Tue, 06 Feb 2018 01:28:32 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 06 Feb 2018 01:28:33 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Feb 2018 01:28:33 GMT
EXPOSE 6379/tcp
# Tue, 06 Feb 2018 01:28:33 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:4b9c0f1a415433a98643bdda391dcf4fe5d9653fc3ed3845c7ac1be99eb43399`  
		Last Modified: Tue, 12 Dec 2017 13:39:52 GMT  
		Size: 26.3 MB (26282714 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d6835fe576543df3c87405f33db99aa1f040e3f241c5e5d72ffb416953902b8`  
		Last Modified: Tue, 12 Dec 2017 16:44:59 GMT  
		Size: 2.1 KB (2076 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a11c10ad12017478481b1755839ece7c69945ee8c04b97bb10909db85e4ed338`  
		Last Modified: Tue, 12 Dec 2017 16:44:59 GMT  
		Size: 956.1 KB (956126 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69000625f437a6cf3ee8d6b60151e3b39452ece0ef361e2f590893944afeef55`  
		Last Modified: Tue, 06 Feb 2018 01:29:04 GMT  
		Size: 7.9 MB (7935860 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12aed7147e11e132c5248e25289535495e5d0ad14d81289ee91a77f27e1863e2`  
		Last Modified: Tue, 06 Feb 2018 01:29:02 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:718285eeeaaf6b3766acae3b4b75420baeffe68ad824cb8c6c27be64c95a6deb`  
		Last Modified: Tue, 06 Feb 2018 01:29:02 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm64 variant v8

```console
$ docker pull redis@sha256:c176f707c0b8377acdeee4f8bb2dea83e47c28e195a0d2f51bf5dd1c2172aa8f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **36.9 MB (36876433 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:79ccb057108af0b1b266f0e3d3ef157f65e26939129295e26f3a7c9ab698a29f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 18:26:03 GMT
ADD file:da6be268a98d89a43438155746ca6d08f474e9aa85c64699f50445352b46c348 in / 
# Tue, 12 Dec 2017 18:26:04 GMT
CMD ["bash"]
# Wed, 20 Dec 2017 13:25:39 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 20 Dec 2017 13:25:40 GMT
ENV GOSU_VERSION=1.10
# Wed, 20 Dec 2017 13:26:36 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Feb 2018 13:25:53 GMT
ENV REDIS_VERSION=4.0.8
# Tue, 06 Feb 2018 13:25:53 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Tue, 06 Feb 2018 13:25:54 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Tue, 06 Feb 2018 13:27:45 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Feb 2018 13:27:47 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Feb 2018 13:27:47 GMT
VOLUME [/data]
# Tue, 06 Feb 2018 13:27:48 GMT
WORKDIR /data
# Tue, 06 Feb 2018 13:27:48 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 06 Feb 2018 13:27:49 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Feb 2018 13:27:50 GMT
EXPOSE 6379/tcp
# Tue, 06 Feb 2018 13:27:50 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:8e9df51286bbe86a4cb3ffe54327681ab34b9b6d62c3f4e187ffc677125e4780`  
		Last Modified: Tue, 12 Dec 2017 18:41:37 GMT  
		Size: 27.5 MB (27480582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:075c247daad6bb45a002c0a24377355e91aef8e96dbc920ef85b5f95dba5d597`  
		Last Modified: Wed, 20 Dec 2017 13:31:04 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:671b4ef947e36f312884f8d49f560e5191e57a0e583820b56b530e7ff03d771f`  
		Last Modified: Wed, 20 Dec 2017 13:31:04 GMT  
		Size: 948.7 KB (948652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f10bccc98703ca88b1bd0e49f4f2d9c4b3365d0711c52394bd478877eedd7491`  
		Last Modified: Tue, 06 Feb 2018 13:30:05 GMT  
		Size: 8.4 MB (8444596 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cafc779b99f3b7579b6e089be946244cbca353682df6522f8019af603b2c8fb4`  
		Last Modified: Tue, 06 Feb 2018 13:30:01 GMT  
		Size: 99.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:217dcb97c97acfe1d28bd854c74b53c1a8be2612d4aacd3926c89640d73cf38b`  
		Last Modified: Tue, 06 Feb 2018 13:30:02 GMT  
		Size: 404.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; 386

```console
$ docker pull redis@sha256:c1d2bd3e2ffb3b38672d74ed078157ea4e0925d2739b7bba99381aa70dae86f6
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **38.7 MB (38741291 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5cdfeace81c84e393250a1ebc04a88d2acdee83d1e2938dd69a77e95b2adb4df`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 14:21:05 GMT
ADD file:d31765999b40e32b628f3ec72b762f007f4918b08c507484e425adc990c87c26 in / 
# Tue, 12 Dec 2017 14:21:05 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 21:03:38 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 21:03:38 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 21:04:16 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Feb 2018 14:09:59 GMT
ENV REDIS_VERSION=4.0.8
# Tue, 06 Feb 2018 14:09:59 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Tue, 06 Feb 2018 14:10:00 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Tue, 06 Feb 2018 14:11:14 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Feb 2018 14:12:12 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Feb 2018 14:12:12 GMT
VOLUME [/data]
# Tue, 06 Feb 2018 14:12:12 GMT
WORKDIR /data
# Tue, 06 Feb 2018 14:12:13 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 06 Feb 2018 14:12:13 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Feb 2018 14:12:13 GMT
EXPOSE 6379/tcp
# Tue, 06 Feb 2018 14:12:14 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:6b323e7c684c46ec9e577d3acb692c7e1c0c26ffbea6a4530dbe784a7eedf0f7`  
		Last Modified: Tue, 12 Dec 2017 14:49:35 GMT  
		Size: 30.3 MB (30266257 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00b36a22b0f548b632d8bc28aa752a7c776351e3fa3c167b13901a9a648dff0f`  
		Last Modified: Tue, 12 Dec 2017 21:11:34 GMT  
		Size: 2.1 KB (2074 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:625bd220ae9238fdcd1a3e9db810236dc47502995b93d54b4a7bc5f474508112`  
		Last Modified: Tue, 12 Dec 2017 21:11:34 GMT  
		Size: 960.8 KB (960808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2a842fb5bf7992b4c96576cbe97492ee102a7ece4241dc58189b27f2972a325`  
		Last Modified: Tue, 06 Feb 2018 14:22:18 GMT  
		Size: 7.5 MB (7511649 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5df78bbcf8a6821271ca85c542a0de04934d0d8f358d3f3fa0d118d9b668276`  
		Last Modified: Tue, 06 Feb 2018 14:22:15 GMT  
		Size: 99.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:906e82ad113af8575aa1425cd184b14bbd3715f17ef9ce993cdc39782e22c8ba`  
		Last Modified: Tue, 06 Feb 2018 14:22:17 GMT  
		Size: 404.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; ppc64le

```console
$ docker pull redis@sha256:134ac2054c08eee9a609088a5d0db7e71892b37b7120ec7142e25f6e79cd1ca2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **38.9 MB (38917361 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9e021d56f58b628c70c15a9b5a2883d38c4d3d36b889045287970ea8acdc7f6e`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 01:33:17 GMT
ADD file:db3712029b01ae02058b528d156cfdf714f7f2b5fc30216a349f13c15ff9fd67 in / 
# Tue, 12 Dec 2017 01:33:18 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 06:40:30 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Tue, 12 Dec 2017 06:40:32 GMT
ENV GOSU_VERSION=1.10
# Tue, 12 Dec 2017 06:42:22 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Feb 2018 06:35:29 GMT
ENV REDIS_VERSION=4.0.8
# Tue, 06 Feb 2018 06:35:31 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Tue, 06 Feb 2018 06:35:32 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Tue, 06 Feb 2018 06:37:49 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Feb 2018 06:37:52 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Feb 2018 06:37:53 GMT
VOLUME [/data]
# Tue, 06 Feb 2018 06:37:55 GMT
WORKDIR /data
# Tue, 06 Feb 2018 06:37:56 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 06 Feb 2018 06:37:58 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Feb 2018 06:38:00 GMT
EXPOSE 6379/tcp
# Tue, 06 Feb 2018 06:38:01 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:f90148bfa218fdcac96e1ad5dd98070db3f45afdca6148d5d71bb9c4b12e5776`  
		Last Modified: Tue, 12 Dec 2017 01:39:02 GMT  
		Size: 29.3 MB (29306117 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f662385d2726c68cbb1dde138126e2577b69f2f75edb031782b33056fcca8e15`  
		Last Modified: Tue, 12 Dec 2017 06:50:31 GMT  
		Size: 2.1 KB (2098 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75d4e7f0b93f593fb94ad43d33ba101f2f418b2ce017189138ab2b434f5a6b19`  
		Last Modified: Tue, 12 Dec 2017 06:50:31 GMT  
		Size: 950.7 KB (950658 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9f70906cd9707ce7d0f27dde0849bd499f7beb920f7ed33713946f7e2913ea2`  
		Last Modified: Tue, 06 Feb 2018 06:39:23 GMT  
		Size: 8.7 MB (8657952 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf9bf18c4bbaae7b9ba3e85535dde50c06b297ba4f49b24badd8c6a2c4cfc66b`  
		Last Modified: Tue, 06 Feb 2018 06:39:21 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0d2e3605ac268c0cd583c5f2d686a9295bde4b56c66b055a32363307d47b11a`  
		Last Modified: Tue, 06 Feb 2018 06:39:22 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; s390x

```console
$ docker pull redis@sha256:238e9fb365b47d4caee288075684a904a3fc5d91bff4541a6c372f003549272f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **40.2 MB (40197448 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b41868a13131a6e8199602f307a85d93db5973ceb41ff046fd86cea900681105`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 12 Dec 2017 06:23:05 GMT
ADD file:68877912183dff16971679b6264399a76d678986d7cf02bbba2e006d91077cf3 in / 
# Tue, 12 Dec 2017 06:23:06 GMT
CMD ["bash"]
# Sun, 07 Jan 2018 09:26:06 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Sun, 07 Jan 2018 09:26:06 GMT
ENV GOSU_VERSION=1.10
# Sun, 07 Jan 2018 09:26:33 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Tue, 06 Feb 2018 06:24:31 GMT
ENV REDIS_VERSION=4.0.8
# Tue, 06 Feb 2018 06:24:31 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Tue, 06 Feb 2018 06:24:32 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Tue, 06 Feb 2018 06:25:11 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Tue, 06 Feb 2018 06:25:12 GMT
RUN mkdir /data && chown redis:redis /data
# Tue, 06 Feb 2018 06:25:12 GMT
VOLUME [/data]
# Tue, 06 Feb 2018 06:25:12 GMT
WORKDIR /data
# Tue, 06 Feb 2018 06:25:12 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Tue, 06 Feb 2018 06:25:12 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 06 Feb 2018 06:25:12 GMT
EXPOSE 6379/tcp
# Tue, 06 Feb 2018 06:25:12 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:7ef9b5c13de473137c3ae16d379a5f152b59921d4e96887c06f9e1291af84691`  
		Last Modified: Thu, 14 Dec 2017 00:53:34 GMT  
		Size: 30.3 MB (30293639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:608e779e09f2eff9338668b6f32d30ad6db5824db6e05a40163baa53af8a4732`  
		Last Modified: Sun, 07 Jan 2018 09:28:52 GMT  
		Size: 2.1 KB (2094 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca3bc2bf99d2d3b8b7af50eabf05bcd385693d216437119560e8b76a250123d1`  
		Last Modified: Sun, 07 Jan 2018 09:28:52 GMT  
		Size: 966.9 KB (966920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e3b8cfc49318affd19b1bf038f24056cf6e9d29af52b4bfae8a87a937a867191`  
		Last Modified: Tue, 06 Feb 2018 06:26:12 GMT  
		Size: 8.9 MB (8934295 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40c1e2a9f2143561d02f9cf91b0e1349c12689ad33f621bb6c3667e7bd93a138`  
		Last Modified: Tue, 06 Feb 2018 06:26:09 GMT  
		Size: 98.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b436c81dc8868e47fbe319c57134765522c95c0aa21df408b5b306f6b4efed0`  
		Last Modified: Tue, 06 Feb 2018 06:26:10 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
