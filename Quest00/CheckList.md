## Checklist
### 형상관리 시스템은 왜 나오게 되었을까요?
  개발하는 동안 소스코드의 변경사항을 보존하여 버그 및 문제점이 발생했을 때 추적하기 위해 나오게 되었다.
<br><br>

### git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?
* 가볍고 빠르다: 모든 작업이 대부분 로컬에서 진행되어 매번 네트워크에 접속할 필요가 없기 때문에 네트워크 속도와 관계없이 빠르게 진행된다.
* 분산 작업: 사용자들은 복사된 프로젝트에서 동시에 작업을 진행할 수 있으며 서버가 다운되는 등의 문제가 발생하더라도 사용자 각각이 코드 전체를 가지고 있기 때문에 문제가 발생할 소지가 없다.
* 무결성 보장: 모든 파일을 체크섬이라는 검사를 거친다. 체크섬은 Commit ID라고 불리며 Commit ID가 같은 것은 파일 또는 구성이 완벽하게 같다는 것을 의미한다.
* 분산형 형상관리 시스템: 버전 관리 자료가 하나의 원격 저장소와 분산된 로컬 저장소에 함께 저장되어 관리되는 방식이다. 원격 저장소의 자료를 로컬 저장소로 복사하여 작업한 후 변경 내용을 로컬 저장소에서 우선 반영한 다음 이를 원격 저장소에 반영한다.
<br><br>

### git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?
Git이 만들어지기 전 Linux 커널은 BitKeeper라고 하는 분산 버전관리 시스템을 사용하고 있었다. BitKeeper는 유료였지만 Linux에 무료로 제공하고 있었는데 BitKeeper와 Linux간의 관계가 틀어지자 라이센스를 제한하고 이를 대체할 버전관리 시스템이 필요해져 Git을 개발하게 되었다. Git은 분산형 시스템을 채택하여 수 천개의 동시 다발적인 비선형적인 개발에 끄떡없다.
<br><br>

### git과 GitHub은 어떻게 다를까요?
Git은 오픈소스 버전관리 시스템이고 GitHub는 Git저장소를 위한 호스팅 서비스이다.
<br><br>

### git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
* clone: 원격 저장소를 로컬 저장소에 복사하고 싶을 때 사용한다.
    `git clone [REPO_URL] [DIR]` 
    [REPO_URL]에는 복사해올 원격 저장소의 주소를 지정해준다.
    [DIR] 인자는 생략이 가능하며 로컬에 복사할 위치를 지정한다.
* add: Git은 Untracked 파일을 아직 스냅샷(커밋)에 넣어지지 않은 파일이라고 보기 때문에 Tracked 상태가 되기 전까지는 Git은 절대 그 파일을 커밋하지않기 때문에 git add 명령어로 파일을 추적할 수 있다.
  `git add [FILE_NAME]`
* commit:작업공간의 변경된 상태를 저장소에 저장하는 것
    `git commit`
    Git 설정에 지정된 편집기가 실행되고 커밋한 내용을 쉽게 기억할 수 있도록 메시지를 작성할 수 있다. `-m` 옵션을 추가하여 메시지를 인라인으로 첨부할 수 있다.
* push: 커밋을 통해 로컬 저장소에 저장된 변경사항을 원격저장소로 전송할 때 사용한다.
    `git push [저장소명] [브랜치명]
* branch: 다른 브랜치와 영향을 받지 않고 독립적으로 작업을 진행하기 위해 사용한다.
    `git branch [BRANCH_NAME]
* stash: 아직 마무리하지 않은 작업을 스택에 잠시 저장하기 위해 사용한다.
    `git stash`
    git stash 명령을 사용하면 워킹 디렉토리에서 수정한 파일들만 저장한다.
<br><br>

### git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?
* Object: git은 4개의 object로 관리한다. 객체명은 SHA1로 40자리로 해쉬된다. 따라서 내용이 같으면 객체명이 같다. 객체들은 `.git/objects`에 위치한다. 내용을 까볼려면 `git cat-file –p 객체명`으로 보면된다.
    * Blob: Working Directory의 파일에 대응하여 내용이 저장되는 Object. Blob에는 파일의 이름이나 형식등은 저장되지 않고 파일의 내용만 저장된다. 이는 만약 이름이 다른 2개의 파일이 프로젝트 내에 있더라도, 그 내용이 같으면 Git은 Blob을 한 개만 저장한다는 것을 의미한다. 또한 `clone`이나 `fetch`등을 할 때에도 파일이 한 개만 전송이 될 것이다.
    * Tree: Working Directory의 디텍토리에 대응하여 Git에 저장되는 Object. Tree의 내용은 해당 디렉토리 내부의 파일과 디렉토리의 정보(파일명, 형식, SHA-1, 등..)를 담은 Blob과 Tree Object의 리스트이다.
    * Commit: commit history를 저장하는 Object. author, committer, commit message를 포함하고 있다. 또한 내용 제일 첫 번째줄에는 tree object에 대한 정보가 있는데, 이는 이 commit의 스냅샷의 최상단 tree를 가르키는 포인터이다.
    * Tag: Git의 특정 commit에 tag를 달면 tag object가 생성된다. 태그는 Lightweight와 Annotated태그로 나뉘는데 Lightweight태그는 단순히 특정 commit에 대한 포인터로 작동하는 반면, Annotated태그는 태그의 작성자, 이메일, 날짜, 메세지를 저장할 수 있다. 또한 보안을 위해 GPG로 서명할 수 도 있다.
* Commit: 작업공간 안에 있는 모든 파일과 파일의 데이터를 복사해서 저장소에 보존하는 것.
* Head: 현재 브랜치를 가리키는 포인터이며, 브랜치는 브랜치에 담긴 커밋 중 가장 마지막 커밋을 가리킨다.
* Branch: 코드를 통째로 복사하고  기존 코드와는 상관없이 독립적으로 개발을 할 수 있다. 즉, 브랜치를 통해 하나의 프로젝트를 여러 갈래로 나누어서 관리할 수 있다.
* Tag: 특정 커밋을 태그해 두는 것이다. 커밋과 태그의 차이점은 커밋의 경우 checkout 하여 내용을 수정할 수 있으나, 태그는 수정이 불가능 하며, 따라서 읽기전용 커밋같은 개념이다. 보통 태그는 소프트웨어의 버전을 릴리즈 할 때 사용한다. 예를들어 제품이 1.0 이 릴리즈 될때 태깅을 한번 해 두고 1.1 버전을 개발하면서 그 사이에 만들어지는 브랜치들과 커밋들이 존재하는데 이러한 것들은 커밋으로만 관리하다가 1.1 버전이 완성되는 커밋에 태깅을 해두는 것이다.
<br><br>

### 리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?
`git revert [되돌리고 싶은 commit hash]`

복수의 커밋을 되돌리고 싶을 때는 되돌리고 싶은 commit의 범위를 인수로 지정해주면 된다.
`git revert HEAD~3`

만약 revert한 결과를 stage 상태만 유지하고, commit 하지 않으려면 `--no-commit` 옵션을 추가한다.
