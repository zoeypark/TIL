# git branch
git clone 후 처음 작업을 시작할 때는 main 브랜치에 위치하게 된다.<br> main 브랜치는 배포할 때 보여지게 될 브랜치이다.
여러명이 함께 여러 가지 기능을 테스트하고 개발하는 과정에서 모두 main 브랜치에만 merge를 하면, conflict도 자주 일어나고, 코드가 꼬이게 된다.<br>

따라서 어떠한 기능을 개발하고자 할 때, branch를 만들어서 나중에 main 브랜치에 PR을 하여 팀원들과 코드리뷰 후 merge하는 것이 좋다.

## branch 종류
- main : 배포 단계까지 완료된 기능들이 최종적으로 merge되는 브랜치
- dev : 보통 기능 단위로 하나의 기능이 완성될 때마다 merge되는 브랜치
- feat : 자잘한 변경사항들이 기록되는 branch (변수명 변경, 테스트 코드 등)

## Create Branch / Switch Branch
- Create
    ```
    git checkout -b <<branch>>
    // or
    git switch -c <<branch>>
    ```
- Switch
git이 바라보는 곳을 HEAD라고 하고, HEAD를 특정 브랜치로 변경하고 싶을 때는 아래 명령어를 사용한다. 
    ```
    git checkout <<branch>>
    // or
    git switch <<branch>>
    ```

## Merge branch
머지를 위해서는 상위 브랜치로 이동한 후, 다음 명령어를 실행한다.
```
git merge <<branch>>
```  

but, local 레포지토리에서 merge하는 것보다는, push & PR 후 팀원들과 github에서 코드리뷰 후 merge하는 approval을 받아 merge 하는 것이 낫다.

## Delete branch
성공적으로 branch가 머지된 경우, 머지된 branch는 삭제하면 된다.
원격 레포지토리에서는 github에서 머지 후 브랜치 삭제 버튼을 눌러 쉽게 삭제할 수 있고, 로컬에서는 아래 명령어를 사용하면 된다. 
    
    ```
    git branch -d feat/todo
    // or
    git branch -D feat/todo // 기능이 완성되지 않아서 branch 삭제가 안되는 경우 사용할 수 있는 명령어
    ```
## git flow
- tip: 레포지토리의 insight 탭 -> network 탭에서 모든 커밋 및 merge 기록을 network graph로 볼 수 있다.

- todo-app을 만들고자 할 때 git flow 예시
1. 구현하고 싶은 기능은 todo 추가 기능이다. 기능 단위 브랜치 dev를 생성하고 이동한다.
    ```
    git checkout -b dev
    ```
    현재 branch를 확인하고 싶다면,
    ```
    git branch
    ```
    ```
    main 
    *dev
    ```
     이런식으로 현재 브랜치를 *로 알 수 있다.

2. todo 추가 기능을 위해 버튼을 구현하고자 한다. feat/todo-btn 브랜치를 생성한다.
    ```
    git checkout -b feat/todo-btn
    ```
    버튼 생성 후, 필요에 따라 commit을 하고, 완성되었다면 dev에 merge 해준다.
    ```
    git switch dev
    git merge feat/todo-btn
    ```

3. 위와 같은 과정을 반복하여 dev에서 하나의 기능이 완성되었으면, main으로 merge해준다.

## merge conflict
여러 사람들과 협업을 하다보면, 코드가 겹쳐서 (동일한 줄에서 서로 다른 변경사항이 있을 때) merge가 안되는 경우가 있다.<br>
다른 사람이 내가 진행하고 있는 동안 동일한 작업을 이미 merge 했을 때 생기는 상황이다.<br>
이런 상황을 conflict(충돌) 상황이라고 한다.<br>
conflict를 미연에 방지하기 위해서는 작업 시작 전에 무조건 fetch/ pull을 통해 기존 branch에서 코드를 끌어와서 merge 해주는 게 좋다.<br>
혹은 이런 상황이 발생했을 때 pull하여 merge하여 해결하면 된다.





