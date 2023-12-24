---
title: N100 등 미니PC 전원을 PD충전기로
meta_title: n100 미니pc pd충전기
description: pd충전기로 N100 등 미니pc 사용하기
date: 2023-12-24T14:25:25.529Z
categories:
  - 프로그램
author: mychatterbox
tags:
  - 미니pc
  - n100
draft: false
keywords:
  - n100
  - 미니pc
  - pd충전기
---


N100 등 미니PC 어댑터대신 PD충전기를 사용해보자.


<!--more--> 
 <!-- more 위 문장만 블로그 목록에서 노출된다. -->


{{< image src="blog-images/post-2_1.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}


알리에서 흔히 볼 수 있는 여러 충전기들 중 하나이다. 

65W + 30W + 25W 라서 120W 충전기로 표기한다.

{{< image src="blog-images/post-2_2.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}


포트개수가 많은 충전기들은 대부분 위처럼 어떤 특정한 규칙이 있다.

위의 충전기는 전면 디자인에 2칸씩 묶은 테두리를 쳐서 조금 더 명확하게 보여주고 있는데

설명하자면 C1, C2 포트는 각각 혼자 쓰면 65W 출력 가능하지만 동시에 사용하면 45W + 20W 출력 가능하다. 2포트의 총합이 65W 인 것이다.



N100 CPU를 사용하는 미니PC는 보통 소비전력이 30W대 이하이므로 C1 포트에 사용할건데 문제가 하나 생긴다.

C1 포트에 연결해서 65W + 0W 출력으로 아주 여유롭게 사용하다가, C2 포트에 케이블 연결해서 휴대폰 충전하는 순간 C1, C2 포트가 일시 리셋(OFF)되고 잠시 후 45W + 20W 출력으로 변하게 된다. 휴대폰, 패드, 노트북은 내장배터리가 있어서 상관없지만 PC는 잠시라도 연결이 끊어지면 문제가 된다.

이것을 해결하는 방법은 아주 간단하다. C2포트를 사용하지 않으면 된다. 

애초에 이 충전기를 65W 고정출력을 가진 5포트 충전기라고 생각하면 되는 것이다. 

만약 C4 포트도 사용하지 않으면

결국 이 충전기는 65W, 30W 고정출력 포트 2개에, 가변출력 포트 2개를 가진 4포트 충전기가 되는 것이다. 아트뮤 등 국내브랜드에서 출시하면 7-8만원 정도 예상되는 수준의 상당히 괜찮은 충전기라고 볼 수 있다.



그러면 이 충전기로 미니PC를 어떻게 사용할 것인가.

N100 정도의 cpu를 사용하는 미니pc는 대부분 19V 혹은 12V 입력을 받을 것이고 아답터를 확인해보면 보통 12V x 3A = 36W 짜리일 것이다.

C타입 케이블로 직접 충전기의 PD포트와 연결 가능한 미니pc라면 충전기의 포트가 미니pc 의 입력을 지원하는지 확인하면 된다.

이외에는 대부분 12V 혹은 19V 아답터를 따로 주고 5.5mm x 2.5mm DC 단자로 연결하는 방식인데, 그런 경우에는 아래와 같은 변환 케이블로 충전기와 미니pc를 연결해서 사용하면 된다. 

{{< image src="blog-images/post-2_3.png" caption="" alt="alter-text" height="" width="" position="center" command="fill" option="q100" class="img-fluid" title="image title"  webp="false" >}}


<hr>