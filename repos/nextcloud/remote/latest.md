## `nextcloud:latest`

```console
$ docker pull nextcloud@sha256:d43c07e4c0e3915d341347c224acc9ef4fd4ea1f8f7de2c3aa46f2824a8ed304
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

### `nextcloud:latest` - linux; amd64

```console
$ docker pull nextcloud@sha256:8d3359271fb1e7f45fb8f00f6d0bb0bff9ba6a4a8acf6febf98706ebb9147d75
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **231.5 MB (231535835 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9d7d01184cbfd938e9451332ff4c12b838169f4688bbb360893e9aadab929ef7`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 12 Dec 2017 01:41:12 GMT
ADD file:1dd78a123212328bdc72ef7888024ea27fe141a72e24e0ea7c3c92b63b73d8d1 in / 
# Tue, 12 Dec 2017 01:41:12 GMT
CMD ["bash"]
# Tue, 19 Dec 2017 20:02:28 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Tue, 19 Dec 2017 20:02:29 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Thu, 04 Jan 2018 02:17:45 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Thu, 04 Jan 2018 02:17:45 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 04 Jan 2018 02:17:46 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 04 Jan 2018 02:28:49 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Thu, 04 Jan 2018 02:28:50 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Thu, 04 Jan 2018 02:28:50 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Thu, 04 Jan 2018 02:28:51 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Thu, 04 Jan 2018 02:28:52 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Thu, 04 Jan 2018 02:28:52 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Thu, 04 Jan 2018 02:28:53 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Thu, 04 Jan 2018 02:28:53 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Thu, 04 Jan 2018 02:28:54 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Thu, 04 Jan 2018 02:28:54 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 02:28:54 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 02:28:54 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 09 Jan 2018 00:38:35 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Tue, 09 Jan 2018 00:38:35 GMT
ENV PHP_VERSION=7.1.13
# Tue, 09 Jan 2018 00:38:36 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 00:38:36 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Tue, 09 Jan 2018 00:38:51 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Tue, 09 Jan 2018 00:38:51 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 00:41:26 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 00:41:27 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Tue, 09 Jan 2018 00:41:27 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 00:41:28 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Tue, 09 Jan 2018 00:41:28 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 00:41:28 GMT
EXPOSE 80/tcp
# Tue, 09 Jan 2018 00:41:28 GMT
CMD ["apache2-foreground"]
# Tue, 06 Feb 2018 01:11:21 GMT
RUN set -ex;     apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;         savedAptMark="$(apt-mark showmanual)";         apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install gd exif intl mbstring mcrypt ldap mysqli opcache pdo_mysql pdo_pgsql pgsql zip pcntl;     pecl install APCu-5.1.9;     pecl install memcached-3.0.4;     pecl install redis-3.1.6;     docker-php-ext-enable apcu redis memcached;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*;         {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         chown -R www-data:root /var/www/html;     chmod -R g=u /var/www/html
# Tue, 06 Feb 2018 01:11:21 GMT
VOLUME [/var/www/html]
# Tue, 06 Feb 2018 01:11:22 GMT
RUN a2enmod rewrite
# Tue, 06 Feb 2018 01:28:39 GMT
ENV NEXTCLOUD_VERSION=12.0.5
# Tue, 06 Feb 2018 01:28:54 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Tue, 06 Feb 2018 01:28:55 GMT
COPY multi:b680850547a7d6e3b427bb289061cea91ea149b388bd13c63f961d11b2eda4c9 in / 
# Tue, 06 Feb 2018 01:28:56 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Tue, 06 Feb 2018 01:28:56 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 06 Feb 2018 01:28:56 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:f49cf87b52c10aa83b4f4405800527a74400fb19ea1821d209293bc4d53966aa`  
		Last Modified: Tue, 12 Dec 2017 01:47:59 GMT  
		Size: 52.6 MB (52599697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:185616061386b6fbf50284203b0bfdefaca12fc92bbb65d2f65c3d51dd942ad9`  
		Last Modified: Tue, 19 Dec 2017 21:56:59 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5fc132db2e0d4529b0f1ecce1b0208d1415551c378edbbf72912b2da05b161b1`  
		Last Modified: Thu, 04 Jan 2018 04:57:51 GMT  
		Size: 80.2 MB (80245843 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00c1c323341aeccc9c187d1704349390ffbf8437718af11841e34591ff13d47f`  
		Last Modified: Thu, 04 Jan 2018 04:57:30 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff3701349211b0562574e27d711206dcd615b3797f6d77c9aa875134377b7761`  
		Last Modified: Thu, 04 Jan 2018 04:59:28 GMT  
		Size: 4.5 MB (4466468 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:faab1d6ad70f31babae6f7c2270dd249254e70d4c08a50256538f302ff572a81`  
		Last Modified: Thu, 04 Jan 2018 04:59:26 GMT  
		Size: 1.2 KB (1248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eae8d88d75e023a84174030212c8214aa6901e2fc3ed5ec0a28410f0d16433ba`  
		Last Modified: Thu, 04 Jan 2018 04:59:24 GMT  
		Size: 428.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fbd4c732645aa40ffe7bc27c7cd11c0788e303712f489bab7103dbedd6c8791`  
		Last Modified: Thu, 04 Jan 2018 04:59:24 GMT  
		Size: 231.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2e59bdd1208f7a5114bfa402c99e628de65f3e48c7497bfa31e1747b10414ff`  
		Last Modified: Thu, 04 Jan 2018 04:59:24 GMT  
		Size: 490.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:af536a539f2ee3b65b0e9288f75df796b0f3489ef9e62716df4f27807c050215`  
		Last Modified: Tue, 09 Jan 2018 03:33:45 GMT  
		Size: 12.5 MB (12547852 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca33427a3005101d445a9f430a7a67afcbc85a9bbc26094f3f7e7484fdd1b263`  
		Last Modified: Tue, 09 Jan 2018 03:33:42 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c14c2a608861b3df0d0a0f56a7bad654b75f9b3865d9b11acddd9b18e9e10d74`  
		Last Modified: Tue, 09 Jan 2018 03:33:45 GMT  
		Size: 14.2 MB (14203360 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2363ccdb49f35a5d6aad201b093e872f1d1729c7c3e68702ce543bd74c969234`  
		Last Modified: Tue, 09 Jan 2018 03:33:41 GMT  
		Size: 2.2 KB (2190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4277e7718bb1d21575004064e531fe9059504763cf4de3390d5c7aed2a89bbf3`  
		Last Modified: Tue, 09 Jan 2018 03:33:41 GMT  
		Size: 905.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:856e618ddf575072c038c97db1f7572b08abb632b8676198ca89de1bc0805a88`  
		Last Modified: Tue, 06 Feb 2018 01:30:22 GMT  
		Size: 18.9 MB (18935066 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c57ad2be05f3c7112978bb829cfe528d7695a59923bec9835059d39133c15458`  
		Last Modified: Tue, 06 Feb 2018 01:30:16 GMT  
		Size: 318.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b7089d8f45e1e233fd1d28c7bb884e818d8883e37f8c8d744c390c28d6f4146f`  
		Last Modified: Tue, 06 Feb 2018 01:33:13 GMT  
		Size: 48.5 MB (48528979 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6be4009ae560ef749a767e9a96a79c3932a754fa1afcb0b77dcc81963e642639`  
		Last Modified: Tue, 06 Feb 2018 01:33:06 GMT  
		Size: 999.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8b1c6bd8a1b067ec31fdfe4018cc3e514fc58458dd91ba6b601526717a80374`  
		Last Modified: Tue, 06 Feb 2018 01:33:07 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nextcloud:latest` - linux; arm variant v5

```console
$ docker pull nextcloud@sha256:45604d0a6b5314ee6666ff58ccf2855fc6d32a68a780dca224795a2e75650ff3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **209.6 MB (209638850 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7eb2a84cce4a2f3c932e8f15414b08fda9cb575821307a2ddca0da83522e9593`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 12 Dec 2017 20:57:00 GMT
ADD file:2c2c6b8bfbbc9860c0ddd8a2ba3d769171576fc13d5d99fb50a852f6b03618d1 in / 
# Tue, 12 Dec 2017 20:57:00 GMT
CMD ["bash"]
# Wed, 20 Dec 2017 14:53:33 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Wed, 20 Dec 2017 14:53:33 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Thu, 04 Jan 2018 14:54:35 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Thu, 04 Jan 2018 14:54:36 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 04 Jan 2018 14:54:37 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 04 Jan 2018 14:59:34 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Thu, 04 Jan 2018 14:59:34 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Thu, 04 Jan 2018 14:59:34 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Thu, 04 Jan 2018 14:59:35 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Thu, 04 Jan 2018 14:59:36 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Thu, 04 Jan 2018 14:59:37 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Thu, 04 Jan 2018 14:59:37 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Thu, 04 Jan 2018 14:59:38 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Thu, 04 Jan 2018 14:59:38 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Thu, 04 Jan 2018 14:59:38 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 14:59:38 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 14:59:39 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 09 Jan 2018 14:57:25 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Tue, 09 Jan 2018 14:57:25 GMT
ENV PHP_VERSION=7.1.13
# Tue, 09 Jan 2018 14:57:25 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 14:57:25 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Tue, 09 Jan 2018 14:58:05 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Tue, 09 Jan 2018 14:58:05 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 15:01:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 15:01:10 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Tue, 09 Jan 2018 15:01:10 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 15:01:11 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Tue, 09 Jan 2018 15:01:11 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 15:01:11 GMT
EXPOSE 80/tcp
# Tue, 09 Jan 2018 15:01:12 GMT
CMD ["apache2-foreground"]
# Tue, 06 Feb 2018 03:31:30 GMT
RUN set -ex;     apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;         savedAptMark="$(apt-mark showmanual)";         apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install gd exif intl mbstring mcrypt ldap mysqli opcache pdo_mysql pdo_pgsql pgsql zip pcntl;     pecl install APCu-5.1.9;     pecl install memcached-3.0.4;     pecl install redis-3.1.6;     docker-php-ext-enable apcu redis memcached;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*;         {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         chown -R www-data:root /var/www/html;     chmod -R g=u /var/www/html
# Tue, 06 Feb 2018 03:31:30 GMT
VOLUME [/var/www/html]
# Tue, 06 Feb 2018 03:31:31 GMT
RUN a2enmod rewrite
# Tue, 06 Feb 2018 03:39:45 GMT
ENV NEXTCLOUD_VERSION=12.0.5
# Tue, 06 Feb 2018 03:40:07 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Tue, 06 Feb 2018 03:40:08 GMT
COPY multi:b680850547a7d6e3b427bb289061cea91ea149b388bd13c63f961d11b2eda4c9 in / 
# Tue, 06 Feb 2018 03:40:09 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Tue, 06 Feb 2018 03:40:09 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 06 Feb 2018 03:40:09 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:fbe67b6ec6f136174afee77eff07fd99e5764d9db2b13d0dc1189bf8203d289b`  
		Last Modified: Tue, 12 Dec 2017 21:06:47 GMT  
		Size: 50.9 MB (50882486 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:940132a1efc5f029fd2e21473210940db3f7676ffdc20d10f0b84261dff9527a`  
		Last Modified: Wed, 20 Dec 2017 15:47:04 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50f63b8685afdce2bdc95d81cd4269cbf8c1dd6da568eb53172f94107494f4e5`  
		Last Modified: Thu, 04 Jan 2018 15:50:12 GMT  
		Size: 61.4 MB (61428603 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f3a5b45509afe172e390a0f71d97c7b4195138c10d084041caecbd665c2769ad`  
		Last Modified: Thu, 04 Jan 2018 15:49:53 GMT  
		Size: 213.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:438920dcb5042a3ee346e5c3d94daa7d47428115219da297c47579fc49bcca87`  
		Last Modified: Thu, 04 Jan 2018 15:50:50 GMT  
		Size: 4.2 MB (4182810 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23124cb9b61400f1e754c1a59fb1614264377d2b39c0fb4dfebb5d2a4fd8d684`  
		Last Modified: Thu, 04 Jan 2018 15:50:49 GMT  
		Size: 1.3 KB (1279 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c554f4b6b4240896c5530a4feb88e7f922ea4a80044eb0193d18c14cc8c8e51f`  
		Last Modified: Thu, 04 Jan 2018 15:50:48 GMT  
		Size: 466.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72b918af2e49b9fb2b740716458f759b47bef78a47aee88966aeb5ff86fcf3b0`  
		Last Modified: Thu, 04 Jan 2018 15:50:47 GMT  
		Size: 229.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe5a10edf763b46178f1ea65b671be5fc4bbeb291e0a354b9cdfd17f8b40fd5d`  
		Last Modified: Thu, 04 Jan 2018 15:50:48 GMT  
		Size: 507.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68755d1f3ff1fc4c038b45b7a43ded6bed8d1340a95538759defb7af2fef7ab6`  
		Last Modified: Tue, 09 Jan 2018 15:48:10 GMT  
		Size: 12.5 MB (12546305 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7375b63ff32aa8752ca0b758d7473e9048baed7695d4c6ac69b05a79a13359db`  
		Last Modified: Tue, 09 Jan 2018 15:48:07 GMT  
		Size: 501.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:93d04f0c1f0e8bb3dd6a598c339d57b0d5b04a05eded8b6aac8b04822230c34b`  
		Last Modified: Tue, 09 Jan 2018 15:48:12 GMT  
		Size: 13.5 MB (13518683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:315dc5f0906acf522e625822a6d681b93bc101238a205ce158142600558a472b`  
		Last Modified: Tue, 09 Jan 2018 15:48:08 GMT  
		Size: 2.2 KB (2187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14836bafd2ac13021d3986df0702051f8bf2a2eeb09d5435ab8d6bd5a0d12617`  
		Last Modified: Tue, 09 Jan 2018 15:48:07 GMT  
		Size: 904.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a23ec14dc4fede7e03f27d731f7f4e327cc114afa120cfb90822e9fa3a2538d7`  
		Last Modified: Tue, 06 Feb 2018 03:41:03 GMT  
		Size: 18.5 MB (18542384 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:299134291a9812ebd383c188b444c8784b7b7e96b6b13c7781fbfb1a55f775d0`  
		Last Modified: Tue, 06 Feb 2018 03:40:58 GMT  
		Size: 315.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fa18b34c8410b7f0826bf838011062cd28d9ef96880b09522cf7a6bc6a9a993`  
		Last Modified: Tue, 06 Feb 2018 03:42:54 GMT  
		Size: 48.5 MB (48528902 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e839ece496747f4aeb0dfc88483d39d0a75b7b207c1623e6614c9275ab79791`  
		Last Modified: Tue, 06 Feb 2018 03:42:37 GMT  
		Size: 998.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0ab5aafd04d95b77e3c6d6fd802913368545c341ab8ffdf59e02afdc896f883`  
		Last Modified: Tue, 06 Feb 2018 03:42:36 GMT  
		Size: 852.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nextcloud:latest` - linux; arm variant v7

```console
$ docker pull nextcloud@sha256:fd3a09e781495772a59e020e2035339afd46fd2dfb999c1f2993df246d8564b8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **206.4 MB (206411105 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ca646f3d68b117696e775b70956878d3bdbeca2c38ebe59b8c012b21a0a011f4`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 12 Dec 2017 13:27:05 GMT
ADD file:aeb57f3a84dc1b93e1d38a80409a407df553344149d5070ed79b656865c90c54 in / 
# Tue, 12 Dec 2017 13:27:06 GMT
CMD ["bash"]
# Wed, 20 Dec 2017 13:02:52 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Wed, 20 Dec 2017 13:02:52 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Thu, 04 Jan 2018 13:00:45 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Thu, 04 Jan 2018 13:00:45 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 04 Jan 2018 13:00:46 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 04 Jan 2018 13:05:33 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Thu, 04 Jan 2018 13:05:33 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Thu, 04 Jan 2018 13:05:33 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Thu, 04 Jan 2018 13:05:34 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Thu, 04 Jan 2018 13:05:35 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Thu, 04 Jan 2018 13:05:36 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Thu, 04 Jan 2018 13:05:36 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Thu, 04 Jan 2018 13:05:37 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Thu, 04 Jan 2018 13:05:37 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Thu, 04 Jan 2018 13:05:37 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 13:05:37 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 13:05:38 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 09 Jan 2018 13:06:30 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Tue, 09 Jan 2018 13:06:31 GMT
ENV PHP_VERSION=7.1.13
# Tue, 09 Jan 2018 13:06:31 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 13:06:31 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Tue, 09 Jan 2018 13:07:10 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Tue, 09 Jan 2018 13:07:11 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 13:10:00 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 13:10:01 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Tue, 09 Jan 2018 13:10:01 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 13:10:01 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Tue, 09 Jan 2018 13:10:01 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 13:10:02 GMT
EXPOSE 80/tcp
# Tue, 09 Jan 2018 13:10:02 GMT
CMD ["apache2-foreground"]
# Tue, 06 Feb 2018 04:13:49 GMT
RUN set -ex;     apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;         savedAptMark="$(apt-mark showmanual)";         apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install gd exif intl mbstring mcrypt ldap mysqli opcache pdo_mysql pdo_pgsql pgsql zip pcntl;     pecl install APCu-5.1.9;     pecl install memcached-3.0.4;     pecl install redis-3.1.6;     docker-php-ext-enable apcu redis memcached;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*;         {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         chown -R www-data:root /var/www/html;     chmod -R g=u /var/www/html
# Tue, 06 Feb 2018 04:13:50 GMT
VOLUME [/var/www/html]
# Tue, 06 Feb 2018 04:13:50 GMT
RUN a2enmod rewrite
# Tue, 06 Feb 2018 04:21:14 GMT
ENV NEXTCLOUD_VERSION=12.0.5
# Tue, 06 Feb 2018 04:21:36 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Tue, 06 Feb 2018 04:21:38 GMT
COPY multi:b680850547a7d6e3b427bb289061cea91ea149b388bd13c63f961d11b2eda4c9 in / 
# Tue, 06 Feb 2018 04:21:38 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Tue, 06 Feb 2018 04:21:39 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 06 Feb 2018 04:21:39 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:95e140a16c792899abc97cadee0138064dd21346fe51aa332ca4cbbd5563383c`  
		Last Modified: Tue, 12 Dec 2017 13:38:47 GMT  
		Size: 48.7 MB (48691755 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fe6b8e9a5cea34996ae971f312ad63b45e810b0446880a52e081ced2cbfa88b9`  
		Last Modified: Wed, 20 Dec 2017 13:52:32 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76581d7db5179696ba384f33dfbdfb711706587f1af1d13ac570bba3c45e8953`  
		Last Modified: Thu, 04 Jan 2018 13:52:32 GMT  
		Size: 61.8 MB (61826560 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b049f32d0e1f7bd688a6c490380f4577cc1afc4ce1fa4d24acde97a4bc62f720`  
		Last Modified: Thu, 04 Jan 2018 13:52:15 GMT  
		Size: 214.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d51b85e5c865ec8ddee52c0c3b33983638ea5a1783056d645661934eb3a9a390`  
		Last Modified: Thu, 04 Jan 2018 13:53:10 GMT  
		Size: 3.9 MB (3937252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b5e863702a22f10a57bd2abeb0643b9e7a1fd746207bad044b62ddd0df40239`  
		Last Modified: Thu, 04 Jan 2018 13:53:09 GMT  
		Size: 1.3 KB (1281 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:08fad5991fa004815e9ae712395d1366049b69946ce321a869f9de308478d7a4`  
		Last Modified: Thu, 04 Jan 2018 13:53:08 GMT  
		Size: 467.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e1954d3468024035535c60448c6c75857a29b6308167749ee380381460c9bd0`  
		Last Modified: Thu, 04 Jan 2018 13:53:08 GMT  
		Size: 229.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06736516e0a6d5d8fb7844efe2f931919f2e8be8a415fa58f445bb2079b0bdf2`  
		Last Modified: Thu, 04 Jan 2018 13:53:08 GMT  
		Size: 513.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a9ff9e45e0e8ea3d4f4ec1b45c9d9e61089b1f5215fcead80261808be109a4c`  
		Last Modified: Tue, 09 Jan 2018 13:55:10 GMT  
		Size: 12.5 MB (12546299 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19015b9c5f408f80d61dd297b08677a2a0692474230cb3f2efbb55ee44f76d42`  
		Last Modified: Tue, 09 Jan 2018 13:55:07 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65c94fa8d61034e7b36e2c891e2414e5caa10dc60c2551982314d518347c62c6`  
		Last Modified: Tue, 09 Jan 2018 13:55:11 GMT  
		Size: 12.8 MB (12809590 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f1b44f0314d69e193fb798b92c89ac11b6da172c4e9354fdb386022f72dad71d`  
		Last Modified: Tue, 09 Jan 2018 13:55:07 GMT  
		Size: 2.2 KB (2189 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c9a8bb8d23e6d9ff8c371310b7dd4b4af9947d39e69aafb45b0cf268794fd54`  
		Last Modified: Tue, 09 Jan 2018 13:55:07 GMT  
		Size: 904.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcb4bb831719449c4d0c2b529caf46135e5d5dcc970c4c06d238d92f6c32c611`  
		Last Modified: Tue, 06 Feb 2018 04:22:32 GMT  
		Size: 18.1 MB (18062069 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f297f63ef355aadb94d6e3c3d8542bb7532c8a38aee467e135d6e4c94a135181`  
		Last Modified: Tue, 06 Feb 2018 04:22:28 GMT  
		Size: 310.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f77d079c7403524ff34b107a2a4ffed6b3d70f8e08477dd093b378714946f0c`  
		Last Modified: Tue, 06 Feb 2018 04:24:19 GMT  
		Size: 48.5 MB (48528899 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e98fb21341d53cea964531a214bf6293aa4c0f1257776a0852063a55d8b2cdb`  
		Last Modified: Tue, 06 Feb 2018 04:24:04 GMT  
		Size: 998.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f7da1f59173f138eded0150bdba1d60e424318c8f471710700fc644d2a0f878`  
		Last Modified: Tue, 06 Feb 2018 04:24:03 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nextcloud:latest` - linux; arm64 variant v8

```console
$ docker pull nextcloud@sha256:ba20be79d6a4330e041d711e86f8d3e476baa4e54fb8f82dfa7513e7eb7a0660
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **209.6 MB (209616991 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1995822d127540decd8f9c39b75fcdfea6b36f819936d733bb620e83632b0c14`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 12 Dec 2017 18:24:58 GMT
ADD file:f0da52be154f821919dcbfb92afd89714053ae507038126715c96ac77a6768e1 in / 
# Tue, 12 Dec 2017 18:24:59 GMT
CMD ["bash"]
# Wed, 20 Dec 2017 03:34:00 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Wed, 20 Dec 2017 03:34:01 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Thu, 04 Jan 2018 03:35:42 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Thu, 04 Jan 2018 03:35:43 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 04 Jan 2018 03:35:44 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 04 Jan 2018 03:44:20 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Thu, 04 Jan 2018 03:44:21 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Thu, 04 Jan 2018 03:44:21 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Thu, 04 Jan 2018 03:44:23 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Thu, 04 Jan 2018 03:44:25 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Thu, 04 Jan 2018 03:44:26 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Thu, 04 Jan 2018 03:44:31 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Thu, 04 Jan 2018 03:44:31 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Thu, 04 Jan 2018 03:44:32 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Thu, 04 Jan 2018 03:44:33 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 03:44:34 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 03:44:34 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 09 Jan 2018 04:06:07 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Tue, 09 Jan 2018 04:06:08 GMT
ENV PHP_VERSION=7.1.13
# Tue, 09 Jan 2018 04:06:08 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 04:06:09 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Tue, 09 Jan 2018 04:06:44 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Tue, 09 Jan 2018 04:06:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 04:11:58 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 04:11:59 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Tue, 09 Jan 2018 04:12:00 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 04:12:00 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Tue, 09 Jan 2018 04:12:01 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 04:12:02 GMT
EXPOSE 80/tcp
# Tue, 09 Jan 2018 04:12:02 GMT
CMD ["apache2-foreground"]
# Tue, 06 Feb 2018 09:43:33 GMT
RUN set -ex;     apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;         savedAptMark="$(apt-mark showmanual)";         apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install gd exif intl mbstring mcrypt ldap mysqli opcache pdo_mysql pdo_pgsql pgsql zip pcntl;     pecl install APCu-5.1.9;     pecl install memcached-3.0.4;     pecl install redis-3.1.6;     docker-php-ext-enable apcu redis memcached;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*;         {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         chown -R www-data:root /var/www/html;     chmod -R g=u /var/www/html
# Tue, 06 Feb 2018 09:43:33 GMT
VOLUME [/var/www/html]
# Tue, 06 Feb 2018 09:43:35 GMT
RUN a2enmod rewrite
# Tue, 06 Feb 2018 09:53:48 GMT
ENV NEXTCLOUD_VERSION=12.0.5
# Tue, 06 Feb 2018 09:54:15 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Tue, 06 Feb 2018 09:54:16 GMT
COPY multi:b680850547a7d6e3b427bb289061cea91ea149b388bd13c63f961d11b2eda4c9 in / 
# Tue, 06 Feb 2018 09:54:17 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Tue, 06 Feb 2018 09:54:18 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 06 Feb 2018 09:54:19 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:7e6d91e96b32c4999458c6c0cda42f920e41aab0cfbf3153f6e013b222bf084d`  
		Last Modified: Tue, 12 Dec 2017 18:39:54 GMT  
		Size: 49.9 MB (49926676 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c8ee9610c809e6d2cfa5b61b3a45f6eb4705cf6c0eceabe5e8d63f713dfa2b3`  
		Last Modified: Wed, 20 Dec 2017 05:12:16 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e012cccb8aaf979c4f41c3c82588ed8c2a189ff2596f0baf0720141fd77ed39b`  
		Last Modified: Thu, 04 Jan 2018 05:18:21 GMT  
		Size: 62.5 MB (62543804 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8046c037fcf61f0fb100a40e965687d3961e99d8974c11b059f64d34b4d504de`  
		Last Modified: Thu, 04 Jan 2018 05:17:57 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12e1b629fa9abd1e98d4898cf59a6b052f3840c66040295b295021db1f5644f6`  
		Last Modified: Thu, 04 Jan 2018 05:19:29 GMT  
		Size: 4.1 MB (4124290 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9cc9e9e484dfb7f8198f79f8c13d04ccb998e44ea3454f35711ec1097a4596f`  
		Last Modified: Thu, 04 Jan 2018 05:19:30 GMT  
		Size: 1.2 KB (1246 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6dedd5c448cdf9038fff6f55fcc5ed17f2d0c3f6470dc14e182ce74a288b7cce`  
		Last Modified: Thu, 04 Jan 2018 05:19:27 GMT  
		Size: 434.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35045dcc734b45bf8b12aa8e3e24b383b0c64c9b557d34e0ddc54e58fabf2b03`  
		Last Modified: Thu, 04 Jan 2018 05:19:27 GMT  
		Size: 231.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2e4b70b5d14425c120198b6fce12d03f6a70357909b5ddbc83a4799a6016f8a`  
		Last Modified: Thu, 04 Jan 2018 05:19:26 GMT  
		Size: 487.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a123e225a3c8e51f9782a272114a107101810990ded8ca4ce6e745e91c66d39`  
		Last Modified: Tue, 09 Jan 2018 05:37:34 GMT  
		Size: 12.5 MB (12546056 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc39128b7818008e487cd734ab16c0eae02db292e857c98fdedcad12376b68a7`  
		Last Modified: Tue, 09 Jan 2018 05:37:31 GMT  
		Size: 503.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc45b9a8e93a42a913bae87080e32b79122e3988236418022607bd90c1295b73`  
		Last Modified: Tue, 09 Jan 2018 05:37:37 GMT  
		Size: 13.3 MB (13291659 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cb61955d1b3696d4b92954e0d6e349f6318fd77eb7864c3d0e057dc049dc880`  
		Last Modified: Tue, 09 Jan 2018 05:37:31 GMT  
		Size: 2.2 KB (2190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2fcec7113f3a1855e8a3481f5b112860d46d87771f48cdd2dedaef9893a7455`  
		Last Modified: Tue, 09 Jan 2018 05:37:31 GMT  
		Size: 906.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a108d9f246a413765ae2c48731cc5430e2b3a11e78607cd35451c9fba9d586d7`  
		Last Modified: Tue, 06 Feb 2018 09:55:36 GMT  
		Size: 18.6 MB (18646999 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:398bb5b8cd32428612780d768bc6f338a7e8928d6d84b58230c5acae8f44cb85`  
		Last Modified: Tue, 06 Feb 2018 09:55:29 GMT  
		Size: 312.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c667bfdc7a299c45baaf6d4a00fe76f8644563454944edc5b5f3bb956926323`  
		Last Modified: Tue, 06 Feb 2018 09:58:17 GMT  
		Size: 48.5 MB (48528940 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f7e3712a21e9c72ee4b9d2620491ced60214ee267a04453f803dd58a171cae44`  
		Last Modified: Tue, 06 Feb 2018 09:57:58 GMT  
		Size: 998.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c18dcff5b0ba9da983ee01b69dee72ccbd9d3202a303bc62e4dbce50432721b1`  
		Last Modified: Tue, 06 Feb 2018 09:57:58 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nextcloud:latest` - linux; 386

```console
$ docker pull nextcloud@sha256:9fc316efeff2bc3b4ef95707b472d3af2d7c9d5dde99c3b8730b99b9b6503f62
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **233.8 MB (233795102 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:82c93dd8d5f5e5a5a5b175e8907d656371b35615e5a24a28f45d71a4c5eea690`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 12 Dec 2017 14:19:55 GMT
ADD file:235a40e05b677eb2ae7e7a3cc5cbb0cda242ff15dddb87cb8dc9bb0cd2d6aed8 in / 
# Tue, 12 Dec 2017 14:19:55 GMT
CMD ["bash"]
# Wed, 20 Dec 2017 09:54:02 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Wed, 20 Dec 2017 09:54:03 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Thu, 04 Jan 2018 11:19:18 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Thu, 04 Jan 2018 11:20:27 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 04 Jan 2018 11:20:28 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 04 Jan 2018 11:39:55 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Thu, 04 Jan 2018 11:39:55 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Thu, 04 Jan 2018 11:39:56 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Thu, 04 Jan 2018 11:39:57 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Thu, 04 Jan 2018 11:40:09 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Thu, 04 Jan 2018 11:40:10 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Thu, 04 Jan 2018 11:40:11 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Thu, 04 Jan 2018 11:40:22 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Thu, 04 Jan 2018 11:40:23 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Thu, 04 Jan 2018 11:40:23 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 11:40:23 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 11:40:23 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 09 Jan 2018 14:44:03 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Tue, 09 Jan 2018 14:44:04 GMT
ENV PHP_VERSION=7.1.13
# Tue, 09 Jan 2018 14:44:04 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 14:44:04 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Tue, 09 Jan 2018 14:44:45 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Tue, 09 Jan 2018 14:44:53 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 14:49:41 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 14:55:03 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Tue, 09 Jan 2018 14:55:03 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 14:55:04 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Tue, 09 Jan 2018 14:55:04 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 14:55:04 GMT
EXPOSE 80/tcp
# Tue, 09 Jan 2018 14:55:05 GMT
CMD ["apache2-foreground"]
# Tue, 06 Feb 2018 09:58:50 GMT
RUN set -ex;     apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;         savedAptMark="$(apt-mark showmanual)";         apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install gd exif intl mbstring mcrypt ldap mysqli opcache pdo_mysql pdo_pgsql pgsql zip pcntl;     pecl install APCu-5.1.9;     pecl install memcached-3.0.4;     pecl install redis-3.1.6;     docker-php-ext-enable apcu redis memcached;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*;         {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         chown -R www-data:root /var/www/html;     chmod -R g=u /var/www/html
# Tue, 06 Feb 2018 09:58:51 GMT
VOLUME [/var/www/html]
# Tue, 06 Feb 2018 09:58:52 GMT
RUN a2enmod rewrite
# Tue, 06 Feb 2018 10:26:05 GMT
ENV NEXTCLOUD_VERSION=12.0.5
# Tue, 06 Feb 2018 10:26:27 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Tue, 06 Feb 2018 10:26:28 GMT
COPY multi:b680850547a7d6e3b427bb289061cea91ea149b388bd13c63f961d11b2eda4c9 in / 
# Tue, 06 Feb 2018 10:26:28 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Tue, 06 Feb 2018 10:26:29 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 06 Feb 2018 10:26:29 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:d99577c7ee3d4d82987bedaeb10f3244ff7e19e41c5259bb8cac00568d1c4271`  
		Last Modified: Tue, 12 Dec 2017 14:46:26 GMT  
		Size: 52.8 MB (52777369 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02e78f833def8147f02d3b46ee9fa9bd4b7dc76472e6f78b04a44c617456a787`  
		Last Modified: Thu, 21 Dec 2017 13:06:53 GMT  
		Size: 226.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:800a874680e6297c686a886a24dc8a58968a7f1b19ee0feec2b43fda5fff070c`  
		Last Modified: Thu, 04 Jan 2018 15:03:55 GMT  
		Size: 81.5 MB (81549738 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfe30bfdc208a3fee8ee073c6c85f98e1f74f9013ebc071962e4a635e51f717a`  
		Last Modified: Thu, 04 Jan 2018 15:03:30 GMT  
		Size: 184.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:670e09b0df737aa4a43f58cd8ef4e484e74663484b520d9bc85ec7de4ef67499`  
		Last Modified: Thu, 04 Jan 2018 15:06:32 GMT  
		Size: 4.7 MB (4650272 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3cae5c720c42aa72095c99a80ce0af30c04b65d874fc8c4de59326949f77800`  
		Last Modified: Thu, 04 Jan 2018 15:06:29 GMT  
		Size: 1.2 KB (1248 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f7aceca139d3c08e96ababe2cfb8f5107f587fa1b219999b09d9301b8c1789e0`  
		Last Modified: Thu, 04 Jan 2018 15:06:30 GMT  
		Size: 430.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70cf5007ffe6910e081df4574fa67d5081e3d88093697198d89f43cf00d0d1bf`  
		Last Modified: Thu, 04 Jan 2018 15:06:29 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e04ca694b7e7515e326813a2bedcc6fc09c421bc32040de9675565cd86a5103`  
		Last Modified: Thu, 04 Jan 2018 15:06:29 GMT  
		Size: 488.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0919698e5dbc4031da03dfab8e3bd86984dac987f513c1a4d5474e0ec70c105e`  
		Last Modified: Tue, 09 Jan 2018 22:27:16 GMT  
		Size: 12.5 MB (12547489 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87ec6e83a31753b3285758e0a715e4b41fbfa931eade4a0e69ee37a3dd99f840`  
		Last Modified: Tue, 09 Jan 2018 22:27:14 GMT  
		Size: 502.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:459a0add8a06f4f12f28007f31032c2938627b2a1fb5a48658bba37bb072b4bd`  
		Last Modified: Tue, 09 Jan 2018 22:27:20 GMT  
		Size: 14.7 MB (14657175 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34f0c691b41115790f5e82e7fbabae70a979eabd3460838f1579d6ca90e6ce9b`  
		Last Modified: Tue, 09 Jan 2018 22:27:14 GMT  
		Size: 2.2 KB (2189 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb9a3b1f21b40df00cccfcf3226b759cc8697111bc22c64161f1be29e4e650ba`  
		Last Modified: Tue, 09 Jan 2018 22:27:13 GMT  
		Size: 905.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea82bc087cab8c4b649aa59bd0ef2bbaec6cc29653c12a001d914243821ade72`  
		Last Modified: Tue, 06 Feb 2018 10:49:45 GMT  
		Size: 19.1 MB (19075510 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69221001cc6e0fbd6df51ca7260fccea2cbcba6f802039e60271c4700b84d3e3`  
		Last Modified: Tue, 06 Feb 2018 10:49:40 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:684066af888f9619d31306842ceeafbaea9d32f79ce8ad1be59dd5cba272b369`  
		Last Modified: Tue, 06 Feb 2018 12:05:31 GMT  
		Size: 48.5 MB (48528981 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73b3d2c7df553a1f36bc78045ef7e66181ef4872c7877149c65e8c3c8c86bde6`  
		Last Modified: Tue, 06 Feb 2018 12:05:01 GMT  
		Size: 997.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e23caeaf5a7df051f721f7146abc1a9a57144056c97868ce45e9c1a1c6f3768f`  
		Last Modified: Tue, 06 Feb 2018 12:05:01 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nextcloud:latest` - linux; ppc64le

```console
$ docker pull nextcloud@sha256:08648fa40abbb25c6ec2ff4e559de1a86f64112f364cc0b23f1b05e58ecdf58c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **218.4 MB (218431098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:aaac1d7a211acd32229bfe507d7edf42a0d5fdc8c7adb2fa8ddeb189499eeaf5`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 12 Dec 2017 01:32:54 GMT
ADD file:a66da0d75afce2da6174648a861b98f8e9999028d4f04a59288ca92a090256e2 in / 
# Tue, 12 Dec 2017 01:32:56 GMT
CMD ["bash"]
# Wed, 20 Dec 2017 10:17:49 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Wed, 20 Dec 2017 10:17:50 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Thu, 04 Jan 2018 10:24:24 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Thu, 04 Jan 2018 10:24:25 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Thu, 04 Jan 2018 10:24:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Thu, 04 Jan 2018 10:31:00 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Thu, 04 Jan 2018 10:31:01 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Thu, 04 Jan 2018 10:31:05 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Thu, 04 Jan 2018 10:31:15 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Thu, 04 Jan 2018 10:31:23 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Thu, 04 Jan 2018 10:31:31 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Thu, 04 Jan 2018 10:31:40 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Thu, 04 Jan 2018 10:31:45 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Thu, 04 Jan 2018 10:31:47 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Thu, 04 Jan 2018 10:31:49 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 10:31:50 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Thu, 04 Jan 2018 10:31:52 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 09 Jan 2018 10:45:48 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Tue, 09 Jan 2018 10:45:49 GMT
ENV PHP_VERSION=7.1.13
# Tue, 09 Jan 2018 10:45:51 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 10:45:52 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Tue, 09 Jan 2018 10:46:29 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Tue, 09 Jan 2018 10:46:30 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 10:50:29 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 10:50:30 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Tue, 09 Jan 2018 10:50:31 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 10:50:33 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Tue, 09 Jan 2018 10:50:34 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 10:50:35 GMT
EXPOSE 80/tcp
# Tue, 09 Jan 2018 10:50:36 GMT
CMD ["apache2-foreground"]
# Tue, 06 Feb 2018 14:26:00 GMT
RUN set -ex;     apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;         savedAptMark="$(apt-mark showmanual)";         apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install gd exif intl mbstring mcrypt ldap mysqli opcache pdo_mysql pdo_pgsql pgsql zip pcntl;     pecl install APCu-5.1.9;     pecl install memcached-3.0.4;     pecl install redis-3.1.6;     docker-php-ext-enable apcu redis memcached;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*;         {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         chown -R www-data:root /var/www/html;     chmod -R g=u /var/www/html
# Tue, 06 Feb 2018 14:26:02 GMT
VOLUME [/var/www/html]
# Tue, 06 Feb 2018 14:26:11 GMT
RUN a2enmod rewrite
# Tue, 06 Feb 2018 14:34:40 GMT
ENV NEXTCLOUD_VERSION=12.0.5
# Tue, 06 Feb 2018 14:35:06 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Tue, 06 Feb 2018 14:35:15 GMT
COPY multi:b680850547a7d6e3b427bb289061cea91ea149b388bd13c63f961d11b2eda4c9 in / 
# Tue, 06 Feb 2018 14:35:18 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Tue, 06 Feb 2018 14:35:20 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 06 Feb 2018 14:35:21 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:75c28926027fc0404a0d21450475473243a59e8fc55443a62d1d744693ec19e9`  
		Last Modified: Tue, 12 Dec 2017 01:38:17 GMT  
		Size: 51.8 MB (51808999 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8bfe49b2829dba0fc576421805ceaeed1e1067c0f07d3052f0a36ade1e7a3e8`  
		Last Modified: Wed, 20 Dec 2017 11:27:45 GMT  
		Size: 229.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb4b841e0c81a4deae0ce70ceb87edca011c7f94cef5a28df34a4bc79d781b27`  
		Last Modified: Thu, 04 Jan 2018 11:33:42 GMT  
		Size: 67.9 MB (67864808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9e94de055a6a25f5d96e3d6ceeb45cd49cda1dcb52f2ba2300553431f08c6061`  
		Last Modified: Thu, 04 Jan 2018 11:33:23 GMT  
		Size: 213.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37e6db937d3933c2a7d525cbe30a04a17b02765c35950c8cc4abd671be7181dd`  
		Last Modified: Thu, 04 Jan 2018 11:34:34 GMT  
		Size: 4.3 MB (4332457 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eee6aab5708d2b433b3e69843a56180bb5f5cbb4bec5cd28d8f63e7e69772b11`  
		Last Modified: Thu, 04 Jan 2018 11:34:33 GMT  
		Size: 1.3 KB (1282 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64bfc0caf35aeb16ea3e1d52cb85a04122a065eb7c4eb8fa9260b4a92902b509`  
		Last Modified: Thu, 04 Jan 2018 11:34:31 GMT  
		Size: 475.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:352cbb6f7eb91abb49ff5578d52b0b60291230910551c31ef073dda2d2acd2cc`  
		Last Modified: Thu, 04 Jan 2018 11:34:31 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61f99636d6db5b9c95ee8178d63237bffbc79c46de009c7dce3d276bf0c888cb`  
		Last Modified: Thu, 04 Jan 2018 11:34:31 GMT  
		Size: 516.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d029894c0b52cf303472d87a2ece1f192ee76a57c6b449b382ebb4f20745fc56`  
		Last Modified: Tue, 09 Jan 2018 11:52:34 GMT  
		Size: 12.5 MB (12546476 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4924a9eaea8039870da7487a2729ac942e1cee7b722ee4ce78f73c2459315635`  
		Last Modified: Tue, 09 Jan 2018 11:52:33 GMT  
		Size: 502.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:266ef59bee7a05d7687152ac882b23735b3bf7d329f239b5e869cdfe8d2d929a`  
		Last Modified: Tue, 09 Jan 2018 11:52:37 GMT  
		Size: 14.1 MB (14113324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9635b7ec1204d36c0ee8535c62831131c6ab4f63fc79f1856f95d2d3587f73c2`  
		Last Modified: Tue, 09 Jan 2018 11:52:33 GMT  
		Size: 2.2 KB (2189 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aad074a72700d36ff6ab6cb426b5530560263cceef6039bbae6f2e95783636d2`  
		Last Modified: Tue, 09 Jan 2018 11:52:33 GMT  
		Size: 907.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b3ffe568d776388cbb46039cf03db02b894e116ef402d2a83d1533feb13d806`  
		Last Modified: Tue, 06 Feb 2018 14:36:30 GMT  
		Size: 19.2 MB (19227419 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0edfc62e2f69a9cb1c7fe31bb4ffe34b1b9354bbf9896a126b02fc731a37ebf9`  
		Last Modified: Tue, 06 Feb 2018 14:36:24 GMT  
		Size: 314.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c3d09eacf149697b0d69b42349004ad95f889488ebf5c30fccbd007e4ee1c58`  
		Last Modified: Tue, 06 Feb 2018 14:38:09 GMT  
		Size: 48.5 MB (48528911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8ff656da62ae96df7f68d5ff07c7e40b3a488a395024081bbe8cd3eb962f629`  
		Last Modified: Tue, 06 Feb 2018 14:37:54 GMT  
		Size: 998.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e6947f196f6d263915e1e2a798c0aeb5ee25a659dba6434a26f9f2d774d2c6b`  
		Last Modified: Tue, 06 Feb 2018 14:37:54 GMT  
		Size: 849.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `nextcloud:latest` - linux; s390x

```console
$ docker pull nextcloud@sha256:c460c257c37f01622dead2ecc606f5528d7b22f36cdb774f32e6787701cfaf5b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **213.9 MB (213922799 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0877a442df938767a43733b8177f2fe6fea7f0cf2b8b05ad89c9811f49fd6904`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 12 Dec 2017 06:22:40 GMT
ADD file:f85dc45c68f6f29cc10d6ef236674dedc10522f11b6fa2e8a6b10a4409ca0bc7 in / 
# Tue, 12 Dec 2017 06:22:40 GMT
CMD ["bash"]
# Sun, 07 Jan 2018 05:49:28 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Sun, 07 Jan 2018 05:49:31 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Sun, 07 Jan 2018 05:50:19 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Sun, 07 Jan 2018 05:50:19 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Sun, 07 Jan 2018 05:50:19 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Sun, 07 Jan 2018 05:54:05 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Sun, 07 Jan 2018 05:54:05 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Sun, 07 Jan 2018 05:54:06 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Sun, 07 Jan 2018 05:54:06 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Sun, 07 Jan 2018 05:54:07 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Sun, 07 Jan 2018 05:54:07 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Sun, 07 Jan 2018 05:54:08 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Sun, 07 Jan 2018 05:54:08 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Sun, 07 Jan 2018 05:54:08 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Sun, 07 Jan 2018 05:54:08 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sun, 07 Jan 2018 05:54:09 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sun, 07 Jan 2018 05:54:09 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 09 Jan 2018 18:25:37 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Tue, 09 Jan 2018 18:25:38 GMT
ENV PHP_VERSION=7.1.13
# Tue, 09 Jan 2018 18:25:38 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.13.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.13.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 18:25:38 GMT
ENV PHP_SHA256=1a0b3f2fb61959b57a3ee01793a77ed3f19bde5aa90c43dcacc85ea32f64fc10 PHP_MD5=
# Tue, 09 Jan 2018 18:25:52 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Tue, 09 Jan 2018 18:25:52 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 18:27:44 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 18:27:44 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Tue, 09 Jan 2018 18:27:44 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 18:27:45 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Tue, 09 Jan 2018 18:27:45 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 18:27:45 GMT
EXPOSE 80/tcp
# Tue, 09 Jan 2018 18:27:45 GMT
CMD ["apache2-foreground"]
# Tue, 06 Feb 2018 00:03:33 GMT
RUN set -ex;     apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;         savedAptMark="$(apt-mark showmanual)";         apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install gd exif intl mbstring mcrypt ldap mysqli opcache pdo_mysql pdo_pgsql pgsql zip pcntl;     pecl install APCu-5.1.9;     pecl install memcached-3.0.4;     pecl install redis-3.1.6;     docker-php-ext-enable apcu redis memcached;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*;         {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         chown -R www-data:root /var/www/html;     chmod -R g=u /var/www/html
# Tue, 06 Feb 2018 00:03:33 GMT
VOLUME [/var/www/html]
# Tue, 06 Feb 2018 00:03:34 GMT
RUN a2enmod rewrite
# Tue, 06 Feb 2018 00:10:12 GMT
ENV NEXTCLOUD_VERSION=12.0.5
# Tue, 06 Feb 2018 00:11:51 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/releases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Tue, 06 Feb 2018 00:11:51 GMT
COPY multi:b680850547a7d6e3b427bb289061cea91ea149b388bd13c63f961d11b2eda4c9 in / 
# Tue, 06 Feb 2018 00:11:52 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Tue, 06 Feb 2018 00:11:52 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 06 Feb 2018 00:11:52 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:98cfcbfa76c6d2a42223dc7a44505bdd260000bffd3ecbb983cb33213128499b`  
		Last Modified: Tue, 12 Dec 2017 06:28:05 GMT  
		Size: 52.8 MB (52790322 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:911220ecf750572b6d8ef6e23491076cb4e8040d9df12400f0182f4672620a8a`  
		Last Modified: Sun, 07 Jan 2018 06:31:48 GMT  
		Size: 229.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea688ade1d181978d1b69c1e63f4d27ad67ffd7abb20fb10f76b004fe5b086f0`  
		Last Modified: Sun, 07 Jan 2018 06:32:00 GMT  
		Size: 61.8 MB (61798486 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:badb354f38748aa6befa8863d2f8510f60f06a4246ed3cb1ef28318dba13083e`  
		Last Modified: Sun, 07 Jan 2018 06:31:47 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63defb1e6316018f89c6e567dc81b85d76ab6c124b54e9836dbaf65a5af61568`  
		Last Modified: Sun, 07 Jan 2018 06:32:52 GMT  
		Size: 4.5 MB (4487907 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bcd529d3abc31f6627e9af930a77377b506dc545f9d5ddfa4af3e4fe94f271d7`  
		Last Modified: Sun, 07 Jan 2018 06:32:50 GMT  
		Size: 1.2 KB (1247 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c301f2d0c7482bcfd9a1a53341a4bdafb2de8d12c3b5ed9d07f2c34b99644c58`  
		Last Modified: Sun, 07 Jan 2018 06:32:50 GMT  
		Size: 433.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d4872bfc0cf8ddcbd3e9eb1f42edc5f5156950065d25ab0cb8d561418cfaf02`  
		Last Modified: Sun, 07 Jan 2018 06:32:49 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c12a9913f61db864f213fb16cc27f45d5c6e6cd2a17fbb5fda1c6899843a633`  
		Last Modified: Sun, 07 Jan 2018 06:32:49 GMT  
		Size: 488.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a296bbcd22729fc07b92a8abfa72b995becb45add13fe99634b477fe805799d`  
		Last Modified: Tue, 09 Jan 2018 18:59:22 GMT  
		Size: 12.5 MB (12545639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:537c839e235abbd444dd3c66130c0602eee3d13685b85b4b6680a896d582904f`  
		Last Modified: Tue, 09 Jan 2018 18:59:20 GMT  
		Size: 500.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:523069ebf8c18fb63b1a3bdc3e43905e8872fb4ffedc2abea44d8dcb85cad1ab`  
		Last Modified: Tue, 09 Jan 2018 18:59:23 GMT  
		Size: 14.5 MB (14508908 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bf863d2e7da7f0957ac8c59856b1e8e4d6d8ca2aa16554da6305ef76966b6f2`  
		Last Modified: Tue, 09 Jan 2018 18:59:20 GMT  
		Size: 2.2 KB (2189 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4583c3d262f18f82e7d2c809baec5ea5398b9593db0eb4abee8592f6c026b9d3`  
		Last Modified: Tue, 09 Jan 2018 18:59:20 GMT  
		Size: 905.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce6ea9c00e1b3e2042fb0f8e90ac921482c4af6cd43d651a20ca3d45498cc5a4`  
		Last Modified: Tue, 06 Feb 2018 00:13:54 GMT  
		Size: 19.3 MB (19254045 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb8779a0fe208bd502835da66b6518038858f746adfeba8e2b7e7ce8389e316a`  
		Last Modified: Tue, 06 Feb 2018 00:13:50 GMT  
		Size: 317.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed553034b560127f8f3980139ef7b52474c3a66d0de6106351ff7cf4dfa24cb2`  
		Last Modified: Tue, 06 Feb 2018 00:14:46 GMT  
		Size: 48.5 MB (48528922 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dfdc5cb225fc765ec4d8e96dd97a71683ba22bd621a80727139b02b0ada705ce`  
		Last Modified: Tue, 06 Feb 2018 00:14:42 GMT  
		Size: 998.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d5aed20278a605968cb25db4306a5e38769d6c0c32255dc2746a2b40d73ff3f1`  
		Last Modified: Tue, 06 Feb 2018 00:14:38 GMT  
		Size: 852.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
