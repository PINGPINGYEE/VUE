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
vs_01 | dev | 템플릿을 이용한 프로젝트 생성
vs_02 | serve | 일반적인 방법으로 프로젝트 생성
vs_03 | serve | 라이프사이클 훅에 대한 설명
vs_04 | serve | 템플릿 문법 학습
vs_05 | serve | computed 개념 및 실습
vs_06 | serve | caching, getter&setter 학습
vs_07 | serve | watch 개념 및 실습
vs_08 | serve | 바인딩으로 class 선언
vs_09 | serve | 바인딩으로 style 선언
vs_10 | serve | 조건문을 이용한 렌더링
vs_11 | serve | 반복문을 이용한 리스트 렌더링
vs_12 | serve | 메소드를 이용한 이벤트 렌더링
vs_13 | serve | 각종 이벤트 수식어
vs_14 | serve | key 관련 수식어
vs_15 | serve | form 입력 바인딩
vs_16 | serve | 입력 관련 v-model 수식어
vs_17 | serve | component 기본
vs_18 | serve | 컴포넌트 간 상속
vs_19 | serve | emit 개념
vs_20 | serve | slot 심화 학습
vs_21 | serve | provide와 inject 개념
vs_22 | serve | refs를 학습 및 응용


### 결격 사유
* vue 5일차(2/23) 학습은 출장으로 인한 불참
* SIS 프로젝트 종료 시까지 보류