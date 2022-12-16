# What is Git?
깃은 version control system으로,<br>
여러 사람들이 모여 하나의 프로젝트를 만들 때, 프로젝트의 진행과 수정 사항 등을<br>
한 눈에 보고 쉽게 관리할 수 있도록 하는 시스템이다.

# How to use (전체적인 흐름)
1. `git clone` 을 통해 레포지토리를 클론해오거나, 직접 `git init`명령어를 통해 레포지토리를 만든다.
2. 로컬 저장소를 원격 저장소에 연결
    ```
    // 원격저장소 보기
    git remote -v 
    // 원격 저장소와 연결
    git remote add <저장소이름> <url>
    ``` 
3. git 의 관리하에 있는 프로젝트 내에서 코드를 작성하면, <u>working space</u>에 코드가 저장된다.
4. `git add <file>...`(특정 파일 add) 혹은 `git add .`(모든 파일 add) 을 통해 코드를 working space -> <u>staging area</u>로 올려줄 수 있다.
    - staging area : git commit 전 코드가 잠시 저장되는 공간
    ```
    git status // working space와 staging area에 있는 파일들을 볼 수 있다.
    git restore --staged <file>... // staging area 취소
    ```
5. `git commit -m "type: message"` 를 통해 코드를 staging area -> <u>commit</u> 으로 이동시킬 수 있다.
    ```
    git log // commit에 올라간 파일들을 볼 수 있다.
    git reset --soft HEAD^ // commit 취소
    ```
    - commit message types
        - Feat - 새로운 기능 추가
        - Fix - 버그 수정
        - Build - 빌드 관련 파일 수정
        - Ci - CI관련 설정 수정
        - Docs - 문서 (문서 추가, 수정, 삭제)
        - Style - 스타일 (코드 형식, 세미콜론 추가: 비즈니스 로직에 변경 없는 경우)
        - Refactor - 코드 리팩토링
        - Test - 테스트 (테스트 코드 추가, 수정, 삭제: 비즈니스 로직에 변경 없는 경우)
        - Chore - 기타 변경사항 (빌드 스크립트 수정 등)
6. 연결된 remote 저장소에 변경 사항 push
    ```
    git push origin main
    // origin : 레포지토리 이름
    // main : 브랜치명
    ```




