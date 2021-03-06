# Bash Shell 사용
  - Bash Shell 기본
  - 기본 명령어 1 (Basic Commands1 )
  - 참고 : CLI 사용 이유

---

## Bash Shell 기본
  ### 1. 기본 명령어의 구조
  - "command name" "Options(flags)" /"Arguments"
  - ex> `ls -l /etc`

  ### 2. Shell의 기본
  - Shell이란 사용자가 실행을 입력하고 관리하는 명령을 해석한다.
  - Shell의 종류에는 tcsh, csh, korn 및 "bash" 가 존재하며 최근에는 거의 Bash shell 로 통합되고 있다. (각 쉘마다 미묘한 차이 존재)
  - 로그인에 성공하면 쉘 프롬프트가 표시된다.

  ### 3. Shell의 특징
  - Shell 명령어는 대소문자를 구분 한다. (Linux는 대소문자를 구분)
  - Linux 는 여러개의 명령을 동시에 실행할 수 있다.
  - 사용자 공간(User Space)는 두 가지 권한이 존재 한다.
    - `$` : 사용자
    - `\#` : root (관리자)
  - reset : 화면을 다시 초기화 한다.
  - Autocomplete(자동완성)
    - 명령 및 파일 이름을 자동으로 완성시킨다.
    - $ PATH의 명령지정된 경로의 파일 이름
  - Linux는 두가지 foreground와 background가 존재하며 실행시킨 프로세스는 background에서 실행된다.

  ### 4. 몇가지 단축키
  - `tab` : 명령어의 일부만 입력하면 자동으로 검색해준다.
  - `CTRL-R` : 지난 명령어 이력을 검색
    - `$ history` 명령으로도 지난 명령어 이력을 출력할 수 있음.
    - 또한 arrow keys 를 사용해 지난 이력을 보거나 실행할 수 있음.
  - `CTRL-L` : Clear 명령어(스크린의 명령줄을 지워준다.)
    - $ clear 명령어와 동일
  - `CTRL-D` : 로그아웃, 파일을 종료
  - `CTRL-C` : Stop
  - `CTRL-Z` : Suspend
  - `CTRL-E` : cut to end of line
  - `CTRL-U` : cut to start of line

---


## 기본 명령어 1 (Basic Commands 1)
  ### 1. pwd
  - 지금 어느 위치에 있는지 알려준다.
  - 사용법 : `pwd`

  ```
  pwd   // 현재 디렉토리 위치를 출력
  ```

  ### 2. cd
  - 디렉토리를 이동한다.
  - 사용법 : `cd {인자값}`

  ```
  cd        // /home 디렉토리로 이동 (/home/ubuntu 와 같이 이동)
  cd ~      // /home 디렉토리로 이동
  cd ..     // 상위 디렉토리로 이동
  cd -      // 이전 작업 디렉토리로 이동
  cd /etc   // /etc 디렉토리로 이동 ("/" 을 사용하면 한번에 이동 가능)
  cd myapp  // myapp 디렉토리로 이동
  ```

  ### 3. ls
  - 디렉토리와 파일의 정보를 출력한다. (약어 : list)
  - 사용법 : `ls {옵션} {디렉토리/파일}`
    - `-a` : 모든 파일과 디렉토리 표시
    - `-l` : 자세히 출력
    - `-d` : 디렉토리 정보 출력
    - `-n` : UID, GID 출력
    - `-R` : 하위 경로와 모든 파일 나열
  - 그 외에도 소팅 등 줄 수 있다.

  ```
  ls                      // 디렉토리 파일 정보를 간략하게 보여준다.
  ls -l                   // 디렉토리 파일정보를 자세히 보여준다.
  ls -a                   // 모든 디렉토리 파일 정보를 간략하게 보여준다.
  ls -al                  // 모든 디렉토리 파일 정보를 자세히 보여준다.
  ls -l --sort=time       // 디렉토리 파일 정보를 시간 순서로 자세히 보여준다.
  ls -al --sort=size -r   // 모든 디렉토리 파일 정보를 파일 크기 순서로 자세히 보여준다.
  ```
  ### 4. clear
  - 터미널을 깨끗하게 지워준다.(혹은 CTRL-L)
  - 사용법 : `clear`

  ```
  clear   // 터미널의 입력창을 깨끗하게 한다.
  ```

  ### 5. mkdir
  - 디렉토리를 만든다. (약어 : make directory)
  - 사용법 : `mkdir {옵션} {이름}`
    - `-m` : 디렉토리 생성 시 기본 권한 설정
    - `-p` : 상위 디렉토리 생성
    - `--help` : 도움말
    - `--version` : 버전 표시

  ```
  mkdir myapp   // 현재 디렉토리에 myapp(디렉토리 이름) 디렉토리를 만든다.
  ```

  ### 6. touch
  - 빈 파일을 만든다. (data는 0 이며, meta 정보만 존재한다.)
  - 사용법 : `touch {옵션} {파일이름}`
    - `-r` : 시간 동기화
    - `-t` : 지정 시간으로 변경
    - `-a` : 접근 시간 변경
    - `-m` : 수정 시간 변경

  ```
  touch test1         // 현재 디렉토리에 test1(파일 이름)을 만든다.
  touch myapp1/good   // myapp1 디렉토리에 good(파일 이름)을 만든다.
  ```

  ### 7. cp
  - 파일을 복사한다. (약어 : copy)
  - 사용법 : `cp {옵션} {복사소스} {복사위치}`
    - `-f` : 강제로 복사
    - `-r` : 하위 디렉토리를 포함하여 복사
    - `-v` : 복사 진행 상황 출력
    - `-s` : 링크 정보 유지하여 복사
  - 파일 생성후 바로 cp명령어를 사용하면 사용 중이기 때문에 'omitting directory'에러가 발생하므로 -r 옵션으로 강제로 복사하도록 한다.

  ```
  cp test1 test2        // 현재 디렉토리에 test1을 복사하여 test2를 만든다. (파일)
  cp -r myapp1 myapp2   // 현재 디렉토리에 myapp1을 복사하여 myapp2를 만든다. (디렉토리)
  ```

  ### 8. rm
  - 파일을 지운다. (약어 : remove)
  - 사용법 : `rm {옵션} {디렉토리/파일}`
    - `-i` : 삭제에 대한 여부 물음
    - `-f` : 강제삭제
    - `-r` : 디렉토리 삭제 시 하위 경로와 파일 삭제
    - `-v` : 파일 삭제 정보를 자세히 보여줌

  ```
  rm test2      // 현재 디렉토리에 있는 test2 파일을 지운다.
  rm -r myapp3  // 현재 디렉토리에 있는 myapp3 디렉토리를 지운다.
  rm -fr myapps  // 현재 디렉토리에 있는 myapps 디렉토리를 강제로 지운다.
  ```

  ### 9. mv
  - 디렉토리를 옮기거나 변경한다. (약어 : move)
    - 입력한 디렉토리가 존재할 경우 그 디렉토리의 하위 디렉토리로 옮긴다.
    - 입력한 디렉토리가 존재하지 않을 경우 그 디렉토리 이름을 변경한다.
  - 사용법 : `mv {옵션} {이동소스} {이동타겟}`
    - `-i` : 이동에 대한 실행 여부 물음
    - `-f` : 강제로 이동
    - `-u` : 이동 대상 위치보다 최근 파일 시 이동
    - `-v` : 이동 진행 상태 출력
    - `-b` : 대상 파일이 이미 있어 백업 파일 생성

  ```
  mv myapp mymvapp  // myapp 디렉토리를 mymvapp 으로 옮기거나 변경한다.
  ```

  ### 10. echo
  - 입력한 내용을 출력한다.
  - 사용법 : `ehco {출력값}`
    - Redirection 과 함께 이용 가능

  ```
  echo hello                // shell에 hello 를 출력한다.
  echo hello >> test.txt    // hello를 test.txt에 append 한다.
  ```

  ### 11. cat & tac
  - cat : 파일 내용을 출력한다.
  - tac : 파일 내용을 역순으로 출력한다.
  - 사용법 : `{cat or tac} ({옵션}) {파일 이름}`
    - Redirection 과 함께 이용 가능

  ```
  cat hello.txt         // hello.txt 파일의 내용을 모두 출력한다.
  tac hello.txt         // hello.txt 파일의 내용을 역순으로 모두 출력한다.
  cat >> hello.txt      // hello.txt 파일에 내용을 append (종료는 Ctrl + D)
  ```

  ### 12. less & more
  - 텍스트 파일 내용을 화면에 읽을 수 있을 만큼씩 출력한다. (종료는 `q` 버튼 클릭)
  - 사용법 : `less {파일 이름}` & `more {파일 이름}`
  - 이는 `cat {파일 이름} | more` 과 동일하다.

  ```
  less hello.txt          // hello.txt 파일의 내용을 화면의 크기만큼 출력한다.
  more hello.txt          // hello.txt 파일의 내용을 화면의 크기만큼 출력하며 More로 표시 및 퍼센테이지를 알려준다.
  ```

  ### 13. chgrp
  - 파일의 사용자 그룹 속성을 변경한다.
  - 사용법 : `chgrp {옵션} {그룹} {파일}`
    - `-c` : 변경된 파일만 자세하게 보여준다.
    - `-f` : 변경되지 않은 파일에 대해서 오류 메시지를 보여주지 않는다.
    - `-v` : 작업상태를 자세히 보여준다.
    - `-R` : 경로와 그 하위 파일들을 모두 변경한다.

  ```
  chgrp bar /home/foo   // bar 속성을 /home/foo 로 변경
  ```

  ### 14. chown
  - 파일의 소유자나 소유그룹을 변경 (보통 모두 바꾸므로 -R 옵션 사용)
  - 사용법 : `chown {옵션} {소유자:소유그룹} {파일}` or `chown {옵션} {소유자.소유그룹} {파일}`
    - `-c` : 변경된 파일만 자세하게 보여준다.
    - `-f` : 변경되지 않은 파일에 대해서 오류 메시지를 보여주지 않는다.
    - `-v` : 작업상태를 자세히 보여준다.
    - `-R` : 경로와 그 하위 파일들을 모두 변경한다.

  ```           
  chown -R foo:bar /home/foo                  // foo:bar 를 /home/foo 로 변경
  chown -R foo:bar bobs --from=nobody:nobody  // bobs 디렉토리 내의 파일중 소유자가 nobody이고 소유그룹이 nobody로 되어 있는 파일의 소유자를 foo 변경하고 소유그룹을 bar로 변경
  ```

  ### 15. chmod
  - 파일의 퍼미션을 변경
  - 사용법 : `chmod {옵션} {퍼미션} {파일}`
    - `-c` : 변경된 파일만 자세하게 보여준다.
    - `-f` : 변경되지 않은 파일에 대해서 오류 메시지를 보여주지 않는다.
    - `-v` : 작업상태를 자세히 보여준다.
    - `-R` : 경로와 그 하위 파일들을 모두 변경한다.

  ```
  chmod 755 myfile    // 소유자에겐 7(rwx), 그룹과 나머지에겐 5(r-x) 권한부여
  ```

  ### 16. umask
  -  파일이 만들어질때 허가권 기본값 (777에서 뺀다.)
  - 사용법 : `umask {777-퍼미션}`

  ```
  umask 077   // chmod 722 와 동일 (no one else cand do anything)
  ```

  ### 17. file
  - 파일 타입을 확인한다.
  - 사용법 : `file {파일 or 디렉토리}`

  ```
  file hello.txt   // hello.txt 파일의 타입을 확인
  ```

  ### 18. head & tail
  - head : 파일 내용 중 처음 10줄 출력
  - tail : 파일 내용 중 마지막 10줄 출력
  - 사용법 : `head or tail {파일}`

  ```
  head hello.txt   // hello.txt 내용중 처음 10줄 출력
  tail hello.txt   // hello.txt 내용중 마지막 10줄 출력
  ```

  ### 19. shutdown
  - 전원을 끈다.
  - 사용법 : `shutdown {옵션} {시간}`

  ```
  shutdown 22:30      // 22:30 에 전원을 끈다
  shutdown –r now     // 지금 재부팅 시작
  shutdown –h now     // 지금 바로 전원을 끈다
  ```

---

## 참고사항
  ### 1. CLI를 사용하는 이유
  - app1, app2, … app99 의 폴더를 만들어야 할 경우 GUI 환경에서는 99 번의 폴더 생성 작업을 실행해야 하지만 CLI의 경우 아래의 명령어만으로 99개의 폴더 생성이 가능하다.

  ```
  $ mkdir test        // 폴더를 생성
  $ cd test           // 디렉토리 변경
  $ mkdir app{1..99}  // 폴더를 99개 생성
  ```
---
