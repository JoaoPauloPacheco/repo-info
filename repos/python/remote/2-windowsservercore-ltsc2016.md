## `python:2-windowsservercore-ltsc2016`

```console
$ docker pull python@sha256:6d7c803b5c2b60e6e25e41e3cc2ef85b31e3ddde9113bbfdb4b3ff5d4015981d
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2007; amd64

### `python:2-windowsservercore-ltsc2016` - windows version 10.0.14393.2007; amd64

```console
$ docker pull python@sha256:2ba08e774f1846479425d5006d9150c9e13d4d59cf750b60ab618746cbb912d8
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.4 GB (5428265849 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0cd807fca2427372d9a855fde877b80393ac26c3efbc6769f1725ab547a5a4e2`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Thu, 04 Jan 2018 20:07:32 GMT
RUN Install update 10.0.14393.2007
# Fri, 05 Jan 2018 10:02:17 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Fri, 05 Jan 2018 17:39:50 GMT
ENV PYTHON_VERSION=2.7.14
# Fri, 05 Jan 2018 17:39:51 GMT
ENV PYTHON_RELEASE=2.7.14
# Fri, 05 Jan 2018 17:42:04 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}.amd64.msi' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'python.msi'; 		Write-Host 'Installing ...'; 	Start-Process msiexec -Wait 		-ArgumentList @( 			'/i', 			'python.msi', 			'/quiet', 			'/qn', 			'TARGETDIR=C:\Python', 			'ALLUSERS=1', 			'ADDLOCAL=DefaultFeature,Extensions,TclTk,Tools,PrependPath' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.msi -Force; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 17:42:05 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Fri, 05 Jan 2018 17:43:35 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Fri, 05 Jan 2018 17:44:43 GMT
RUN pip install --no-cache-dir virtualenv
# Fri, 05 Jan 2018 17:44:44 GMT
CMD ["python"]
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
	-	`sha256:e41b6b16cb26c71bf465c4eb0edd8a39b1334438b55231f414a13ac00683eb51`  
		Last Modified: Fri, 05 Jan 2018 17:47:00 GMT  
		Size: 1.2 KB (1197 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84a9c15adc9f74c1ddcdb59ff1aaf400bc89364293c20323221e7a3bee0d1692`  
		Last Modified: Fri, 05 Jan 2018 17:47:00 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13de81a1e220546359b424835fdfa8ef7a5b9ff2b9e4fdd5c64a61ebeb7ca4c8`  
		Last Modified: Fri, 05 Jan 2018 17:47:08 GMT  
		Size: 38.4 MB (38414025 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e153921e590d4c85a36a8e29f669cf4e03836d942660971b46f66e6233118dc8`  
		Last Modified: Fri, 05 Jan 2018 17:46:56 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:964c61bf86aa7f476d772ef6a86d865a149fe4425ca2f2686a96c9eed1fc8ccd`  
		Last Modified: Fri, 05 Jan 2018 17:47:02 GMT  
		Size: 9.1 MB (9060226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9702d0ff66644104c0d306b20cf430d447f69cb2e996a67d54bfe3c04cb98ef8`  
		Last Modified: Fri, 05 Jan 2018 17:46:59 GMT  
		Size: 6.8 MB (6780436 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c8cf9e4d2d620e721acc43a87022a449d97f111ccf6d3239215de3118f7f017`  
		Last Modified: Fri, 05 Jan 2018 17:46:56 GMT  
		Size: 1.2 KB (1190 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
