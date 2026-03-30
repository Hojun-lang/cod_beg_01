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
```


