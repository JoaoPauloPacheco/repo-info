## `golang:rc-nanoserver-sac2016`

```console
$ docker pull golang@sha256:fecff2b8b145c4be68f9816712c7d7c61cc956d583c81254040ec0d8d4611b83
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.1884; amd64

### `golang:rc-nanoserver-sac2016` - windows version 10.0.14393.1884; amd64

```console
$ docker pull golang@sha256:7edb97a29efada6475b3d7d573f5e84b7fbe4bc16af62619abcbaf5197bd523e
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **603.2 MB (603200895 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2c1992c5bdc23631e182401bb2ea7f474a2fcb6f710743ba915cae2ae38caea8`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Mon, 13 Nov 2017 21:41:41 GMT
RUN Install update 10.0.14393.1884
# Wed, 15 Nov 2017 03:21:45 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Wed, 15 Nov 2017 03:21:46 GMT
ENV GOPATH=C:\gopath
# Wed, 15 Nov 2017 03:22:24 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Sat, 09 Dec 2017 03:32:03 GMT
ENV GOLANG_VERSION=1.10beta1
# Sat, 09 Dec 2017 03:40:15 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'ff2789b7baf33f87111d30bac81ac1ae19dcc16bdd75553f9b5aceda14733a40'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Sat, 09 Dec 2017 03:40:17 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:53a0ccfb7e6fe326c54359c802287bbe5435ac269242e4883f85a1f305e1d0cb`  
		Last Modified: Mon, 13 Nov 2017 21:41:41 GMT  
		Size: 148.0 MB (147993264 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:6391c8dfb28a8f45d62407ef2c1a147f2ea682f9352a6e736a21b3502f24d922`  
		Last Modified: Wed, 15 Nov 2017 10:26:45 GMT  
		Size: 945.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91148436619439d6fb249446bb0a082ae737c67580c3a0c8c75ec2984c905908`  
		Last Modified: Wed, 15 Nov 2017 21:08:32 GMT  
		Size: 831.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e75d25db7ea2288538a1b9a82c433cdd9c6dec70ebdf8f259cb6224ddd83c63`  
		Last Modified: Wed, 15 Nov 2017 21:08:33 GMT  
		Size: 838.7 KB (838706 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3247988fd19e00bd331fef70106720757fe53e582da6a112730c9e1a13b0672f`  
		Last Modified: Sat, 09 Dec 2017 03:43:24 GMT  
		Size: 940.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:844dd63f05ca78ac3e696593a8e74da4105fbc2ae66fc1ad7e9e1439c17b333d`  
		Last Modified: Sat, 09 Dec 2017 03:44:14 GMT  
		Size: 201.7 MB (201674059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e456d3fafe6fad2da386ba0a6b4c7932fe90d238aab6c579d0005aa00bde950`  
		Last Modified: Sat, 09 Dec 2017 03:43:25 GMT  
		Size: 1.1 KB (1148 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip