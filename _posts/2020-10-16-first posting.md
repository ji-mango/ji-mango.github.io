---
layout: post
title:  "linux command"
image: ''
date:   2020-10-16 12:35:00
tags:
- system programming
description: ''
categories:
-  subject record
---

# [리눅스 명령어 정리]
### 파일 관련
1. 생성
- **vi** : 파일 편집기 
- **gcc** : 컴파일 
- **mknod** : 장치파일 생성

2. 복사/변경
- **cp** : 복사
- **mv** : 이동or이름변경
- **ln** : 링크파일 생성

3. 삭제
- **rm** : 파일 삭제

4. 리스트화
- **ls** : 디렉토리에 있는 내용 확인<br>
  *ls -s* : 파일의 정보, 유저권한, 그룹권한, 그외권한, 소유아이디, 소유그룹, 크기, 수정된 시간, 이름

5. 내용 보기
- **cat** : 파일 내용 보여줌
- **more** : 터미널 창의 크기에 맞춰 파일 내용 보여줌
- **less** : 엔터치면 한줄씩 스페이스바 치면 두줄씩 출력
- **head** : 파일의 앞부분 지정한 만큼 출력
- **tail** : 파일의 뒷부분 지정한 만큼 출력
- **objdump** : 오프젝트파일 내용 볼 때<br>
 *objdump -d* : disassemble(.o->.s) 보기 쉽게 <br>
 *objdump -f* : 파일의 포맷 보여줌<br>
 *objdump -h* : 헤더정보 보여줌<br>
- **hexdump** : 텍스트 또는 이진파일 내용을 16진수로 출력

6. 속성 변경
- **chmod** : 파일 권한 변경(chmod 권한 파일명)
- **chown** : 소유권 변경
- **chgrp** : 소유그룹 변경
- **touch** : 파일의 날짜, 시간정보 변경

7. 입출력 재지정 
- **'>'** - 파일의 결과 또는 출력을 다른 파일이나 스트림으로 전달

<hr>

### 디렉토리 관련
1. 생성
- **mkdir** : 디렉토리 생성
2. 변경
- **cd** : 디렉토리 이동
3. 삭제
- **rmdir** : 디렉토리 삭제
4. 정보
- **pwd** : 현재 디렉토리

<hr>

### 프로세스 관련
1. 내용 보기
- **ps** : 현재 실행 중인 프로세스 정보 보여줌(pid, 터미널정보, 시간, 진행중인 프로세스)
- **pstree** : 프로세스간의 연결구조를 트리형식으로
- **top** : 자세한 정보 출력, proc에서 일정 주기로 합산해 cpu 사용율 출력
- **/proc** : 프로세스 상태 보여줌
2. 생성
- **fork()** : 프로세스 생성
- **execve()** : 프로세스 실행
= **exit()** : 프로세스 종료
3. 삭제
- **signal(^c)** : 프로세스에 어떠한 정보를 알리는 일종의 인터룹트 - **kill command(kill killsignal pid)** : 프로그램 강제종료

<hr>

### 디버거 관련(gdb 프로그램명)
*gcc -g로 컴파일해서 파일을 만들어야 symbol table을 포함해주기 때문에 디버깅이 쉬워진다*
- run - 디버깅할 프로그램의 수행 시작
- list - 소스파일을 보여줌
- break i - i번째 라인에서 실행하다가 멈춤 
- n - next라 부름, single stepping 해줌
- l - main 함수를 기준으로 소스를 출력
- quit - 디버깅 종료
- info display - 프로그램이 멈출 때 출력할 표현을 보여줌

<hr>

### 기타
- pipe( ㅣ ) - 파일의 결과 또는 출력값을 다른 파일에 입력값으로 전달
- & - 백그라운드 실행(뒤에서 실행->프로그램이 종료되지 않아도 쉘로 돌아옴)
- sort (-k5n) - (key로 5번째 항목 사용해서)정렬
- wc - word count(-l : line몇갠지, -c : character 몇갠지, -w : word 몇갠지)
- grep - 파일에 패턴이 있는지
 *ex)grep-o 단어명 파일명 | wc -l* : 해당 단어가 몇 개있는지 개수 세줌

<!-- <p class="music-read"><a href="spotify:track:4DAZ8UYNpWVIV46aLkN2Qp">Music for reading(spotify)</a></p>

<img src="http://cdn1.tnwcdn.com/wp-content/blogs.dir/1/files/2016/02/raw.gif">

## Sharding ? why ?

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iste quas, esse laudantium quis ipsa consequuntur iure atque! Necessitatibus quam quidem illum, corrupti molestiae, maxime neque, consequuntur quia alias, modi commodi.Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate rem ducimus dolores repellat itaque perferendis corporis ex dicta doloremque optio harum excepturi, ut, praesentium asperiores! Voluptatum amet perspiciatis iusto, fugiat!Lorem ipsum dolor sit amet, consectetur adipisicing elit. Harum, libero quia placeat necessitatibus culpa mollitia, illum, quam sed ratione ad eaque suscipit consectetur itaque quasi aperiam. Quaerat, nihil voluptas tenetur?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eos unde quam autem fugit, aliquam perspiciatis, accusamus numquam, pariatur impedit excepturi debitis repellendus consectetur laboriosam voluptatem temporibus sunt illo magnam! Voluptates.Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ullam repudiandae quidem, fuga eaque, deserunt eius. Aperiam, maxime fuga alias ad vel amet et facere soluta asperiores quasi. A, aperiam, ipsam.

<figure class="foto-legenda">
	<img src="{{ "/assets/img/sharding-gerenciamento-usuarios/ajudando-carregar.jpg"}}" alt="">
	<figcaption> <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repellat architecto minus sed dolorum debitis iste quae harum, fuga commodi libero voluptatum voluptates nemo, assumenda itaque. Placeat neque voluptatem, veritatis quae.</p>
	</figcaption>
</figure>

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tenetur, illo eaque incidunt voluptatibus minus repudiandae eius consectetur tempore enim quisquam, quia veniam fuga autem, labore quas voluptate suscipit. Omnis, rem!Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vero, veritatis modi libero unde! Sapiente tempora eius cum doloribus, non, provident, veniam placeat veritatis quos possimus asperiores ipsam animi aliquam vel!

<img src="https://octodex.github.com/images/codercat.jpg" alt="">

## Lorem ipsum dolor, alias.?

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nemo minima veritatis est, unde nesciunt optio debitis. Soluta eos temporibus harum esse eveniet, alias praesentium, sapiente ipsa excepturi reprehenderit ullam ea.

### Warning!

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Atque corporis, fuga sequi cumque in quos excepturi placeat iste! Eaque voluptatum laudantium, recusandae optio! Rem impedit laborum enim minima aliquid, repellendus.<br>
` scalability` Lorem ipsum dolor sit amet, consebus tempora!:

1. <a href="http://dba.stackexchange.com/questions/4508/what-does-horizontal-scaling-mean" target="_blank">What does horizontal scaling mean?</a>
2. <a href="https://blog.openshift.com/best-practices-for-horizontal-application-scaling/" target="_blank">Best Practices For Horizontal Application Scaling</a>
3. <a href="http://www.infoq.com/articles/ebay-scalability-best-practices" target="_blank">Scalability Best Practices: Lessons from eBay</a>
4. <a href="http://stackoverflow.com/questions/5401992/what-does-scale-horizontally-and-scale-vertically-mean" target="_blank">What does scale horizontally and scale vertically mean?</a>

## Lorem ipsum dolor sit amet,res.


{% highlight javascript %}
use admin
db.createUser{
	user: "bonitao",
	pwd: "2016bonitao",
	roles: [{role: "userAdminAnyDatabase", db: "admin"}]
}
{% endhighlight %}

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cumque asperiores quam fuga tempora nisi consequatur, sequi cum voluptate deleniti quis, perspiciatis commodi beatae modi, iusto ab deserunt corrupti libero doloribus.

{% highlight javascript %}

db.updateUser("bonitao",
{
	pwd: "2016bonitao",
	roles: [{role: "read", db: "assets"}]
})

{% endhighlight %}

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Magni assumenda perferendis, iure atque. Tempore qui blanditiis autem necessitatibus natus soluta voluptas saepe totam animi voluptatum recusandae, nihil maiores et cumque.
-->
