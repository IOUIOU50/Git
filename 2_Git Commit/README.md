# Commit에 조금 더 자세히

## commit 내역 수정하기

이전에 commit은 일종의 **snapshot** 형태로 소스코드를 유지한다고 언급하였는데,  
만약 이전 상태의 소스코드로 돌아가고 싶을 때, 또는 잘못된 commit을 수행하였을 때  
commit을 수정하고, 프로젝트를 되돌리는 것이 가능하다.

## pull

github에 존재하는 프로젝트의 내용을 local repository로 가져와 갱신하는 명령어이다.  
현재 local repository에 remote repository, 즉 github의 소스코드가 적용되니  
주의해야 한다.

<pre>
> git pull
</pre>

## 특정 commit 지점으로 소스코드 되돌리기

소스코드를 수정하고, add-commit-push까지 마쳐 local-remote간의 동기화가 완료 된 상태에서  
이전 상태로 되돌리는 법에 대해 알아보자.

우선 commit한 내용을 확인하기 위해서는 `git log`명령어를 사용하면 된다.

**입력**
<pre>
> git log
</pre>

**결과**

<img src='https://user-images.githubusercontent.com/57579709/103740983-96e7d380-503b-11eb-9e04-d515431cab6d.png'></img>

여기서 특정 commit위치로 돌아가고싶다면, `git reset`명령어를 사용하게 되는데,  
옵션으로 `hard`, `soft`, `mixed`옵션이 있다. 이에 대한 설명은 좋은 글이 있어  
해당 글을 첨부해왔다.

<pre>
돌아가고 싶은 commit으로 reset할 때,
--hard: reset하기 전까지 했던 staging area, working directory의 작업까지 모두 reset!
(모든 게 잘못됐어! 나 돌아갈래~ 꽃피던 때부터 정갈하게 다시 해보자!)
--mixed(default): staging area은 reset, reset하기 전까지 했던 working directory의 작업은 남겨둠.
(현재 작업물은 지우긴 싫고, 이전 버전으로 돌아가서 add할지 말지 결정해야 할 때)
--soft: reset하기 전까지 했던 staging area, working directory의 작업은 남겨둠.
(reset한 버전과 현재까지의 작업을 합쳐 새로운 버전 만들 때)

출처 : https://opentutorials.org/module/4032/24533
</pre>

위에서 `git log`명령어를 사용하면 얻을 수 있는 **해시코드**값을 이용하여  
이전 commit 상태로 되돌아가는 명령어는 아래와 같다.

**입력**
<pre>
> git reset --hard(또는 soft, mixed. default는 mixed) commit해시코드
</pre>

여기서 local과 remote사이의 commit기록의 오차로 인해 push명령어가 오류메시지를 뿜어낼 수 있는데,  
이때는 push명령어 뒤에 `-f`를 추가하면 강제로 push가 이루어져  
local과 remote가 완전히 동일한 상태가 된다.
물론 commit 내용은 모두 사라진다.

<pre>
> git push -f
</pre>
