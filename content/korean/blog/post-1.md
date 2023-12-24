---
title: 토탈커맨더로 심볼릭링크 생성하기
meta_title: 토탈커맨더 심볼릭링크
description: 토탈커맨더로 심볼릭링크 생성하기
date: 2023-12-17T05:00:00Z
categories:
    - 프로그램
author: mychatterbox
tags:
    - 토탈커맨더
    - 심볼릭링크
draft: false
keywords:
    - symbolic link
    - 심볼릭링크
    - 토탈커맨더
    - symlink
---

토탈커맨더에서 개인 명령어를 추가하고 메뉴에 등록해서 사용하려면 우선 토탈커맨더 폴더에 usercmd.ini 파일을 만들고 명령어들을 넣은 다음, 이 명령어를 이용해 아이콘과 연결해 사용하든, 시작 메뉴에 등록해야 한다.

　
<!--more--> 
 <!-- more 위 문장만 블로그 목록에서 노출된다. -->

아래는 예시 코드이다.

***ext_symlink*** 라는 명령을 실행하면 ***ext_symlink2text1***, ***symlink2text2*** 라는 2개의 명령을 실행하게 되어 있음을 짐작할 수 있다. 이 이름은 변경해도 된다.

[em_ext_symlink2text1] 부분은 심볼릭링크를 생성하는 명령이고

[em_ext_symlink2text2] 부분은 텍스트파일을 하나 만드는데, 원본 폴더나 파일의 주소를 기록해준다.


```html
[em_ext_symlink]

cmd=em_ext_symlink2text1, em_ext_symlink2text2

menu=Make directory or file symlink in the opposite panel for selected files

button=%COMMANDER_PATH%\WCMICON2.DLL,65

iconic=1

[em_ext_symlink2text1]

cmd=*%COMSPEC% /C

param=@for /f "usebackq tokens=*" %%i in ("%F") do @( if exist "%P%%~i\" ( mklink /D "%T%%~i" "%P%%~i" ) else ( mklink "%T%%~i" "%P%%~i" ) )

menu=Make directory or file symlink in the opposite panel for selected files

button=%COMMANDER_PATH%\WCMICON2.DLL,65

iconic=1

[em_ext_symlink2text2]

cmd=%COMSPEC% /C

param=if exist "%P" copy "%WL" "d:\symbolic link.txt"

menu=Copy selected filenames with full path to file in current folder (Unicode)

iconic=1
```


현재 활성창(원본)의 파일이나 폴더를 선택한 상태에서 명령을 실행하면 반대쪽 비활성창에 심볼릭링크가 만들어지고 원본 폴더나 파일의 주소가 포함된 텍스트 파일을 지정한 위치(d:\)에 지정한 이름(symbolic link)으로 만들어준다.

[em_ext_symlink2text2] 부분은 텍스트파일의 위치나 파일명을 수정해도 되고, 굳이 필요없다면 전체를 지워도 상관없다.



토탈커맨더의 시작 메뉴에 명령을 등록해서 사용하는 방법이다.

시작 메뉴에서 '항목 추가' 후 적절한 제목을 입력한 뒤 아래처럼 구성한다.



{{< image src="blog-images/post-1_1.jpg" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}

<hr>