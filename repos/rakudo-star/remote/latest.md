## `rakudo-star:latest`

```console
$ docker pull rakudo-star@sha256:2872bcd0a1521274cd83c22f70ccbdc0ba0773c5d1060f4c15b97de555f7acc8
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `rakudo-star:latest` - linux; amd64

```console
$ docker pull rakudo-star@sha256:223dcf89aac45fe7bab6ab76f86869389a90aeead5566627b1c1ca9a6e1df197
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **131.6 MB (131566930 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7668bea85f6ea7508c91c6953ff460946ee824c40c668292dd19ceb95cece3fe`
-	Default Command: `["perl6"]`

```dockerfile
# Tue, 12 Dec 2017 01:44:20 GMT
ADD file:eb2519421c9794ccc99d483c07f59ba305531bc9b4dc294e74d2ddb7de69e52a in / 
# Tue, 12 Dec 2017 01:44:21 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 07:54:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 07:54:15 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 12 Dec 2017 07:54:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 12 Dec 2017 17:09:41 GMT
MAINTAINER Rob Hoelz
# Tue, 12 Dec 2017 17:09:43 GMT
RUN groupadd -r perl6 && useradd -r -g perl6 perl6
# Wed, 31 Jan 2018 00:33:45 GMT
ARG rakudo_version=2018.01
# Wed, 31 Jan 2018 00:33:46 GMT
ENV rakudo_version=2018.01
# Wed, 31 Jan 2018 00:44:52 GMT
RUN buildDeps='         gcc         libc6-dev         libencode-perl         make     '     && set -x     && apt-get update     && apt-get --yes install --no-install-recommends $buildDeps     && rm -rf /var/lib/apt/lists/*     && mkdir /root/rakudo     && curl -fsSL http://rakudo.org/downloads/star/rakudo-star-${rakudo_version}.tar.gz -o rakudo.tar.gz     && tar xzf rakudo.tar.gz --strip-components=1 -C /root/rakudo     && (         cd /root/rakudo         && perl Configure.pl --prefix=/usr --gen-moar         && make install     )     && rm -rf /rakudo.tar.gz /root/rakudo     && apt-get purge -y --auto-remove $buildDeps
# Wed, 31 Jan 2018 00:44:52 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/share/perl6/site/bin
# Wed, 31 Jan 2018 00:44:52 GMT
CMD ["perl6"]
```

-	Layers:
	-	`sha256:723254a2c089166d4bcfa917be0181ddbecd94971ebfe85792d96e7e29be9c68`  
		Last Modified: Tue, 12 Dec 2017 01:53:22 GMT  
		Size: 45.1 MB (45121631 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:abe15a44e12f84b4aac20d4f2b450ec8638cc0b176c9130d1802cb4fed17d953`  
		Last Modified: Tue, 12 Dec 2017 08:03:48 GMT  
		Size: 11.1 MB (11107352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:409a28e3cc3de08700c9d37c809a6d3aa43dc076402943919f4a78c286c60a0b`  
		Last Modified: Tue, 12 Dec 2017 08:03:48 GMT  
		Size: 4.3 MB (4335420 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50316693559041b3c6895bce352b10c302f31c074495671a820b689d2ce12baa`  
		Last Modified: Tue, 12 Dec 2017 08:04:27 GMT  
		Size: 50.0 MB (50022829 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c9faa9cd7187ed3e04fe2c888775a96bda33659cc961b37453be015e0b8942c`  
		Last Modified: Tue, 12 Dec 2017 17:21:49 GMT  
		Size: 1.8 KB (1763 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b351e20ac01818b90d54ea873b69f430caa5a30fdb7b13ed3f6c8300545cc0ae`  
		Last Modified: Wed, 31 Jan 2018 00:45:13 GMT  
		Size: 21.0 MB (20977935 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
