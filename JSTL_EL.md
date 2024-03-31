## JSTL & EL

JSTL(Jakarta Standard Tag Library)과 EL(Expression Language)은 JSP(JavaServer Pages)에서 동적인 웹 페이지를 더 쉽게 구현할 수 있도록 도와주는 기술들입니다. 이들은 JSP에서 자바 코드의 사용을 줄이고, 보다 표현력 있고 간결한 방식으로 웹 페이지의 로직을 표현할 수 있도록 설계되었습니다.

### JSTL

JSTL은 JSP 페이지 내에서 조건문, 반복문 등의 프로그래밍 로직을 처리하거나, 국제화(i18n), 데이터베이스 접근, XML 문서 처리 등을 위한 커스텀 태그 라이브러리의 모음입니다. JSTL은 태그를 사용하여 JSP 페이지에서 자바 코드의 사용을 최소화하고, 페이지의 가독성과 유지 보수성을 향상시킵니다.

JSTL은 다음과 같은 기능별 태그 라이브러리로 구성됩니다:

- **Core 태그 라이브러리**: 변수 선언, 조건문, 반복문, URL 처리 등의 기본적인 작업을 수행합니다.
- **Formatting 태그 라이브러리**: 숫자, 날짜, 시간 포맷팅 및 다국어 지원 등의 기능을 제공합니다.
- **SQL 태그 라이브러리**: 직접적인 데이터베이스 접근과 관련된 태그를 제공합니다. (사용을 자제하는 것이 좋습니다.)
- **XML 태그 라이브러리**: XML 문서의 처리와 관련된 태그를 제공합니다.
- **Functions 태그 라이브러리**: 문자열 처리 등의 함수를 제공합니다.

### EL

EL은 JSP 2.0 부터 도입된 간단한 표현 언어로, JSP 페이지 내에서 자바 객체의 속성에 쉽게 접근하고 조작할 수 있도록 설계되었습니다. EL은 JSTL 태그와 함께 사용되어 JSP 페이지의 표현력을 크게 향상시킵니다.

EL의 주요 기능은 다음과 같습니다:

- **단순한 문법**: 자바 프로퍼티, 메서드 호출, 산술 연산, 논리 연산 등을 간단한 문법으로 표현할 수 있습니다.
- **암시적 객체 접근**: `request`, `session`, `application` 등의 JSP 내장 객체에 대한 암시적 접근을 지원합니다.
- **컬렉션 접근**: 배열, 리스트, 맵 등의 컬렉션 요소에 접근할 수 있습니다.
- **표현식의 결합**: JSTL 태그 내에서 EL 표현식을 사용하여 동적인 데이터 처리를 간결하게 표현할 수 있습니다.

### 예제들

#### 예제 1: 변수 출력
**JSP 구문**:
```jsp
<%= request.getParameter("username") %>
```
**EL 변환**:
```
${param.username}
```

#### 예제 2: 조건문
**JSP 구문**:
```jsp
<%
    if (session.getAttribute("user") == null) {
%>
    <p>Guest</p>
<%
    } else {
%>
    <p>Welcome back!</p>
<%
    }
%>
```
**EL 변환 (JSTL의 c:if 태그와 함께 사용):**:
```
<c:if test="${empty sessionScope.user}">
    <p>Guest</p>
</c:if>
<c:if test="${not empty sessionScope.user}">
    <p>Welcome back!</p>
</c:if>
```

#### 예제 3: 반복문
**JSP 구문**:
```jsp
<%
    List<String> items = (List<String>) request.getAttribute("items");
    for (String item : items) {
%>
    <p><%= item %></p>
<%
    }
%>
```
**EL 변환 (JSTL의 c:forEach 태그와 함께 사용)**:
```
<c:forEach var="item" items="${items}">
    <p>${item}</p>
</c:forEach>
```

#### 예제 4: 객체 속성 접근

**JSP 구문**:
```jsp
<%= ((User) session.getAttribute("user")).getName() %>
```
**EL 변환 (JSTL의 c:forEach 태그와 함께 사용)**:
```
${sessionScope.user.name}
```
