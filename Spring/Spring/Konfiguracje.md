- Konfiguracja odnosi się do sposobów definiowania i zarządzania komponentami, zależnościami i ustawieniami aplikacji
- Konfiguracja XML
	- W starszych wersjach Springa dominowała
	- Używana do definiowania beanów i zależności
	- Zawierają definicje komponentów i sposoby ich wstrzykiwania
	- Przykład:
```xml
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
           http://www.springframework.org/schema/beans/spring-beans.xsd">

    <bean id="myBean" class="com.example.MyBean">
        <property name="propertyName" value="propertyValue"/>
    </bean>

</beans>
```
- Konfiguracja za pomocą adnotacji (Java-based Configuration)
	- Spring umożliwia definiowanie konfiguracji za pomocą adnotacji w kodzie Java
	- W tym podejściu, klasa `App Config` jest oznaczona adnotacją `@Configuration`, a metody zwracające beany są oznaczone adnotacją `@Bean`
	- Przykład:
```java
@Configuration
public class AppConfig {

    @Bean
    public MyBean myBean() {
        return new MyBean();
    }

}

```
- Konfiguracja za pomocą adnotacji komponentów (Component Scanning)
	- Spring może automatycznie wykrywać i rejestrować beany za pomocą adnotacji takich jak `@Component`