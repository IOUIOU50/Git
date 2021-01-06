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

<img src='https://user-images.githubusercontent.com/57579709/103733194-811ee200-502c-11eb-819c-dca0ce609045.png' width='700'></img>

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

