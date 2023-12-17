---
title: OSFMOUNT 램디스크 작업스케쥴러
meta_title: osfmount 램디스크
description: 윈도우 시작 시 자동으로 램디스크를 생성
date: 2023-12-17T05:00:00Z
categories:
    - 프로그램
author: mychatterbox
tags:
    - OSFMount
    - 램디스크
draft: false
keywords:
    - osfmount
    - 램디스크
    - ramdisk
---

윈도우 시작 시 자동으로 램디스크를 생성하고 몇 개의 폴더를 자동으로 만드는 방법을 설명한다.


1. OSFMount 설치

2. OSFMount 폴더 혹은 임의의 위치에 osfmount.bat 와 같은 파일을 만든다. (다른 위치에 만들 경우 작업 스케쥴러의 동작탭에서 위치를 수정한다.)


3. osfmount.bat 파일을 메모장 등 에디터로 열고 아래 내용으로 저장한다.

   아래 예시는 드라이브명은 R, RAMDISK 이름을 붙이고 16기가 고정된 용량으로 설정한다. 
    ```html
    @echo off
    osfmount -a -t vm -o rw,hd,format:ntfs:"RAMDISK" -m R: -s 16G
    ```    

    만약 윈도우 시작 시 미리 폴더를 만들기 원하면 아래 내용을 추가할 경우 램디스크 생성하고 3초 후 정한 위치에 폴더를 자동으로 만든다.     

    ```html
    timeout /t 3

    mkdir r:\Chrome\Cache

    mkdir r:\Chromium\Cache

    mkdir r:\Temp
    ```

4. 이제 이 osfmount.bat 파일을 작업 스케쥴러에 아래와 같이 혹은 각자의 방법으로 등록한다. 제대로 등록한 것 같은데 왠지 작동이 안되는 것 같으면 작업 스케쥴러의 계정 부분이나 동작 탭의 설정 부분을 확인한다. 

    윈도우 시작 시 바탕화면에 진입한 후 너무 빨리 이런저런 작업을 하려고 하면 램디스크가 만들어지지 않는 경우가 생길 수 있다.



{{< image src="blog-images/post-5_1.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}
{{< image src="blog-images/post-5_2.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}
{{< image src="blog-images/post-5_3.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}

<hr>