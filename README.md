# mvc-practice
comento 

## 1주차 과제 : 개발 환경 구성
 참고자료 : https://level-rosehip-002.notion.site/new-1-073f6b64717f40d49c6b22d0c5143e6c
- JDK 11, IntelliJ IDEA, MariaDB, DBeaver 설치
- DBeaver에 MariaDB 연동, 필요 DB 및 데이터 생성



### 1주차 과제에 대한 질문
applicationContext-webapp.xml의 22번째 라인인 "<mvc:resources mapping="/resources/**" location="/resources/" />"에서 "위치 '/resources/'을(를) 해결할 수 없습니다."라는 오류 메시지가 발생하는데 resources디렉토리를 리소스 디렉토리로 지정했음에도 계속해서 오류가 발생합니다. 오류가 발생해도 실행결과는 잘 나타나긴하나 왜 오류가 발생하는지 어떻게 문제를 해결해야하는지 궁금합니다. 

---

## 2주차 과제 : 인터페이스 가이드 문서 작성
참고자료 : https://level-rosehip-002.notion.site/2-1-API-ec3efdb0e9554296900b3293b0589f73

### REST API에 대해 학습
- 정의 : REST API는 웹에서 사용되는 소프트웨어 아키텍처 스타일이고, HTTP는 이를 구현하는 데 사용되는 프로토콜이다.
- 특징
  - URI를 이용한 자원 식별 : 각 자원은 고유한 URI로 식별된다.
  - HTTP 메서드 활용 : GET, POST, PUT, DELETE 등의 HTTP 메서드를 사용하여 자원에 대한 CRUD 작업을 수항한다.
  - 무상태성 (Stateless) : 서버는 클라이언트의 상태 정보를 유지하지 않으므로, 각 요청은 독립적으로 처리된다.
  - 균일한 인터페이스 : 클라이언트와 서버는 동일한 인터페이스를 통해 통신합니다.
  - 계층화된 시스템 : 클라이언트는 최종 서버에 직접 연결되지 않고, 중간 계층을 통해 통신할 수 있습니다.
  - 캐싱 가능 : 응답 데이터를 캐싱하여 성능을 향상시킬 수 있습니다.

  
1) HTTP 통신에 관하여
 - 정의 : 웹에서 데이터를 주고받기 위한 프로토콜
 - 특징
   - 클라이언트-서버 모델 기반
   - 텍스트 기반 프로토콜
   - 요청(Request)와 응답(Response)로 구성된다.
   - 다양한 미디어 타입 지원
   - 상태 비저장 (Stateless)
 - 역할 : REST API를 구현하기 위한 기본 통신 수단

 - REST API와 HTTP의 관계 : REST API는 HTTP 프로토콜을 기반으로 구현되는 아키텍처 스타일입니다. 즉, REST API는 HTTP를 사용하여 자원을 주고받고 조작하는 규칙을 정의하고, HTTP는 이러한 규칙을 실제로 구현하는 통신 프로토콜입니다. 간단히 말해, REST API는 "어떻게 통신할 것인가"에 대한 설계이고, HTTP는 "어떻게 데이터를 주고받을 것인가"에 대한 규칙입니다. 
   
2) 브라우저에 URL을 입력 후 요청하여 서버에서 응답하는 과정까지에 대해 학습한 내용을 작성
 - 과정 요약
   - 사용자가 /users/123 입력
   - 브라우저가 도메인(IP 주소) 찾음 (DNS)
   - 브라우저가 서버에 GET /users/123 요청
   - 서버는 DB에서 사용자 123을 조회
   - 사용자 정보를 JSON 형식으로 응답
   - 브라우저가 응답 데이터를 처리하여 사용자에게 보여줌

   (1) 사용자 조회
   - URI: /users/{user_id} (예: /users/123)
   - HTTP Method: GET (조회)
   - 응답: 사용자 정보 (JSON 형식 등)
  
   (2) 사용자 전체 목록 조회
   - URI : /users
   - HTTP Method : GET (목록 조회)
   - 응답 : 사용자 목록 (JSON 배열 형식)

   (3) 사용자 생성
   - URI : /users
   - HTTP Method : POST (등록)
   - 요청 본문 : 
     {
       "name": "홍길동",
       "email": "hong@example.com"
     }
   - 응답: 생성된 사용자 정보 (JSON 형식, 201 Created)

   (4) 사용자 정보 수정
   - URI : /users/{user_id}
   - HTTP Method : PUT (전체 수정)
   - 요청 본문 :
     {
       "name": "홍길동",
       "email": "hong@example.com"
     }
   - 응답 : 수정된 사용자 정보 (JSON 형식)

   (5) 사용자 삭제
   - URI : /users/{user_id}
   - HTTP Method : DELETE (삭제)
   - 응답 : 상태 코드 204 No Content (응답 본문 없음)
   
