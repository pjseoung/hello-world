
# **GIT 명령어**

### **1. 디렉토리 만들기**
  * mkdir 폴더이름
  * cd 폴더이름

### **2. 환경설정**
  * git config --global --list : 현재 설정정보 조회할 수 있다. <br>
                                global옵션은 전역설정에 대한 옵션이며 현재 프로젝트에만 적용할때는 주지 않는다.
  * git config --global user.name "깃허브이름“
  * git config --global user.email "깃허브이메일주소"
  * git config --global color.ui “auto” : 터미널에 표시되는 메시지에 칼라를 표시해줌

### **3. 저장소 만들기**
  * git init : 깃 저장소 초기화
            이 명령을 해줘야 폴더가 git 폴더로 바뀌어 깃 명령어를 사용할 수 있다.      
  * git config : 처음에 깃을 설정할 경우 사용하는 명령어 
  * git status : 깃의 저장소의 상태를 나타냄(commit되지 않은 파일 목록을 보여 줌)
  * git add : 처음 파일을 만들었을 때 처음에 git은 파일을 무시하다가 add로 파일을 선언해줘야만 git이 인식해 사용할 수 있게 함
  * git commit : 어떤 변경사항이 발생했을 경우 저장소의 스냅 샷을 기록하기 위해 이 명령어를 사용 <br>
                 --amend 옵션 : 직전에 commit 메시지를 수정<br>
                 -am 옵션 : add 와 commit 을 동시 진행
                 
### **4. commit에서 삭제한 파일 복구**
  * git checkout 커밋아이디 : commit id 시점으로 복구
  * git checkout 커밋아이디 파일명 : 지정된 파일만 복구
  * git checkout master : 최근 commit으로 복구<br>
                         ->주의 checout 후에 add와 commit을 새로 해줄 것

### **5. Branch와 Tag**
  * git branch : 지역 브랜치 목록 보기
  * git branch -r : 원격 브랜치 목록 보기
  * git branch -a : 지역과 원격을 포함한 모든 브랜치 목록 보기
  * git branch <새로운 브랜치> : 현재 브랜치에서 새로운 브랜치 생성하기
  * git checkout <브랜치> : 다른 브랜치 체크아웃 
  * git checkout -b <새로운브랜치> : 현재 브랜치에서 새로운 브랜치 생성하고 체크아웃
  * git checkout <새로운브랜치><브랜치를 생성할 위치> : 다른 시작 지점에서 브랜치 생성
  * git branch -f <기존 브랜치> [<브랜치를 생성할 위치>] : 기존의 브랜치를 새로운 브랜치로 덮어쓰기  
  * git checkout -m <기존 브랜치> <새로운 브랜치> : 새로운 브랜치명이 존재하지 않을 경우 브랜치를 옮기거나 브랜치명 변경하기
  * git checkout -M <기존 브랜치> <새로운 브랜치> : 무조건 덮어쓰기
  * git merge <브랜치> : 다른 브랜치를 현재 브랜치로 합치기
  * git merge - -no-commit <브랜치> : 커밋하지 않고 합치기
  * git cherry-pick <커밋명> : 선택하여 합치기
  * git cherry-pick -n <커밋명> : 커밋하지 않고 선택하여 합치기
  * git merge - -squash <브랜치> : 브랜치 이력을 다른 브랜치에 합치기
  * git branch -d <삭제할 브랜치> : 삭제할 브랜치가 현재 브랜치에 합져졌을 경우에만 삭제
  * git branch -D <삭제할 브랜치> : 삭제할 브랜치가 현재 브랜치에 합쳐지지 않았어도 삭제
 
### **6. 원격저장소(githum.com)연결, 이름변경**
  * git clone <저장소> : 저장소 복제
  * git clone - -depth 200 <저장소> : 마지막 200개의 커밋만 포함하여 저장소 복제
  * git remote add <원격 저장소> <저장소 url> : 새로운 원격 저장소 추가
  * git branch -r : 모든 원격 브랜치 목록 보기
  * git branch <새로운 브랜치> <원격 브랜치> : 원격 브랜치에서 지역 브랜치 생성하기
  * git branch <새로운 브랜치> <원격 태그> : 원격 태그에서 지역 브랜치 생성하기
  * git fetch : origin 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
  * git fetch <원격 저장소> : 원격 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
  * git pull <원격 저장소> : 원격 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
  * git pull : origin 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
  * git push <원격 저장소> <지역 브랜치>:<원격 브랜치> : 지역 브랜치를 원격 브랜치에 푸싱하기
  * git push <원격 저장소> <지역 브랜치> : 지역 브랜치를 동일한 이름의 원격 브랜치에 푸싱
  * git push <원격 저장소> <지역 브랜치> : 새로운 로컬 브랜치를 원격 저장소에 푸싱하기
  * git remote prune <원격 저장소> : 원격 저장소에서 쓸모가 없어진 원격 브랜치 제거하기
  * git remote rm <원격 저장소> : 원격 저장소를 제거하고 관련된 브랜치도 제거하기

### **7. 로그관리**
  * git log : 커밋로그들을 볼 수 있으면 -1나 -2같은 옵션을 주어 출력할 커밋로그의 갯수를 지정 
  * git log 커밋명 : 해당 커밋명의 로그를 볼 수 있다. 
    * 커밋명A..커밋명B (마침표2개)와 같이 입력하면
    * 커밋명A이후부터 커밋명B까지의 로그를 볼 수 있습니다. 
  * git blame 파일명 : 갈 줄 앞에 커밋명과 커밋한 사람등의 정보를 볼 수 있다. 
  * git blame -L 10,15 파일명 : -L 옵션을 사용하면 10줄부터 15줄로 범위를 지정해서 볼 수 있고 <br>
                              *** 15대신 +5와 같이 사용할 수 있다.숫자의 범위 대신 정규식도 사용이 가능
  * git blame -M 파일명 : -M 옵션을 사용하면 반복되는 패턴을 찾아서 복사하거나 이동된 내용을 찾아준다.  
  * git revert 커밋명 : 기존의 커밋에서 변경한 내용을 취소해서 새로운 커밋을 만든다
  * git reset 커밋명 : 이전 커밋을 수정하기 위해서 사용합니다. 
  * git rebase -i 커밋범위 : -i옵션으로 대화형모드로 커밋 순서를 변경하거나 합치는 등의 작업을 할 수 있다

# **MARKDOWN**

### **문법**
######  1. 제목  
    <h1>부터 <h6> 까지 표현 
    # Heading ->h1, ### Heading -> h3 
    #의 개수의 따라서 h# 구분 
    h1이 크기가 제일 크다 
     
######  2. 강조
    1)<em> : 기울여 쓰기/같은 동작*,_
       *강조한*텍스트 or _강조한_텍스트 ->강조한부분이 강조된다
    2)<strong> : 굵게쓰기/같은동작 **,__
       **강조한**텍스트 or __강조한__텍스트 ->강조한부분이 강조된다
    3)<del> : 
       취소선 ~~ 
       ~~취소한~~텍스트 ->취소한부분이 취소된다
    4)<u></u>(밑줄) <br>

######  3. 목록  
    1)순서가 없는 리스트(Unordered List) : <ul>
       *HTML *CSS *JavaScript or -HTML -CSS -JavaScript
       * 또는 -를 사용해서 작성
       tab 또는 2칸 띄어쓰기를 통해 중첩된 항목을 작성할 수 있다.
    2)순서가 있는 리스트(Ordered List) : <ol>
       - 1. HTML, 2. CSS, 3. JavaScript 숫자를 사용해서 작성

######  4. 링크  
    1)인라인 링크 
         [Google](http://www.google.co.kr “구글”)
         -> 실핼결과 Google       
    2)참조 링크 
         [Google][1] 
         [Naver][2]
         [1]: http://google.com/ “구글”
         [2]: http://naver.com/ “네이버” 
         -> 실핼결과 Google
                      Naver
    3)URl 링크
         <http://google.com/>
         <example@gmail.com/> 
         -> 실핼결과 http://google.com
                      example@gmail.com 

######  5. 이미지  
    <img>

######  6. 코드강조  
    pre>,<code>
    인라인 코드강조 : `(Grave)를 입력하세요.
    블록 코드 강조 : ``` or ~~~ 3번 이상 입력하고 코드 종류도 적는다

######  7. 표  
    <table> </table>

######  8. 인용문  
    <blockqute>

######  9. 수평선 
    ---(Hyphens), ***(Asterisks), ___(Underscores)
    각 기호를 3개 이상 입력 (단, -을 사용할 경우 header로 인식할 수 있으니 이 전 라인은 비워두어야한다.) *
         
######  10. 줄바꿈 : 
    <br> or 띄어쓰기 2번
