## `golang:rc-nanoserver`

```console
$ docker pull golang@sha256:56474bdeeb164a0cccbaf4f169a1631eec21f50f42050f6b9924a63bf0f2d0fe
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64

### `golang:rc-nanoserver` - windows version 10.0.14393.2007; amd64

```console
$ docker pull golang@sha256:48a166375dd095c8e597da193af5881081b67c6f6f27cc0ff406ac20286df596
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **532.3 MB (532293298 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:03f529cd2ec419307912e6c04c7923d322ebf1276f818c312acd0c52664508d8`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:02 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:05:51 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Mon, 08 Jan 2018 18:26:16 GMT
ENV GOPATH=C:\gopath
# Mon, 08 Jan 2018 18:27:21 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Fri, 26 Jan 2018 03:54:29 GMT
ENV GOLANG_VERSION=1.10rc1
# Fri, 26 Jan 2018 03:59:08 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'f3730ee5ff779a2a0862e858b94b40423c613e91142be99e05e47953343326a8'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Fri, 26 Jan 2018 03:59:09 GMT
WORKDIR C:\gopath
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
	-	`sha256:a86e7fa28644d6145ab3a303bf625643f98fd573f0c038ccd2aed1d1a7de6a9a`  
		Last Modified: Mon, 08 Jan 2018 19:55:41 GMT  
		Size: 942.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c3e186accae51f0eeb18ba54d31934fbb1db4dc4adcae8b4bbc186ce83d476f`  
		Last Modified: Mon, 08 Jan 2018 19:55:43 GMT  
		Size: 856.7 KB (856654 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2b38c0c03298c9ab4a3d8b834ce45e745a0526b55fe35f71e0c6f371956d387`  
		Last Modified: Fri, 26 Jan 2018 04:01:52 GMT  
		Size: 956.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bbf2838907303de5f6816b59e7cc8db0d63d3e2140b24e675eb08e4b1c9f44b`  
		Last Modified: Fri, 26 Jan 2018 04:03:16 GMT  
		Size: 128.4 MB (128383918 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0378f536beb0ff94549772582bed8fdbac5c39d81c3d1a62d45c4e42083ab8ab`  
		Last Modified: Fri, 26 Jan 2018 04:01:52 GMT  
		Size: 1.2 KB (1156 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
