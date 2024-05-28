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
	- Spring może automatycznie wykrywać i rejestrować beany za pomocą adnotacji takich jak `@Component`, `@Service`, `@Repository`, `@Controller`
	- W kodzie `@ComponentScan` mówi Springowi, aby przeszukał pakiet `com.example` w poszukiwaniu klas oznaczonych adnotacjami komponentów
	- Przykład:
```java
@Component
public class MyBean {
    // ...
}

@Configuration
@ComponentScan(basePackages = "com.example")
public class AppConfig {
    // ...
}

```
- Profile
	- Spring Profiles pozwalają na definiowanie różnych konfiguracji dla różnych środowisk (np. dev,text,prod)
	- Profile mogą być aktywowane programowo lub za pomocą zmiennych środowiskowych
	- Przykład:
```java
@Configuration
@Profile("dev")
public class DevConfig {

    @Bean
    public MyBean myBean() {
        return new MyBean("Development");
    }
}

@Configuration
@Profile("prod")
public class ProdConfig {

    @Bean
    public MyBean myBean() {
        return new MyBean("Production");
    }
}
```
- Konfiguracja za pomocą plików properties i YAML
	- [[Spring Properties]]
- @Value i @ConfigurationProperties
	- Adnotacja `@Value` pozwala na wstrzykiwanie wartości z plików konfiguracyjnych bezp