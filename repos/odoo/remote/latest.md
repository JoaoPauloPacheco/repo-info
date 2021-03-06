## `odoo:latest`

```console
$ docker pull odoo@sha256:5530f38649ed1872e571d8846bc7804d2338b96b12ad2c4a2f1b18ecccf46bb4
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `odoo:latest` - linux; amd64

```console
$ docker pull odoo@sha256:616ef500c86a3708f63a53508de83746461243c7f41b5eb88910542bbff44c9e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **414.6 MB (414555886 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bbb646b6039b301f4e813277e31cb9ff050be6a9a5f0cd6f8a7c5218d5b17573`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["odoo"]`

```dockerfile
# Tue, 12 Dec 2017 01:44:20 GMT
ADD file:eb2519421c9794ccc99d483c07f59ba305531bc9b4dc294e74d2ddb7de69e52a in / 
# Tue, 12 Dec 2017 01:44:21 GMT
CMD ["bash"]
# Tue, 12 Dec 2017 05:22:06 GMT
MAINTAINER Odoo S.A. <info@odoo.com>
# Tue, 12 Dec 2017 05:22:06 GMT
ENV LANG=C.UTF-8
# Tue, 12 Dec 2017 05:22:37 GMT
RUN set -x;         apt-get update         && apt-get install -y --no-install-recommends             ca-certificates             curl             node-less             python3-pip             python3-setuptools             python3-renderpm             libssl1.0-dev             xz-utils         && curl -o wkhtmltox.tar.xz -SL https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.4/wkhtmltox-0.12.4_linux-generic-amd64.tar.xz         && echo '3f923f425d345940089e44c1466f6408b9619562 wkhtmltox.tar.xz' | sha1sum -c -         && tar xvf wkhtmltox.tar.xz         && cp wkhtmltox/lib/* /usr/local/lib/         && cp wkhtmltox/bin/* /usr/local/bin/         && cp -r wkhtmltox/share/man/man1 /usr/local/share/man/
# Tue, 12 Dec 2017 05:22:37 GMT
ENV ODOO_VERSION=11.0
# Mon, 22 Jan 2018 20:34:09 GMT
ENV ODOO_RELEASE=20180122
# Mon, 22 Jan 2018 20:35:25 GMT
RUN set -x;         curl -o odoo.deb -SL http://nightly.odoo.com/${ODOO_VERSION}/nightly/deb/odoo_${ODOO_VERSION}.${ODOO_RELEASE}_all.deb         && echo '56f61789bc655aaa2c014a3c5f63d80805408359 odoo.deb' | sha1sum -c -         && dpkg --force-depends -i odoo.deb         && apt-get update         && apt-get -y install -f --no-install-recommends         && rm -rf /var/lib/apt/lists/* odoo.deb
# Mon, 22 Jan 2018 20:42:48 GMT
RUN pip3 install num2words xlwt
# Mon, 22 Jan 2018 20:47:03 GMT
COPY file:33fddeba88e5214ff2c7cd05a02348dc417a5de70b767d6ff559e871ee6d046a in / 
# Mon, 22 Jan 2018 20:47:03 GMT
COPY file:db43c8e34bfc1a07c1c22547437af17629fbadb6633084c02cbfc0bb6069c9fd in /etc/odoo/ 
# Mon, 22 Jan 2018 20:47:04 GMT
RUN chown odoo /etc/odoo/odoo.conf
# Mon, 22 Jan 2018 20:47:05 GMT
RUN mkdir -p /mnt/extra-addons         && chown -R odoo /mnt/extra-addons
# Mon, 22 Jan 2018 20:47:05 GMT
VOLUME [/var/lib/odoo /mnt/extra-addons]
# Mon, 22 Jan 2018 20:47:05 GMT
EXPOSE 8069/tcp 8071/tcp
# Mon, 22 Jan 2018 20:47:05 GMT
ENV ODOO_RC=/etc/odoo/odoo.conf
# Mon, 22 Jan 2018 20:47:05 GMT
USER [odoo]
# Mon, 22 Jan 2018 20:47:06 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Mon, 22 Jan 2018 20:47:06 GMT
CMD ["odoo"]
```

-	Layers:
	-	`sha256:723254a2c089166d4bcfa917be0181ddbecd94971ebfe85792d96e7e29be9c68`  
		Last Modified: Tue, 12 Dec 2017 01:53:22 GMT  
		Size: 45.1 MB (45121631 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70518ac76bc0293637ea81d1936563cca08dea6c643b5a8507e1c621c370fb8c`  
		Last Modified: Tue, 12 Dec 2017 05:35:39 GMT  
		Size: 221.4 MB (221395553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1996eb6b6c346ff369d6e942244ab1e4f343bf53ac89e6dcee30bab3fc1bd06`  
		Last Modified: Mon, 22 Jan 2018 21:02:41 GMT  
		Size: 147.6 MB (147574574 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:871c44a18b9bf235be76fd9b9c47059e12371ae629e74e51e16e0db6961e16bf`  
		Last Modified: Mon, 22 Jan 2018 21:01:52 GMT  
		Size: 462.3 KB (462294 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8a6cf3b703ef17275a7d0f1ed818b807ce5b3d7078c5c728148486d76289188`  
		Last Modified: Mon, 22 Jan 2018 21:01:51 GMT  
		Size: 600.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0d5ab43b4cfbe9d15d10ba370edd49da035dfbcfc6f03ba73a4013ed5140d5de`  
		Last Modified: Mon, 22 Jan 2018 21:01:51 GMT  
		Size: 551.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89f04509397d1b5d0689c5193813b9d1abbf3867e00504710c39a5ccfe5cdc13`  
		Last Modified: Mon, 22 Jan 2018 21:01:51 GMT  
		Size: 555.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bb8d99001756065b84c61b3a754dc4e4611880211b2b7dd50d6978806e214fc`  
		Last Modified: Mon, 22 Jan 2018 21:01:51 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
