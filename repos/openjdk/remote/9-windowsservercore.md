## `openjdk:9-windowsservercore`

```console
$ docker pull openjdk@sha256:52cc48f9503a519b757b589e1b2f32b772cba7d1da031d543f0d93c5d2da2c89
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64
	-	windows version 10.0.16299.192; amd64

### `openjdk:9-windowsservercore` - windows version 10.0.14393.2007; amd64

```console
$ docker pull openjdk@sha256:2456acd89ddc9abe63f6da24d5f27af7f69e223e5966896ac7376a4bc5e1cccc
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.6 GB (5575479759 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a7ce61d6819459f95f168485fa52f9dd6657597e239342a977e0d027020e5231`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:32 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:02:17 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 05 Jan 2018 10:02:18 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Fri, 05 Jan 2018 10:03:43 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Thu, 01 Feb 2018 10:02:55 GMT
ENV JAVA_VERSION=9.0.4
# Thu, 01 Feb 2018 10:02:56 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.4-1
# Thu, 01 Feb 2018 10:02:57 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.4-1.b11.ojdkbuild.windows.x86_64.zip
# Thu, 01 Feb 2018 10:02:57 GMT
ENV JAVA_OJDKBUILD_SHA256=1333ab5bccc20e9043f0593b001825cbfa141f0e0c850d877af6b8e2c990cb47
# Thu, 01 Feb 2018 10:05:39 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Thu, 01 Feb 2018 10:05:41 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 13 Dec 2016 10:53:31 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:449343c9d7e2919413898dc8a7e8780ef164b76a3b9dd19de104706edf05113a`  
		Last Modified: Thu, 04 Jan 2018 20:07:32 GMT  
		Size: 1.3 GB (1304019288 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:c86d0434e36d69287bea586f96045245d5ee4f04e4e2a5edf6881dbbfdc628c3`  
		Last Modified: Fri, 05 Jan 2018 10:13:30 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8043493a566c4b6517006bcc781208f6a6ed6679b087349f1c3abcfbc7c5bbc0`  
		Last Modified: Fri, 05 Jan 2018 10:13:30 GMT  
		Size: 1.2 KB (1191 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9863b66916588215ba59a3ee437280bdacb3e25f890c1f8886ddc754f6ed36b1`  
		Last Modified: Fri, 05 Jan 2018 10:13:32 GMT  
		Size: 4.9 MB (4932063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8859ee080bcc575e0ecb4612f333f071644553f5d5be8ea7cf1113da5f899988`  
		Last Modified: Thu, 01 Feb 2018 10:11:26 GMT  
		Size: 1.2 KB (1170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7558786bc84ae0c2ee28de34689206e7daaca4099580df98b815f04e487fd598`  
		Last Modified: Thu, 01 Feb 2018 10:11:23 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea41222362e6840aea544d941596e3fb28694b0ee3b035985fd7cbb09b92945b`  
		Last Modified: Thu, 01 Feb 2018 10:11:23 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6e13a8ddc28f6b7b7519deb00963505b1a2a17ea62b6d8c2aaa75913bacec7c`  
		Last Modified: Thu, 01 Feb 2018 10:11:23 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbd103348becfe55570b0f8ba935494da913b71dc90201028180f40d3fbc2d6b`  
		Last Modified: Thu, 01 Feb 2018 10:11:48 GMT  
		Size: 196.5 MB (196534172 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3c2a0d023771f6b624e0356e5714ad425af27c94cfc0d516afebcfa5e12767c`  
		Last Modified: Thu, 01 Feb 2018 10:11:25 GMT  
		Size: 1.2 KB (1190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:9-windowsservercore` - windows version 10.0.16299.192; amd64

```console
$ docker pull openjdk@sha256:69f3a5683fe0eab62382763bafc73fd41fa7e1e8f6833cd3a15ba13d05f81ac9
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.2 GB (3164778641 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:82cd99da0aff43a7c86a87c8db6a083c975b2ec299ed1552d593e7530e2ced16`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Wed, 03 Jan 2018 04:46:54 GMT
RUN Install update 10.0.16299.192
# Mon, 08 Jan 2018 17:27:32 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Mon, 08 Jan 2018 17:27:33 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Mon, 08 Jan 2018 17:29:27 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Thu, 01 Feb 2018 10:05:52 GMT
ENV JAVA_VERSION=9.0.4
# Thu, 01 Feb 2018 10:05:53 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.4-1
# Thu, 01 Feb 2018 10:05:54 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.4-1.b11.ojdkbuild.windows.x86_64.zip
# Thu, 01 Feb 2018 10:05:55 GMT
ENV JAVA_OJDKBUILD_SHA256=1333ab5bccc20e9043f0593b001825cbfa141f0e0c850d877af6b8e2c990cb47
# Thu, 01 Feb 2018 10:08:17 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Thu, 01 Feb 2018 10:08:18 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:9f887ccb8077bdc1f1fedd2da6066bb3542c528f5d103b40659ac25785ba4b9b`  
		Last Modified: Fri, 05 Jan 2018 19:38:30 GMT  
		Size: 689.7 MB (689720734 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:189c9822c1fc60043703fa16f44b1cab80d3a786d35bd6b61628d2b3f1fb9635`  
		Last Modified: Mon, 08 Jan 2018 17:34:16 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7a9ce91e9e577e170b629751aa0ed697e6cb3bd7ceb0ee3c4a1f1cd6ee3c2c0`  
		Last Modified: Mon, 08 Jan 2018 17:34:15 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54cd82960b9743e4501d1aa71a781fc291c73a46514cbdf850807efaca102c6f`  
		Last Modified: Mon, 08 Jan 2018 17:34:17 GMT  
		Size: 4.6 MB (4552415 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cced5f878ae256fcd39bfdf6ac424ae05b92dbdb22ba624dda3af3c7d07dceb8`  
		Last Modified: Thu, 01 Feb 2018 10:12:15 GMT  
		Size: 1.2 KB (1179 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb81bb96e3cfff3fab65f4efa03abb04089f0def9f4aae10abdb89dae81e6fe0`  
		Last Modified: Thu, 01 Feb 2018 10:12:13 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9addc7a8f0d46d72642508e1d47dfdfe010e50923d9617af0cce5e58e2fc19ff`  
		Last Modified: Thu, 01 Feb 2018 10:12:14 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75b08d8ecbec37c90e762d8b2df3ccc3c5ea08e63e4b88cbf2721f1687d96d9c`  
		Last Modified: Thu, 01 Feb 2018 10:12:13 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8b6d178dc1d49ffde3da9e040fd39e3e9d09594f214cad061b93bf5aea77341`  
		Last Modified: Thu, 01 Feb 2018 10:12:36 GMT  
		Size: 196.2 MB (196196553 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1b0bfe644dbb98408341a0f51e053cd07729d146ee6cf8fcdf294d938848e7da`  
		Last Modified: Thu, 01 Feb 2018 10:12:13 GMT  
		Size: 1.2 KB (1194 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
