![[Pasted image 20251111090728.png|center|600]]

#### Spring Web MVC의 정의

Spring Web MVC(Model-View-Controller)는 Spring Framework에서 웹 어플리케이션을 개발하기 위한 아키텍쳐 패턴,

#### Model-View-Controller 패턴이란?

애플리케이션을 세 부분으로 분리해 유지보수성과 확장성을 높이는 아키텍처 패턴

- **Model**: 데이터와 비즈니스 로직 관리
- **View**: 사용자에게 보여지는 화면(UI)
- **Controller**: 사용자의 요청을 받아 Model과 View를 연결

즉, 로직(Model)과 화면(View)을 분리하고, Controller가 둘을 중개함으로써 코드 결합도를 낮추는 구조.

#### 간단한 작동 방식

1. 사용자가 View(화면)에서 요청을 보냄
2. Controller가 요청을 받아 적절한 Model(비즈니스 로직) 호출  
3. Model이 데이터 처리 후 결과를 반환
4. Controller가 결과를 View에 전달
5. View가 사용자에게 결과 화면을 렌더링

#### 자세한 작동 방식

![[Pasted image 20251111090728.png|center|500]]

\[요청$\rightarrow$핸들러 선택$\rightarrow$호출$\rightarrow$뷰/바디 변환$\rightarrow$응답\] 순서에 대한 다이어그램 흐름.

1. Request $\rightarrow$ DispatcherServlet  
    모든 HTTP 요청의 진입점(Front Controller).
2. HandlerMapping 
    URL/HTTP 메서드/헤더 등을 기준으로 어느 컨트롤러 메서드(HandlerMethod)가 처리할지 탐색.
3. HandlerAdapter  
    선택된 핸들러를 실제로 호출할 준비:
    - 인자 해석: `@PathVariable`, `@RequestParam`, `@RequestBody`, `HttpServletRequest` 등
    - 바인딩/검증: `DataBinder`, `@Valid`
    - 인터셉터 preHandle 실행
4. Controller 실행 
    서비스/리포지토리 호출로 비즈니스 수행 후 결과 생성.
    - `@Controller`는 주로 뷰 렌더링 전제
    - `@RestController`(= `@Controller + @ResponseBody`)는 바디(JSON 등) 직접 반환 전제
5. 반환값 처리
    - 뷰 흐름: `String`(뷰이름) 또는 `ModelAndView` 또는 `return "redirect:/path"`
    - 바디 흐름: 객체/`ResponseEntity<?>`$\rightarrow$ @ResponseBody로 응답 본문에 쓰기
6. ViewResolver / HttpMessageConverter
    - 뷰 흐름: ViewResolver가 뷰이름 $\rightarrow$ 실제 View(JSP/Thymeleaf 등)로 매핑
    - 바디 흐름: ViewResolver 건너뜀. HttpMessageConverter가 객체 $\rightarrow$ JSON/XML 등으로 직렬화
7. 렌더링 & 후처리
    - 뷰 흐름: View.render() → 내부 forward(템플릿로 이동). `redirect:`이면 302 리다이렉트
    - 인터셉터 postHandle/afterCompletion, 예외는 HandlerExceptionResolver 처리
8. Response
    최종 바디/HTML이 클라이언트로 전송.
요약
- **@Controller** = “모델 + 뷰이름” $\rightarrow$ ViewResolver $\rightarrow$ 템플릿 렌더링
- **@RestController/@ResponseBody** = “객체” $\rightarrow$ MessageConverter $\rightarrow$ **JSON 응답**(뷰 단계 스킵)
**확장 포인트(필요 시)**: `HandlerInterceptor`, `ControllerAdvice/ExceptionHandler`, `Formatter/Converter`, `LocaleResolver`, `ContentNegotiation`.

#### Dispatcher Servlet이란?

Spring Web MVC에서 모든 요청을 받아 적절한 컨트롤러로 전달하고, 결과를 뷰나 JSON 응답으로 돌려주는 중앙 조정자(Front Controller).

즉, “요청과 응답의 흐름 전체를 총괄하는 핵심 서블릿”

즉,
- 클라이언트 요청을 받고
- 어떤 컨트롤러가 처리할지 결정하고
- 처리 결과를 적절한 형태로 응답하도록 **조율(dispatch)** 하는 역할을 함.

#### Servlet이란?

자바를 이용해 웹 요청(HTTP 요청)을 처리하고 응답을 생성하는 서버 측 프로그램

즉, 웹 서버와 자바 애플리케이션을 연결해주는 자바 클래스.

즉, 사용자가 브라우저에서 요청 $\rightarrow$ 서블릿이 실행 $\rightarrow$ 요청 처리 $\rightarrow$ HTML, JSON 같은 응답을 만들어 반환.



