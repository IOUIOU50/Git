# Git Start

## Git 설치 & 명령어 확인하기

Git설치는 Git 홈페이지에서 간단하게 설치할 수 있다.  
설치중에 나타나는 다양한 옵션들은 별도로 지정할 필요 없이 `next` 를 눌러 계속 진행한다.  

기본적인 설치 후 CMD창을 열어 **git명령어** 를 입력해보면, 다양한 git 명령어를 확인할 수 있다.  

**입력**

<pre>
> git
</pre>

**실행결과**

<img src='https://user-images.githubusercontent.com/57579709/103733194-811ee200-502c-11eb-819c-dca0ce609045.png'></img>

간단하게 `git --version`명령어를 실행시켜 보자.

**입력**

<pre>
> git --version
</pre>

**실행결과**

<img src='https://user-images.githubusercontent.com/57579709/103733865-03f46c80-502e-11eb-84ee-645c50755fca.png'></img>

## Git 전역설정
Git을 로컬 컴퓨터 내 전역으로 사용하기 위한 설정에는 `user.name`과 `user.email`을 설정해 주어야 하는데,  
cmd창에서 다시 git명령어 중 하나인 `config` 명령어를 통해 설정해 주도록 한다.  
cmd 디렉토리는 굳이 원하는 프로젝트가 아니라 아무 디렉토리에서나 수행해도 상관 없다.

<pre>
> git config --global user.name 본인github이름
> git config --global user.email 본인github이메일
</pre>

여기서 `--global`조건은 하나의 프로젝트만 사용하는 것이 아니라  
PC 내 전역으로 사용되는 조건을 의미한다.

## git clone을 통해 github프로젝트 가져오기

`git clone`명령어를 이용하면 github내의 프로젝트를 내 로컬 컴퓨터로 가져올 수 있다.

**입력**
<pre>
> git clone github주소
</pre>

이렇게 clone을 통해 프로젝트를 가져오면 해당 디렉토리에 `.git`이라는 폴더가 생성이 되고,  
각종 IDE나 cmd의 `cd`명렁어를 통해 해당 디렉토리로 이동하여 git에서 제공하는 다양한  
형상관리 기능을 이용할 수 있게 된다.

여기서 github에 존재하는 프로젝트를 `Remote Repository`,  
내 컴퓨터 내 존재하는 사본 프로젝트를 `Local Repository`라고 한다.

## add, commit, push

이제 github와 연동되는 git project가 생성되었으니 파일을 새로 만들어 github와 동기화 하는 과정이 필요하다.  
먼저, 수정이나 변경된 사항은 `add`명령어를 통해 수행할 수 있다.

<pre>
> git add 변경/수정된파일
또는
> git add .
</pre>

`add`명령어 뒤에 `.`를 붙이게 되면 변경된 모든 파일이 적용된다.

변경된 파일을 add하고나면 변경 내용을 **snapshot** 으로 보관, 처리하기 위해 `commit`명령어를 사용하게 되는데,  
나중에 commit된 지점으로 되돌리거나 하는 등의 작업을 수행하는데 이용된다.  

<pre>
> git commit -m "커밋메시지"
</pre>

`-m "커밋메시지"` 부분은 commit한 내용에 대해 남길 간단한 변경 내용을 설명하는데 사용할 수 있다.

커밋까지 끝나고 나면 `push`명령어를 통해 **remote repository**인 github에 동기화 할 수 있다.

<pre>
> git push
</pre>

## 왜 Github를 사용하는가?

**첫 번째로,** Github의 기본적인 목적에는 **오픈소스의 공유** 가 있다.  
내 소스코드를 공유하여 기술을 공유개발자로서 사회에 기여할 수 있고  
다른 개발자가 공유한 소스코드를 참고하여 개발할 수 있는 것도 가능하게 한다.

**두 번째로,** 여러 사람과 협업하는 프로젝트를 진행함에 있어 프로젝트의 통합을 위해 사용할 수 있다.

**세 번째로,** github는 개발자의 **포트폴리오**, 즉 **이력서**가 된다.

## checkout

add이전에, 소스코드를 원래의 상태로 되돌리고 싶다면 `git checkout -- 수정/추가돤파일ㅇ`명령어를 사용하면  
add하지 않은 상태로 되돌아가게 된다.

<pre>
> git checkout -- 파일명.확장자
또는
> git checkout -- .
</pre>
