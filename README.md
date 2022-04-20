# GraduationProject

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
        아래의 경우는 예시이며, 더 다양한 방법으로도 사용 가능하다. 
        Integration branch: 언제든지 배포가 가능한 안정적인 버전, 일반적으로 master branch가 이에 해당한다.
        Topic branch: 
            버그수정, 업데이트, 기능추가 등 특정 Topic에 대한 작업을 하는 branch. 
            Topic branch에서 작업이 완료되면 다시 Integration branch로 합친다.

    branch의 생성: 
        branch 명령어를 통해 생성 가능하다. 
        vscode에서는 명령 팔레트를 이용해 간편하게 생성 가능하다. 

    branch의 사용:
        branch의 전환: 
            checkout 명령어를 통해 branch를 변경 가능하다. 
            vscode에서는 화면 좌측하단에서 간편하게 변경 가능하다. 
        HEAD: 
            현재 checkout된 branch의 가장 선두(최신 commit)을 의미한다. 
            혹은 현재 checkout된 branch 자체를 의미한다고 봐도 될 듯. 
        stash: 현재로선 알 필요 없어보임 
    
    branch의 통합: merge와 rebase 두 방법이 있다.
        통합은 merge와 base로 하지만, fast-forward와 non-fast-forward의 개념으로 분류하여 이해하자. 
        주의:
            통합은 branch가 갈라지는 부분부터 수행되며, 갈라지기 이전 부분은 영향이 없다.
            통합은 일반적으로 topic을 integration에 하지만, 반대의 경우도 가능하므로 경직되게 생각할 필요 없다.
        가정: Base branch에서 New branch로 갈라져 나왔다고 생각하자. 이때 갈라져나온 부분은 Cross commit이다. 
        fast-forward: 
            두 branch가 하나의 branch가 되며 합쳐지는 것  
                Base가 New로 통합되면, Base의 Cross commit부터 HEAD까지가 New의 이력으로 변한다.
                New가 Base로 통합되면, New의 이력이 모두 Base의 이력으로 변하며, New branch는 존재 흔적이 사라진다.
            merge: 
                New가 생긴 후 Base에 변화가 없었다면, fast-forward, non-fast-forward 선택 가능 
            rebase: 
                New를 Base로 합친다면, New의 이력을 Base의 이력 뒤로 옮겨버린다.(반대의 경우 Cross commit부터 Base의 HEAD까지를 New의 뒤로 옮긴다.)
                이때 충돌이 발생한 모든 commit을 수정한다.
                항상 fast-forward라 볼 수 있다. 
        non-fast-forward
            두 branch를 유지하면서, HEAD의 내용만을 합쳐 둘중 한 branch에 새롭게 commit하는 것 
            branch 기록이 남아있어 추후 관리하기 편하다.
            merge: 
                New의 HEAD와 Integration의 HEAD를 병합하며, New혹은 Integration에 commit한다. 이를 merge commit이라 한다.
                New가 생긴 후 Base의 변화가 있었다면 항상 non-fast-forward
        충돌이 발생할 때 merge vs rebase 
            rebase는 충돌이 발생한 모든 commit을 수정
            merge는 HEAD에 대해서만 합치므로 한번만 수정   
    ```
