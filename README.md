# 천천히 작성할 예정 🛠
[스프링 시큐리티 가이드](https://spring.io/guides/topicals/spring-security-architecture/)
# SpringBoot-Security

해당 가이드는 `Spring Security`의 `설계` 및 `기본 구성요소`에 대한 **통찰력을 제공하는 입문서**이다.    
                  
이를 위해, 우리는 애플리케이션 보안의 기본만 다루고자 한다.              
`Filter`를 사용하고 `Annotation`을 사용하여 웹 애플리케이션에서 보안이 적용되는 방식을 살펴 볼 예정이다.         
이를 통해 `Spring Security`를 사용하는 개발자들이 겪어본 혼란들을 해결할 수 있을 것이라 기대한다.           
  
만약 당신이     
보안 응용 프로그램의 작동 방식, 사용자 지정 방법에 대한 높은 수준의 이해가 필요하거나       
응용 프로그램 보안에 대해 생각하는 방법을 배워야하는 경우에는 이 가이드를 참고하면 좋을 것이다.    
       
이 가이드는 어려운 문제를 해결하기 위한 매뉴얼이나 레시피가 아니지만 초보자와 전문가 모두에게 유용 할 것이다.           
특히, `Spring Boot`는 보안 애플리케이션에 대한 기본 동작을 제공하기 때문에               
종종 참조되며 전체 아키텍처에 어떻게 부합하는지 이해하는 데 유용 할 수 있다.              
물론, `Spring Boot`를 사용하지 않는 애플리케이션에도 유용하게 적용되리라 기대한다.       

# 인증과 인가
애플리케이션 보안은 `인증`과 `인가`라는 두 가지 독립적인 문제로 귀결된다.    
`Spring Security`는 `인증`과 `인가`를 분리하도록 설계된 아키텍처를 가지고 있으며  
`인증`과 `인가`에 대한 전략과 확장 포인트를 가지고 있다.    
  
## 인증(Authentication)   
`인증`을 위한 주요 전략으로 `AuthenticationManager` 인터페이스를 사용하며이며 메서드는 한 개이다.   

```java
public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}
```
