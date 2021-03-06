## `python:rc-windowsservercore-1709`

```console
$ docker pull python@sha256:5f151b432d52344e5c20453daff06b3d5996414410728d5726075e8756b40668
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.16299.192; amd64

### `python:rc-windowsservercore-1709` - windows version 10.0.16299.192; amd64

```console
$ docker pull python@sha256:0dc056edecd61c77a170778a2034cdc5abfd548ca00b5278569e45a4638ee08e
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.0 GB (3019746309 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e9c56087e84c5c8f8f0d8994d70be68da61ad33380cb463938781e28e3c1a720`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Wed, 03 Jan 2018 04:46:54 GMT
RUN Install update 10.0.16299.192
# Mon, 08 Jan 2018 17:27:32 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Wed, 10 Jan 2018 22:46:01 GMT
ENV PYTHON_VERSION=3.7.0a4
# Wed, 10 Jan 2018 22:46:01 GMT
ENV PYTHON_RELEASE=3.7.0
# Wed, 10 Jan 2018 22:49:55 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}-amd64.exe' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'python.exe'; 		Write-Host 'Installing ...'; 	Start-Process python.exe -Wait 		-ArgumentList @( 			'/quiet', 			'InstallAllUsers=1', 			'TargetDir=C:\Python', 			'PrependPath=1', 			'Shortcuts=0', 			'Include_doc=0', 			'Include_pip=0', 			'Include_test=0' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.exe -Force; 		Write-Host 'Complete.';
# Wed, 10 Jan 2018 22:49:56 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Wed, 10 Jan 2018 22:51:19 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Wed, 10 Jan 2018 22:51:20 GMT
CMD ["python"]
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
	-	`sha256:58a2d4acab24a165eac9a00969de2fa0430266caf666f4bf8f5ad66049c800bf`  
		Last Modified: Wed, 10 Jan 2018 22:52:48 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8ddf3bbbc9596ff014dbe2a04b9915807002b8f6a9a7b8bc179a0e5f99bde04`  
		Last Modified: Wed, 10 Jan 2018 22:52:45 GMT  
		Size: 1.2 KB (1188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccba0c971c49c062bd0835e83093ad59974f84b1a1babce82f5919f8a5ebc9a3`  
		Last Modified: Wed, 10 Jan 2018 22:53:00 GMT  
		Size: 46.8 MB (46766660 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:19a18728c2fe48b93ebfa2a8eef338e7f33cdc53807a08c86f154a40e9194d88`  
		Last Modified: Wed, 10 Jan 2018 22:52:45 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ad51d4a685f915a7e6e039fcc38f6ec8edeec4767dbe41a57699d9c4a327939`  
		Last Modified: Wed, 10 Jan 2018 22:52:49 GMT  
		Size: 9.0 MB (8952371 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:027e3fe15b8c20c80419445483ad27a01887e384e59dd0d0595a97ec6fe5087b`  
		Last Modified: Wed, 10 Jan 2018 22:52:45 GMT  
		Size: 1.2 KB (1184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
