# GraduationProject

# make git repository clone 
    git clone 명령어 실행 -> 경로 설정 -> git주소 입력 

# vscode에서 git 사용하기 
1. git repository를 vscode에 clone 하기
    ```
    git clone 명령어 실행 -> 경로 설정 -> git주소 입력
    ```
2. branch 의 개념 이해하기 
    ```
    참고 주소: https://backlog.com/git-tutorial/kr/stepup/stepup1_1.html 

    branch: 
        개념: 기존 작업물에 영향을 주지 않고 독립적인 작업을 할 수 있는 영역
        목적: 하나의 파일에 여러명이 작업을 하는 등 여러 버전이 존재할 때, branch를 이용하면 서로 간섭받지 않고 수정이 가능하다. 
        사용법: branch가 필요할 때 새로운 branch를 생성하여 독립적인 작업을 한 후에, branch를 병합하여 하나의 결과물로 합칠 수 있다.
        장점: 
            각 branch는 서로 간섭받지 않아 작업시 편리하다.
            branch마다 기록이 남기 때문에, 추후에 feedback하기 좋다. 
        사용예시: 
            문제를 풀 때 A라는 방법과 B라는 방법이 존재한다면, branch를 이용해 두 방법 모두 시도해 볼 수 있다. 
            지금 당장은 A라는 방법을 사용하였더라도, B의 기록이 남아 있으므로 추후 B로 바꾸기도 용이하다.  

    branch의 분류:
        Integration branch: 언제든지 배포가 가능한 안정적인 버전, 일반적으로 master branch가 이에 해당한다.
        Topic branch: 
            버그수정, 업데이트, 기능추가 등 특정 Topic에 대한 작업을 하는 branch. 
            Topic branch에서 작업이 완료되면 다시 Integration branch로 합친다.

    ```
