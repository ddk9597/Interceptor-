# Interceptor에 대한 정리

## Interceptor 의 개념
### 뜻
 요청 또는 응답을 가로채는 Spring에서 지원하는 객체
 
### 작동 방식
>클래스를 생성 후 HandlerInterceptor implements.
  
>-> HandlerInterceptor를 상속받은 클래스는 인터셉터로 간주됨.
  
>MVC2 에서 
>Client <-> filter <-> dispatcherServlet <-> Interceptor <-> Controller <-> service -> ... 단계 중

>전처리, 후처리, aftrerCompletion 3가지로 작동함
  
#### 전처리(preHandle) 
> 컨트롤러가 실행되기 전에 호출되는 메서드
> Controller가 역할을 수행하기 전에 dispatcherServlet -> Controller 사이에서 수행
> true/false 반환하며, true 반환 시 요청 계속 진행됨


#### 후처리(postHandle)
>컨트롤러가 실행 된 후에(전처리에서 true반환 시) 호출되는 메서드
>컨트롤러 실행 결과와 함께 작업을 수행 가능하다.
>dispatcherServlet이 역할을 수행하기 전에 Controller -> dispatcherServlet 사이에서 수행함.

#### afterCompletion
>요청 처리가 완료된 후 호출되는 메서드.
>예외가 발생하더라도 항상 호출된다.
>뷰 완성(forwardCode 해석) 후 viewResolver -> dispatcherServlet 사이에서 수행함

### 사용처
>boardProject
>


## Interceptor
