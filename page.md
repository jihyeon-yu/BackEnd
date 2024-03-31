## 페이지 이동

페이지 이동은 대개 서버 사이드 렌더링(SSR) 또는 클라이언트 사이드 렌더링(CSR)을 통해 이루어진다.

- **서버 사이드 렌더링(SSR)**: 사용자의 요청에 따라 서버에서 HTML을 생성하고 이를 클라이언트로 보낸다. 이 방식은 페이지를 전환할 때마다 서버에 요청을 보내고 새 페이지를 로드한다.
- **클라이언트 사이드 렌더링(CSR)**: 클라이언트(브라우저)에서 JavaScript를 사용해 동적으로 페이지의 내용을 생성하고 변경한다. 이 방식은 SPA(Single Page Application)에서 주로 사용된다.

## HttpServletRequest와 HttpServletResponse

서블릿에서는 주로 두 가지 객체를 사용하여 HTTP 요청과 응답을 처리한다.

- **HttpServletRequest**: 클라이언트로부터 온 요청을 나타낸다. 이 객체를 사용하여 요청 메세지에서 정보를 읽어올 수 있다. 예를 들어 사용자가 입력한 데이터, 쿠키 정보, 세션 정보, 요청 메소드(GET, POST 등) 등을 알아낼 수 있다.
- **HttpServletResponse**: 클라이언트에게 보낼 응답을 나타낸다. 이 객체를 사용하여 응답의 상태 코드를 설정하거나, 응답에 쿠키를 추가하고, 응답 본문에 데이터를 쓸 수 있다.

## doGet()과 doPost()

서블릿은 클라이언트의 요청 타입에 따라 `doGet()` 또는 `doPost()` 메소드를 오버라이드하여 구현한다.

- **doGet(HttpServletRequest request, HttpServletResponse response)**: 클라이언트로부터 GET 요청을 받았을 때 호출된다. 주로 조회 작업에 사용된다.
- **doPost(HttpServletRequest request, HttpServletResponse response)**: 클라이언트로부터 POST 요청을 받았을 때 호출된다. 데이터를 서버로 전송할 때 사용되며, 주로 데이터를 생성하거나 업데이트하는 작업에 사용된다.

## URL 매핑

서블릿을 웹 애플리케이션에 등록하고, 어떤 URL이 해당 서블릿으로 요청을 보낼지 결정하는 과정을 URL 매핑이라고 한다. URL 매핑은 웹 애플리케이션의 'web.xml' 파일 또는 `@WebServlet` 어노테이션을 사용하여 설정할 수 있다.

`@WebServlet` 어노테이션을 사용하면 서블릿 클래스에 직접 URL 매핑을 지정할 수 있다. 이 방법은 서블릿 3.0부터 도입되었으며, 'web.xml' 설정을 대체할 수 있다.
