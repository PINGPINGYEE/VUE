# VUE.JS 학습

### vue 설치 및 실행 방법
1. ```npm install -g @vue/cli``` 명령어를 통해 전역에 vue 설치
    > yarn이 있으면 ```yarn global add @vue/cli``` 명령어 사용
2. ```vue create [project name]``` 명령어를 통해 vue 프로젝트 생성
3. ```cd [project name]``` 명령어를 통해 project로 진입
4. ```code . -r``` 명령어를 통해 해당 코드 열기
    > 새 창에서 열고 싶은 경우 ```code .```만 입력
5. 명령어를 통해 프로젝트 실행
    > ```npm run serve```가 기본 명령어

### Extention
1. Vetur
2. HTML CSS Support
3. Vue 3 Snippets

### PC가 Vue 명령어를 인식 못할 시
1. Windows PowerShell을 관리자로 실행
2. Get-ExecutionPolicy 명령어로 실행 정책 체크(Restricted)
3. Set-ExecutionPolicy RemoteSigned 명령어로 실행 정책 변경
4. Y를 입력하여 동의
5. Get-ExecutionPolicy 명령어로 실행 정책 변경 체크

### 학습 표
프로젝트 | 명령어 | 내용 
-- | -- | --
01 | dev | 템플릿을 이용한 프로젝트 생성
02 | serve | 일반적인 방법으로 프로젝트 생성
03 | serve | 라이프사이클 훅에 대한 설명
04 | serve | 템플릿 문법 학습
05 | serve | computed 개념 및 실습
06 | serve | caching, getter&setter 학습
07 | serve | watch 개념 및 실습
08 | serve | 바인딩으로 class 선언
09 | serve | 바인딩으로 style 선언
10 | serve | 조건문을 이용한 렌더링
11 | serve | 반복문을 이용한 리스트 렌더링
12 | serve | 메소드를 이용한 이벤트 렌더링
13 | serve | 각종 이벤트 수식어
14 | serve | key 관련 수식어
15 | serve | form 입력 바인딩
16 | serve | 입력 관련 v-model 수식어
17 | serve | component 기본
18 | serve | 컴포넌트 간 상속
19 | serve | emit 개념 및 실습


### 결격 사유
* vue 5일차(2/23) 학습은 출장으로 인한 불참