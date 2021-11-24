# nest js

https://nomadcoders.co/nestjs-fundamentals/lobby 강의를 보고 공부한 nestjs 기초

## 메모

---

### 시작

- $ npm i -g @nestjs/cli //nestjs 설치
- $ nest new //프로젝트 생성
- $ npm run start:dev //프로젝트 실행
- $ nest //명령어 모음

---

### 구조

- app.module
  - nestjs는 여러개의 모듈을 가진다.
- controller
  - express의 라우터 역할. HTTP 요청을 받음.
  - ex) express의 app.get() -> nest의 @Get()
  - provider는 controller에 DI 디자인패턴을 이용하여 constructor를 통해 private으로 주입됨.
- provider(service)

  - 비지니스 로직을 담당하는 부분.
  -

- 데코레이터
  - https://docs.nestjs.kr/custom-decorators
  - injectable() 이란?
  - @Param() //url의 파라미터를 가져옴
  - @Body() //request의 body를 가져옴
  - @Query() //url의 쿼리를 가져옴
  - @Req(), @Res()

---

### validation part

- DTO 란?
  - Data Transfer Object의 약자
  - 유효성 검사를 하기 위해 사용
- validationPipe
  - whitelist 를 true 로 설정하면 validator는 decorator가 없는 속성을 제거 후 저장한다.
  - forbidNonWhitelisted (whitelist : true 가 선행되어야 함) 를 true로 설정하면 whitelist에 없는 속성을 받을경우 HttpException을 던진다.
  - transform 를 true로 설정하면 client에서 보낸 데이터를 서버가 원하는 자료형으로 자동변경해줌.
- extends PartialType('TestDto') TestDto를 본따 전부 필수사항이 아니게 설정.

---

### 테스트

#### 실행

- 유닛 테스트
  - npm run test
    - npm run test:cov
    - npm run test:watch
- e2e 테스트
  - npm run test:e2e

#### 메모

- jest란? 자바스크립트 테스트를 쉽게하는 npm 패키지
- e2e란? 사용자 관점에서 테스트 하는 방법.
- it - 테스트 내용?
- describe - 테스트 제목?
- beforeEach - 테스트를 하기 전에 실행되는 것
- beforeAll - ?

---

### 기타

- Nest는 2개의 프레임워크 위에서 돌아간다.???
  - Express 의 기능을 그대로 쓸 수 있지만, 추천을 하지 않음.
    - @Req(), @Res() 를 이용해 express 의 req res를 사용할 수 있음
  - 온전히 nest의 기능만 사용해야 프레임워크를 전환할 때 에러가 나지않음?
