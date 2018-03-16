# Git의 명령어

기본적인 유의사항과 형상관리 시스템에 대한 개념적인 설명은 다음을 참고하라.

* URL등록 예정

git의 저장소는 3가지 단계로 나누어 진다.  
* 커밋한 소스가 보관되는 **저장소(storage)**
* 현재 프로젝트 파일들이 있는 **작업트리(work tree)**  
* 저장소와 작업트리 사이의 버퍼영역으로 커밋될 대상이 저장되는 **스테이징 영역(staging area, index)** 이다.

다음은 git의 가장 기본적인 특징들이다.  
* git은 빈 디렉토리는 추적하지 않는다.
* 형상관리를 하지 않을 파일은 .gitignore에 등록한다.  
* HEAD는 현재 브랜치의 가장 최신 커밋을 의미한다.
* 기본 원격 저장소를 origin이라고 부른다.  

## 기본 명령어(로컬 저장소)

> 주의: 여기서 소개하는 alias목록은 따로 alias가 되어있는 여러 비 로그인 쉘 세션을 위한 파일(/etc/bash.bashrc, ~/.bashrc, ~/zshrc)등을 찾아서 다운로드를 받던지, oh my zsh과 같은 패키지를 설치해야 사용할 수 있다.

### git init

저장소를 생성하는 명령: 실행한 위치를 git저장소로 초기화한다.    
아직 유용한 옵션은 못 찾았다.  

### git add

저장소에 파일 추가: 해당 파일을 git이 추적할 수 있게 저장소에 추가한다.  
구문은 다음과 같다.  

> git add _filename_

모든 파일을 add하고 싶다면 `filename`을 적지 않고, 아래에서 설명할 -A 옵션을 써도 좋다.  
또는 다음과 같은 구문을 사용해도 좋다.  
다음 구문은 ``git add -A``와 같은 의미다.

> git add \*

유용한 옵션은 다음과 같다.  

* -v (verbose): git이 어떤 행동을 했는지 터미널을 통해서 알려준다.  
* -A (All): 저장소 내부의(그리고 gitignore에 등록되어 있지 않은)모든 변경된 파일과 새로운 파일을 저장소에 추가
* -p (patch): patch모드로 add한다.
* -i (interaction): 대화형 모드로 전환한다. 하나씩 살펴보면서 파일을 저장소에 추가하거나 뺄 수 있다.

#### alias목록

* gaa: git add --all

### git status

말 그대로 현재 저장소의 상태를 출력한다.  
만약 작업 디렉토리 안에 git이 추적하고 있지 않은 새로운 파일이 생성되거나, 추적하고 있는 파일에 변경사항이 생기거나, 새로이 스테이징 영역에 올라간(변경된 파일도 보여줌) 파일들의 리스트를 구분해서 보여준다.

* -s (simple): 상태 목록을 간단하게 보여준다.

#### alias목록

* gst: git status

### git commit

스테이징 영역에 올라가 있는 파일들을 커밋한다.  
-m은 커밋메시지를 주는 옵션으로 여러 줄의 커밋 메시지를 쓸 경우 -m을 여러개 사용할 수 있다.  
-a옵션을 사용하면 스테이징에 올리는 작업과 커밋을 동시에 할 수 있다.(추적되지 않는 파일은 추가하지 않는다.)  
특정파일만 커밋하고 싶다면 마지막에 파일명을 추가해주면 된다.  

* -m (message): 커밋시 짧은 메시지를 같이 커밋한다. 그냥 commit명령어를 입력하면 지정된 편집기로 커밋 메시지를 작성해야 한다.
* -a (all): 모든 add된 파일들을 전부 커밋한다.
* -v (verbose): -m을 사용하지 않을 때 -v옵션을 사용하면 커밋하려는 변경사항의 다른점을 보여준다.  

#### alias목록

* gcv: git commit -v

## 원격 저장소

원격 저장소를 관리할 수 있어야 다른 사람과 함께 일할 수 있다.  
리모트 저장소는 인터넷이나 네트워크 어딘가에 있는 저장소를 말하며, 리모트 저장소를 관리하면서 데이터를 push, pull하는 것이 git의 remote 저장소를 활용하는 것이 중요하다.

### git remote

``git remote``명령어로 현재 프로젝트에 등록된 리모트 저장소를 확인할 수 있다.  
하지만 이 명령어만 주면 단축이름만 보여준다. 단축이름과 URL을 함께 보고싶다면 -v옵션을 사용하자.  

#### 리모트 저장소 추가

리모트 저장소를 추가하는 방법을 잘 모르겠는가?  
하지만 이 문서에 들어왔다면 최소한 1번은 해보았을 것이다. 다음 코드를 보자.

```
git remote add origin https://yourremotestorage.git
git push -u origin master
```

어디서 많이 본 기억이 나지 않는가?   
github를 사용해보았다면, 처음 repo를 파고나서 나오는 간단한 튜토리얼에서 나오는 구문이다.


#### 옵션 정리

* ``git remote -v`` : 현재 프로젝트에 등록되어 있는 모든 리모트 저장소의 단축 이름과 URL을 함께 보여준다.
* ``git remote add {name} {URL}`` : 리모트 저장소를 추가하는 구문으로, {name}에 {URL}을 바인딩하여 프로젝트의 새로운 리모트 저장소로 등록한다.

### git push

원격 저장소에 커밋 내용을 보낸다.  
하지만 설명과는 다르게 ``git init``을 하고 처음에 ``git push``를 날리면 원격 저장소에 ``push``를 하지않는다.  
왜 그럴까? -> 그 이유는 ``upstream(-u)``설정을 하지 않았기 떄문이다. 특정한 리모트 저장소를 정하고, upstream을 설정하면 push할 때마다 일일이 원격 저장소의 이름을 명시할 필요가 없다.  


특정한 원격 저장소에 upstream 설정을 하기 위해서는 다음과 같이 명령을 주면 된다.  
```
git push -u {remoteStorageName} {branchName}
```

따라서 가장 많이 쓰이는 ``git push -u ...`` 명령어가 이런 방식으로 나온다.  

```
git push -u origin master
```

origin(기본 remote 저장소 이름)이나 master(기본 local branch 이름)는 많이 사용되는 이름일 뿐이지 특별하게 취급되진 않는다.

#### 정리

* ``git push``: 기존에 등록되어 있던 upstream을 참고해서 push 한다.
* ``-u`` : upstream을 설정하는 옵션이다. 자세한 것은 위 문단을 참조할 것.
* ``-v`` : 보다 자세한 내역을 현재 git을 사용하는 사람에게 보여준다.

## 환경설정

### git config

* git config --global --list: 현재 설정정보를 조회할 수 있다. --global옵션은 전역설정에 대한 옵션이며 현재 프로젝트에만 적용할 때는 주지 않는다.  
* git config --global user.name "username": 사용자명을 등록한다.  
* git config --global user.email "email address": 이메일 주소를 등록한다.
* git config --global color.ui "auto": 터미널에 표시되는 메시지에 색깔을 입혀준다.  

> 주의: username='_string_' 과 같은 방식으로는 해당 속성에 적절한 값을 바인딩 할 수 없다. 따라서 무조건 위의 리스트에 나와 있는데로 해야한다.

## 로그

### git log

## 원격 저장소

### git clone
원격 저장소를 **복제** 하여 저장소를 생성한다.  

### git pull
원격 저장소의 변경사항을 가져와서 원격 브랜치를 갱신한다.  

### git fetch
원격 저장소의 변경사항을 가져와서 원격 브랜치를 갱신한다.  

## 출처

* https://blog.outsider.ne.kr/572
* https://git-scm.com/book/ko/v1/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EB%A6%AC%EB%AA%A8%ED%8A%B8-%EC%A0%80%EC%9E%A5%EC%86%8C
* https://git-scm.com/book/ko/v2/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EB%B8%8C%EB%9E%9C%EC%B9%98%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80
