<!-- Auto generated file, DO NOT EDIT. Please refer to README.yml -->
# docker-go

![https://img.shields.io/docker/pulls/marcelocorreia/go.svg](https://img.shields.io/docker/pulls/marcelocorreia/go.svg)
![https://img.shields.io/github/languages/top/marcelocorreia/docker-go.svg](https://img.shields.io/github/languages/top/marcelocorreia/docker-go.svg)
![https://api.travis-ci.org/marcelocorreia/docker-go.svg?branch=master](https://api.travis-ci.org/marcelocorreia/docker-go.svg?branch=master)
![https://img.shields.io/github/release/marcelocorreia/docker-go.svg?flat-square](https://img.shields.io/github/release/marcelocorreia/docker-go.svg?flat-square)
---
### TLDR;
- [Overview](#overview)
- [Description](#description)
- [Dockerfile](#dockerfile)
- [Usage](#usage)
- [Setting Timezone](#setting-timezone)
- [License](#license)
- **Semver versioning**
### Overview
Docker Go image


### Description
Docker Golang image with some goodies



### Usage
```bash
$ docker run --rm marcelocorreia/go version

```
## Setting timezone
```bash
$ docker run --rm -e TZ=Australia/Sydney marcelocorreia/go version
```
### Extending
```Dockerfile
FROM marcelocorreia/marcelocorreia/go
...
```




## Dockerfile.alpine 
```Dockerfile
FROM golang:alpine

MAINTAINER marcelo correia <marcelo@correia.io>

RUN apk update
RUN set -ex && \
    apk add --no-cache --update \
        bash \
        tzdata \
        git \
        curl \
        zsh \
        sudo \
        make

RUN wget https://github.com/goreleaser/goreleaser/releases/download/v0.106.0/goreleaser_Linux_x86_64.tar.gz
RUN tar -xvzf goreleaser_Linux_x86_64.tar.gz
RUN mv goreleaser /usr/local/bin

RUN curl -L https://github.com/golang/dep/releases/download/v0.5.1/dep-linux-amd64 -o /usr/local/bin/dep
RUN chmod 0750 /usr/local/bin/dep

RUN go get golang.org/x/tools/cmd/stringer

RUN curl https://glide.sh/get | sh

CMD ["uname","-a"]
```


### License
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Copyright [2015]

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.


---
[:hammer:**Created with a Hammer**:hammer:](https://github.com/marcelocorreia/hammer)
<!-- -->
















