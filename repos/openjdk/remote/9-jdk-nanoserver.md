## `openjdk:9-jdk-nanoserver`

```console
$ docker pull openjdk@sha256:836ed9f886ee9c27fe9e337f1abb1c34507b6a388a466c299fd94e105ff9a6da
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64

### `openjdk:9-jdk-nanoserver` - windows version 10.0.14393.2007; amd64

```console
$ docker pull openjdk@sha256:d13df9d1577c0a9ef4815092f2ac39b5e60162a33dca4152cf867a1ebc46d044
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **596.3 MB (596292772 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:744061e6ae8e9c45b6d2a9d23db27cf9975ac90e1c572da56551b22517c7edc2`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:02 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:05:51 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 05 Jan 2018 10:05:52 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Fri, 05 Jan 2018 10:06:59 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Thu, 01 Feb 2018 10:08:34 GMT
ENV JAVA_VERSION=9.0.4
# Thu, 01 Feb 2018 10:08:35 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.4-1
# Thu, 01 Feb 2018 10:08:36 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.4-1.b11.ojdkbuild.windows.x86_64.zip
# Thu, 01 Feb 2018 10:08:37 GMT
ENV JAVA_OJDKBUILD_SHA256=1333ab5bccc20e9043f0593b001825cbfa141f0e0c850d877af6b8e2c990cb47
# Thu, 01 Feb 2018 10:10:24 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Thu, 01 Feb 2018 10:10:26 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:764aee428c28f0935a6ded2a2730509373e1357648795b609b911dd46aa06257`  
		Last Modified: Thu, 04 Jan 2018 20:07:02 GMT  
		Size: 150.4 MB (150357748 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:954c60e18caf74c1c34ea38a04c2d8c7a2e4e2ae3658951596ace699a3894207`  
		Last Modified: Fri, 05 Jan 2018 10:14:14 GMT  
		Size: 922.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f7b6582b2ddc6eb91d5ab41b0e8486aa2bf55f233601cf5aef9b649e5ac11e1a`  
		Last Modified: Fri, 05 Jan 2018 10:14:14 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da7337715dda7f285d15244ca3b41290be3077379f614896a8d7ac302635ef27`  
		Last Modified: Fri, 05 Jan 2018 10:14:14 GMT  
		Size: 845.8 KB (845757 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca4583af4c49224fbb5eb17ab1a08757a125e997960b8759b3d077ed3e1d9466`  
		Last Modified: Thu, 01 Feb 2018 10:13:04 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a7e075e2e72d3dca836ce50cd0ecab3dfd583a08e6d364befb18b7167075004`  
		Last Modified: Thu, 01 Feb 2018 10:13:02 GMT  
		Size: 949.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b746dd1a3a667ca7921174f43d4683d20c30ac8117dc7da9e6b3dcd2b7ad7c3`  
		Last Modified: Thu, 01 Feb 2018 10:13:02 GMT  
		Size: 949.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87c7d80bd6c85e702e1cdd195e37260ef7ac0b97f8c9c8076240d2a680ee422e`  
		Last Modified: Thu, 01 Feb 2018 10:13:02 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c25d235203a606a06836b53b6953ec09655080d3c48fae8165ff232c6f2f29d1`  
		Last Modified: Thu, 01 Feb 2018 10:13:25 GMT  
		Size: 192.4 MB (192391670 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ccc4d08894d5d3c0d470963d0466a7ea6e969dd5a348088eb946a305568f7b7`  
		Last Modified: Thu, 01 Feb 2018 10:13:02 GMT  
		Size: 940.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
