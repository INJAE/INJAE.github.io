---
layout: post
title:  travis 사용할때 주의점
categories: [CI]
tags: [c++, cmake, travis]
---
만약에 Travis를 사용하는데 sudo 명령어가 안될때가 있습니다.
기본적으로 travis가 docker같이 sudo를 지원하지 않아서 sudo 명령어를 사용하려면 
env "PATH=$PATH"를 sudo 뒤에 사용해야됩니다.

<!-- more -->

예시
===
기존 환경
```
sudo cmake --build . --target install
```
Travis 설정 
```
sudo env "PATH=$PATH" cmake --build . --target install
```
