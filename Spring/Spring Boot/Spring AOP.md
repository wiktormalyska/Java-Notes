
- Spring AOP (Aspect-Oriented Programming):
	- Serwisy mogą korzystać z aspektów w celu dodatkowej logiki, takiej jak logowanie, auth i zarządzanie transakcjami bez zmieniania kodu biznesowego
	- Przykład:
```java
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Before;
import org.springframework.stereotype.Component;

@Aspect
@Component
public class LoggingAspect {

    @Before("execution(* com.example.service.UserService.*(..))")
    public void logBefore() {
        System.out.println("Metoda serwisu została wywołana");
    }
}

```