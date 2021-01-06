# Branch 사용하기

## Branch란?

브랜치는 여러 개발자들이 각자 다른 수정/추가사항을 작성할 수 있도록 하는 기능이다.  
브랜치를 잘 이용하면 **서로 어떠한 영향도 받지 않고** 개발을 진행할 수가 있게 된다.

Git repository를 처음 만들면 `Master Branch`가 생성이 되는데,  
이 Master Branch는 배포 가능한 버전을 포함하는 프로젝트를 의미한다.

Master Branch외에 프로젝트의 일부에 해당하는 특정 기능을 개발하기 위해 만들어지는 브랜치를  
`Topic Branch`라고 한다.

## Branch 만들기

`git branch`명령어를 이용하면 현재 존재하는 branch를 확인할 수 있다.

**입력**

<pre>
> git branch
</pre>

**결과**

<img src='https://user-images.githubusercontent.com/57579709/103742685-93098080-503e-11eb-9be6-e9d9ad897fee.png'>

새로운 branch를 만들 땐 같은 명령어에 branch 이름을 뒤에 추가해준다.

**입력**

<pre>
> git branch 새로운브랜치

예)
> git branch develop
</pre>

**결과**

<img src='https://user-images.githubusercontent.com/57579709/103742973-ef6ca000-503e-11eb-8416-ce9f067a3a9f.png'>

## Branch 이동하기

branch를 생성해도 해당 branch를 이용하기 위해서는  
현재 어떤 branch를 가리키고 있는지 표시하는 **head**를 움직여줘야  
해당 branch를 사용할 수 있게 된다.

이 head를 움직일 때에는 `checkout`명령어를 사용하면 된다.  

<img src='https://user-images.githubusercontent.com/57579709/103742973-ef6ca000-503e-11eb-8416-ce9f067a3a9f.png'>

위의 그림에서 현재 `head`는 `master`를 가리키고 있다. 이 `head`를  
`develop`으로 옮기기 위해서는, 아래와 같은 명령어를 입력하면 된다.

<pre>
> git checkout develop
</pre>

**결과**

<img src='https://user-images.githubusercontent.com/57579709/103753634-a290c580-504e-11eb-9a99-4026a75b0bbc.png'>

## merge 수행하기

위에서 설명한 branch로 이동하고 난 후,  
add - commit - push를 수행하고 나면,  master branch에는 어떠한 변화도 일어나지 않고,  
별도로 분리된 Topic branch에만 commit 결과가 적용된다.  

<pre>
> git add .
> git commit -m "test"
> git push
(현재, head가 develop을 가리키고 있는 상태)
</pre>

이 분리된 별도의 Topic branch들을 합치기 위해서는 `merge`를 수행해주면 된다.

먼저, 위의 예시에서 develop으로 옮겨두었던 `head`를 다시 `master`로 옮겨주자.

<pre>
> git checkout master
</pre>

그리고, 