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
@Configuration
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
- Definiowanie użytkowników
```java
@Configuration
public class SecurityConfiguration {
    
    @Bean
    public InMemoryUserDetailsManager userDetailsService() {
        UserDetails user = User.withDefaultPasswordEncoder()
            .username("user")
            .password("password")
            .roles("USER")
            .build();
        return new InMemoryUserDetailsManager(user);
    }

    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }
}
```
- Definiowanie ról
```java
@Configuration
public class SecurityConfiguration {
    
    @Bean
    public InMemoryUserDetailsManager userDetailsService() {
        UserDetails user = User.withDefaultPasswordEncoder()
            .withUser("user")
            .password("password")
            .roles("USER")
            .and()
            .withUser("admin")
            .password("admin")
            .roles("ADMIN")
            .build();
        return new InMemoryUserDetailsManager(user);
    }

    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder();
    }
}
```
- Konfiguracja wraz z bazą danych
```java
@Configuration
public class SecurityConfiguration {
    @Bean
    public DataSource dataSource() {
        return new EmbeddedDatabaseBuilder()
            .setType(EmbeddedDatabaseType.H2) //Typ bazy
            .addScript(JdbcDaoImpl.DEFAULT_USER_SCHEMA_DDL_LOCATION)
            .build();
    }

    @Bean
    public UserDetailsManager users(DataSource dataSource) {
        UserDetails user = User.withDefaultPasswordEncoder()
            .username("user")
            .password("password")
            .roles("USER")
            .build();
        JdbcUserDetailsManager users = new JdbcUserDetailsManager(dataSource);
        users.createUser(user);
        return users;
    }
}
```
- Zaawansowane funkcje
	- CSRF Protection
		- Domyślnie włączona ochrona przed atakami CSRF
	- Remember-me
		- Umożliwia zapamiętanie sesji użytkownika pomiędzy zamknięciami przeglądarki
	- OAuth2
		- Spring Security wspiera OAuth2 i OpenID Connect, co pozwala na integrację z dostawcami takich jak Google, Facebook, itp.
	- Metody Haszujące
		- Obsługa różnych metod haszowania haseł, takich jak BCrypt, SCrypt
### Integracja z Aplikacjami Webowymi
- Spring Security umożliwia zintegrowanie z aplikacjami opartymi na Spring MVC, WebFlux etc.
- Przykład prostej a