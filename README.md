# SVN_Tutorial
 
준비물 : Visual SVN Server / Tortoise SVN


1. Visual SVN Server를 설치한다. (링크 : https://www.visualsvn.com/downloads/)
2. 실행하고 Repository를 만들어준다.
3. User / Group을 생성한다.
4. 생성한 Repository의 Properties에 들어가서 Group을 ADD한다. (선택임. 로컬에서만 사용한다면 굳이 할 필요는 없음.)
5. 생성한 Repository를 확인한다.

~~~~

1. Tortoise SVN을 설치한다.
2. 빈 폴더를 만들고, 빈 폴더에서 위에 Visual SVN Server로 만든 Repository URL을 입력하여 SVN Checkout을 한다.
3. Tortoise SVN의 Commit 기능으로 Saved, Intermediate, DerivedDataCache 등을 Ignore 처리한다.
4. 필요한 데이터들은 Add한다.

~~~~

Visual SVN Server로 만든 Repository는 로컬에서 TortoiseSVN으로 해당 Repository를 새 Repository를 만드는 행위는 하지 말아야한다.
db 폴더에 데이터를 저장하는데, TortoiseSVN으로 Repository를 생성하면서 .svn 파일이 생성되고, db 폴더를 Add하게 되면, 계속 중복 저장하여 프로젝트 크기가 미치도록 커진다.
Server는 Server일 뿐이라 생각하고 그 이후에 건들지 말자

나중에 관리하기 쉽도록 큰 에셋들을 한번에 다 Add하지 말고 적당한 양으로 분할해서 Add하자.

VDFS(VisualSVN Distributed File System)로 만들면 백업용으로 사용은 가능할테지만, 일단 사용하지 않을 예정.
기본으로 사용하면, 해당 리포지토리 컴퓨터가 터지면 SVN 사용이 불가능하고 새로 만들어야함.

추후 이미지 넣고 문서 수정 예정