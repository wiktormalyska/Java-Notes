- Jest to rozbudowane narzędzie do zabezpieczenia aplikacji opartych na Springu
- Umożliwia implementację różnorodnych mechanizmów uwierzytelniania i autoryzacji zapewniając ochronę przez atakami

### Podstawowe Koncepcje
- Uwierzytelnianie (Authentication): 
	- Proces weryfikacji tożsamości użytkownika, np. za pomocą loginu i hasła
- Autoryzacja (Authorization):
	- Proces przyznawania uprawnień użytkownikowi do wykonywania określonych operacji

### Komponenty Spring Security
- Security Context
	- Przechowuje informację o uwierzytelnionym użytkowniku
- Authentication
	- Interfejs reprezentujący informację o uwierzytelnieniu użytkownika (username i password)
- Granted Authority
	- Reprezentuje uprawnienia lub role przypisane użytkownikowi
- User Details
	- Dane użytkownika potrzebne do uwierzytelnienia
- User Details Service
	- Interfejs do ładowania danych użytkownika na podstawie nazwy użytkownika

### Integracja aplikacji z Spring Security
- Dodanie zależności do projektu
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>
```
#### Konfiguracja Bezpieczeństwa
- Konfiguracja oparta na adnotacjach w klasie
	- Dodanie adnotacji `@EnableWebSecurity` do klasy konfiguracyjnej
```java
@Configuration 
@EnableWebSecurity 
public class SecurityConfig{
	@Bean  
	public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {  
	    http  
	        .csrf(AbstractHttpConfigurer::disable)  
            .authorizeHttpRequests(authorizeRequests ->  
            authorizeRequests  
                    .anyRequest().permitAll()  
	    );  
	    return http.build();  
	}
}
```
- Konfiguracja oparta na klasie
```java
@EnableWebSecurity
public class SecurityConfig {

    @Bean
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
        http
            .authorizeRequests(authorizeRequests ->
                authorizeRequests
                    .antMatchers("/", "/home").permitAll()
                    .anyRequest().authenticated()
            )
            .formLogin(formLogin ->
                formLogin
                    .loginPage("/login")
                    .permitAll()
            )
            .logout(logout ->
                logout
                    .permitAll()
            );
        return http.build();
    }
}
```
- Definiowanie użytkowników i ról
```java
public class InMemorySecurityConfig {
    
    
    public void configure(AuthenticationManagerBuilder auth) throws Exception {
        auth.inMemoryAuthentication()
            .withUser("user")
            .password("password")
            .roles("USER")
            .and()
            .withUser("admin")
            .password("admin")
            .roles("ADMIN");
    }

    @Bean
    public static NoOpPasswordEncoder passwordEncoder() {
        return (NoOpPasswordEncoder) NoOpPasswordEncoder.getInstance();
    }
}
```