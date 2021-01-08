# 충돌과 해결법

## branch와 충돌

branch를 사용하다보면 하나의 파일을 여러 개발자가 수정하여 merge시 정상적으로  
합쳐지지 않는, **충돌(Conflict)** 의 문제가 발생할 수 있다.  

`A 브랜치` 에서 예를 들어 하나의 파일에 소스코드 일부를 수정/추가하고,  
`B 브랜치` 에서도 같은 파일에 다른 내용의 소스코드 일부를 수정/추가 하였을 때  
`master branch` 에서 정상적으로 merge가 수행되지 못하고, `conflict`가 발생한다.

이 때, master branch에서 merge수행시 conflict가 발생하면  
해당 소스코드에 두 개의 수정 여부가 동시에 하나의 파일 안에 다 합쳐진다.
(git에서는 한줄단위로 수정이 일어나고,  
수정이 일어나면 해당 줄이 수정되는 것이 아니라  
수정 이전의 line은 삭제, 새로운 line이 추가되는 방식으로 commit이 일어난다.)

master branch로 head를 옮기고, conflict가 일어난 파일을 열어  
어느 부분으로 merge할지 결정하여 소스코드를 수정, 필요없는 소스코드를 삭제 한 뒤  
다시 add-commit-push를 통해 remote repository에 동기화하면 해결할 수 있다.
