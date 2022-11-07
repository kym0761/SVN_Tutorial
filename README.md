# SVN_Tutorial
 
준비물 : Visual SVN Server / Tortoise SVN

## VisualSVN

~~~~
1. Visual SVN Server를 설치한다. (링크 : https://www.visualsvn.com/downloads/)
~~~~

<img src="VisualSVNServer01.png" width="50%">

~~~~
2. 실행하고 Repository를 만들어준다.
~~~~

<img src="VisualSVNServer02.png" width="50%">

~~~~
3. User / Group을 생성한다. (선택임. 로컬에서만 사용한다면 굳이 할 필요는 없음.)
~~~~

<img src="VisualSVNServer03.png" width="50%">

~~~~
4. 생성한 Repository의 Properties에 들어가서 Group을 ADD한다. (선택임. 로컬에서만 사용한다면 굳이 할 필요는 없음.)
5. 생성한 Repository를 확인한다.
~~~~

## Tortoise SVN

~~~~
1. Tortoise SVN을 설치한다.
~~~~

<img src="tortoise01.png" width="30%">
<img src="tortoise02.png" width="30%">

~~~~
2. 빈 폴더를 만들고, 빈 폴더에서 위에 Visual SVN Server로 만든 Repository URL을 입력하여 SVN Checkout을 한다.
3. Tortoise SVN의 Commit 기능으로 Saved, Intermediate, DerivedDataCache 등을 Ignore 처리한다.
4. 필요한 데이터들은 Add한다.
~~~~


Visual SVN Server로 만든 Repository는 로컬에서 TortoiseSVN으로 해당 Repository안에 새 Repository를 만드는 행위는 하지않도록 주의해야한다.
db 폴더에 데이터를 저장하는데, TortoiseSVN으로 Repository를 생성하면서 .svn 파일이 생성되고, db 폴더를 Add하게 되면, 재귀적으로 저장되어 프로젝트 크기가 미치도록 커진다.
생성한 Server는 VisualSVN Manager 이외엔 외부에서 건드리지 않도록 하자.

나중에 관리하기 쉽도록 큰 에셋들을 한번에 다 Add하지 말고 적당한 양으로 분할해서 Add하자.
한번에 다 Add하면 db 리비전 n에 전부 그 에셋들이 저장되므로 나중에 db의 해당 리비전 파일이 손상되면 문제가 생길 가능성이 있음.
예시) 리비전 1에 100GB 에셋을 전부 저장하면 리비전 1 db 용량이 100기가임. 

VDFS(VisualSVN Distributed File System)로 만들면 백업용으로 사용은 가능할테지만, 일단 사용하지 않을 예정.
기본으로 사용하면, 해당 리포지토리 컴퓨터가 터지면 SVN 사용이 불가능하고 새로 만들어야함.
