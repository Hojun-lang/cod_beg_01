## 1) 실행 환경


## 2) 수행 체크리스트
1. [x] 터미널 기본 조작 및 폴더 구성
2. [x] 권한 변경 실습
3. [] Docker 설치/점검
4. [] hello-world 실행
5. [] Dockerfile 빌드/실행
6. [] 포트 매핑 접속(2회)
7. [] 바인드 마운트 반영
8. [] 볼륨 영속성
9. [] Git 설정 + VSCode GitHub 연동

 ## 3) 수행 로그(발췌)

#### 1. 터미널 기본 조작 및 폴더 구성
```bash
milky99259753@c5r2s3 ~ % pwd # 현재 절대 경로 확인
/Users/milky99259753

milky99259753@c5r2s3 ~ % ls # 목록 조회
cod_beg_01	Documents	Library		Music		Pictures
Desktop		Downloads	Movies		OrbStack	Public

milky99259753@c5r2s3 ~ % ls -a # 숨겨진 목록도 표시
.			.viminfo		Downloads
..			.vscode			Library
.CFUserTextEncoding	.zsh_history		Movies
.docker			.zsh_sessions		Music
.orbstack		cod_beg_01		OrbStack
.ssh			Desktop			Pictures
.Trash			Documents		Public

milky99259753@c5r2s3 ~ % mkdir mission_01 # mission_01 디렉토리 생성

milky99259753@c5r2s3 ~ % cd mission_01  # mission_01 디렉토리로 이동

milky99259753@c5r2s3 mission_01 % pwd # 위치 재확인
/Users/milky99259753/mission_01

milky99259753@c5r2s3 mission_01 % touch test.txt # test.txt 파일 생성

milky99259753@c5r2s3 mission_01 % ls # 생성됐는지 확인
test.txt

milky99259753@c5r2s3 mission_01 % echo "hi codyssey" > test.txt # test.txt 파일 안에 "hi codyssey" 텍스트 작성
milky99259753@c5r2s3 mission_01 % cat test.txt # 파일 조회
hi codyssey # 정상적으로 출력됨

### 여기서부터 로컬로 진행 ###

    ~/mission_01 ····················································· 10:35:19  ─╮
❯ cat test.txt                                                                         ─╯
hi codyssey 
    ~/mission_01 ····················································· 10:35:24  ─╮
❯ cp test.txt test_copy.txt # 파일 복사                                                ─╯
    ~/mission_01 ····················································· 10:35:52  ─╮
❯ ls                                                                                   ─╯
test_copy.txt test.txt # 복사된 파일 확인
    ~/mission_01 ····················································· 10:35:54  ─╮
❯ mv test_copy.txt newname.txt # 파일 이름 변경                                        ─╯
    ~/mission_01 ····················································· 10:36:34  ─╮
❯ ls                                                                                   ─╯
newname.txt test.txt # 변경된 파일 이름 확인
    ~/mission_01 ····················································· 10:36:35  ─╮
❯ mkdir backup # 디렉토리 생성                                                         ─╯
    ~/mission_01 ····················································· 10:37:02  ─╮
❯ mv newname.txt backup # newname.txt 파일을 생성한 디렉토리로 이동                    ─╯
    ~/mission_01 ····················································· 10:37:21  ─╮
❯ ls                                                                                   ─╯
backup   test.txt # 목록 확인
    ~/mission_01 ····················································· 10:37:22  ─╮
❯ ls backup                                                                            ─╯
newname.txt # `backup`디렉토리 목록 확인
    ~/mission_01 ····················································· 10:37:30  ─╮
❯ rmdir backup # 디렉토리 삭제                                                         ─╯
rmdir: backup: Directory not empty # 디렉토리가 비워지지 않아 삭제 X
    ~/mission_01 ····················································· 10:38:02  ─╮
❯ cd backup # 디렉토리 진입                                                            ─╯
    ~/mission_01/backup ·············································· 10:38:16  ─╮
❯ rm newname.txt # 파일 먼저 삭제                                                      ─╯
    ~/mission_01/backup ·············································· 10:38:22  ─╮
❯ cd ..                                                                                ─╯
    ~/mission_01 ····················································· 10:38:26  ─╮
❯ rmdir backup # 빈 디렉토리 삭제                                                      ─╯
    ~/mission_01 ····················································· 10:48:34  ─╮
❯ ls                                                                                   ─╯
test.txt # 삭제 확인

### 절대 경로와 상대 경로 ###
    ~/mission_01 ···················································· 00:33:14  ─╮
❯ pwd # 절대 경로 조회                                                                ─╯
/Users/homac/mission_01
    ~/mission_01 ···················································· 00:33:14  ─╮
❯ ls # 현재 디렉토리 내부 목록 확인                                                   ─╯
test.txt
    ~/mission_01 ···················································· 00:33:18  ─╮
❯ cat test.txt # 단순 조회                                                            ─╯
hi codyssey
    ~/mission_01 ···················································· 00:33:27  ─╮
❯ cat ./test.txt # 상대 경로로 조회                                                   ─╯
hi codyssey
    ~/mission_01 ···················································· 00:33:33  ─╮
❯ cat /Users/homac/mission_01/test.txt # 절대 경로로 조회                             ─╯
hi codyssey

### 절대 경로는 루트(Users)부터 시작하는 전체 주소이고, 상대경로는 현재 위치를 기준으로 한 주소이다. 같은 파일이라도 현재 위치에 따라 상대경로 표현은 달라지지만, 절대경로는 불변한다. ###
```

