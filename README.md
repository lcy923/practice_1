[1]원격 저장소와 로컬 저장소
-원격 저장소(Remote Repository) : 파일이 원격 저장소 전용 서버에서 관리되며 여러 사람이 함께 공유하기 위한 저장소
-로컬 저장소(Local Repository) : 내 PC에 파일이 저장되는 개인 전용 저장소
[2]커밋
-파일 및 폴도의 추가/변경 사항을 저장소에 기록하기 위해서는 '커밋'이 필요함
-커밋 의 변경 내용을 요약 -> 빈칸 -> 변경한 이유 를 적는 것을 권장
[3]작업 트리(Work tree)와 인덱스(Index)
-작업 트리 : 흔히 말하는 폴더를 말함
-인덱스 : 커밋을 실행하기 전의 저장소와 작업 트리 사이에 존재하는 공간이 인덱스
[4]저장소 공유
-push : 내 PC의 로컬 저장소에서 변경된 이력을 원격 저장소에 공유하기 위해 로컬 저장소의 변경 이력을 원격 저장소에 업로드
-clone : 누군가의 변경 이력이 적용된 원격 저장소가 있으면, 그걸 웹에서 통째로 복사
-pull : 다른사람이 원격 저장소에 올려놓은 변경 내용을 내 로컬 저장소에도 적용
[5]브랜치 전략
-master : master 브랜치에 merge된 내역은 새로운 버전이 갱신되었다는 것을 의, 변경 내역이 생기면 최종 버전인 Tag를 통해 배포
-develop : 모든 변경 내역이 출발하는 지점, develop브랜치의 코드가 안정화되고 배포할 준비가 되면 master를 통해 배포 버전의 태그를 담.
-feature : 배포하려고 하는 기능을 개발하는 브랜치
[6]주요 Commands
-소스코드의 origin 저장소를 초기화하고 remote 서버와 처음으로 연결할 때
: git init 명령을 통해 git프로젝트로 초기화 할 수 있음.
-git add, commit // git commit -am 으로 add commit 동시에 실행 가능
: git flow 의 첫단계에 해당되며 인덱스에 새로운 파일이 생겼다는 것을 알리는 행위, 저장소에는 반영이 되지 않은 상태이며 git commit 를 통해 비로소 저장소에 변경내역이 반영.
-git push // git push (-u) origin master (-u는 히스토리 기억하고 반영)
: commit 이 완료된 시점은 변경 내용이 로컬 저장소에 HEAD안에 머물고 있음을 의미, 우리는 변경 내역을 동료들도 확인할 수 있도록 remote 서버에 반영할 필요가 있음.
-git pull // git pull <remote> <branch>
: 서버의 가장 최근의 변경 내역을 컴퓨터로 가져오는 행위.
-git checkout -b develop : develop이라는 branch 새로 만들기
-git checkout -b develop origin/stage : stage 라는 특정 branch로부터 새로운 branch 만들기
-git checkout master : master branch로 돌아오기
-git push -u origin develop 
-git branch --set-upstream-to=origin/develop develop
-git pull : branch 를 여러명과 협업하고 있는 도중 push시에 remote 서버의 최신 내용을 로컬에 반영하지 않았다면 remote 서버와 연결 후 git pull 을 통해 merge
