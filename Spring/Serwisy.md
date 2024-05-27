Kluczowy element architektury aplikacji opartej na Springu.
Serwisy są używane do implementacji logiki biznesowej oddzielając ją od warstwy kontrolerów oraz warstwy repozytoriów.

- Adnotacja `@Service`:
	- Serwisy są oznaczane adnotacją `@Service`. Dzięki temu Spring automatycznie wykrywa i rejestruje klasy serwisów jako komponenty w kontekście aplikacji
	- Przykład:
```java
import org.springframework.stereotype.Service;

@Service
public class UserService {
    // logika biznesowa
}
```

- Iniekcja zależności (Dependency Injection):
	- Serwisy mogą być automatycznie wstrzykiwane do innych komponentów, takich jak kontrolery czy inne serwisy, poprzez adnotację `@Autowired`.
	- Przykład:
```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;

@Controller
public class UserController {

    @Autowired
    private UserService userService;

    // logika kontrolera
}

```

- Separacja problemów (Separation of Concerns)
	- Serwisy pomagają w rozdzieleniu odpowiedzialności w aplikacji, co sprzyja organizacji kodu i łatwiejszemu testowaniu. Logika biznesowa jest oddzielona od logiki prezentacji i logiki dostępu do danych.

- Transakcje
	- Serwisy zarządzają transakcjami w aplikacjach korzystających z baz danych. Można użyć adnotacji `@Transactional` na poziomie klasy lub metody, aby zapewnić, że operacje są wykonywane w sposób atomowy.
	- Istnieją różne atrybuty adnotacji, takie jak: 
		- **propagation**: zarządzanie transakcją, gdy metoda jest wywoływana w ramach istniejącej już transakcji
		- **isolation**: widoczność zmian dokonanych w ramach transakcji dla innych transakcji.
		- **timeout**: maksymalny czas w sekundach przez jaki transakcja moze trwać przed zakończeniem
		- **readOnly**: wskazuje, że transakcja jest tylko do odczytu
		- **norollback/rollbackFor**: nie/wycofuje transakcje w przypadku wystąpienia określonego wyjątku
	- Przykład:
```java
import org.springframework.transaction.annotation.Transactional;

@Service
public class UserService {

    @Transactional
    public void registerUser(User user) {
        // logika rejestracji użytkownika
    }
}
```

- Zarządzanie wyjątkami:
	- W serwisach często obsługujemy wyjątki biznesowe. Dobrą praktyką jest tworzenie specyficznych wyjątków.
	- Przykład:
		```java
		public class UserNotFoundException extends RuntimeException {
		    public UserNotFoundException(String message) {
		        super(message);
		    }
		}

		@Service
		public class UserService {
		    public User findUserById(Long id) {
		        return userRepository.findById(id)
		            .orElseThrow(() -> new UserNotFoundException("User not found with id: " + id));
		    }
		}

```

- Testowanie
	- Serwisy mogą być łatwo testowane za pomocą testów jednostkowych i integracyjnych.
	- Dzięki oddzieleniu logiki biznesowej od innych warstw, serwisy można testować niezależnie.
	- Testy Jednostkowe (Unit tests):
		- Narzędzia:
			- [JUnit](https://junit.org/junit5/)
			- [Mockito](https://site.mockito.org/)
		- Przykład:
```java
@Service
public class UserService {

    @Autowired
    private UserRepository userRepository;

    public User findUserById(Long id) {
        return userRepository.findById(id)
                .orElseThrow(() -> new UserNotFoundException("User not found with id: " + id));
    }
}
```

```java
import static org.junit.jupiter.api.Assertions.*;
import static org.mockito.Mockito.*;

import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;
import org.mockito.InjectMocks;
import org.mockito.Mock;
import org.mockito.MockitoAnnotations;

import java.util.Optional;

public class UserServiceTest {

    @InjectMocks
    private UserService userService;

    @Mock
    private UserRepository userRepository;

    @BeforeEach
    public void setUp() {
        MockitoAnnotations.openMocks(this);
    }

    @Test
    public void testFindUserById_UserExists() {
        User user = new User();
        user.setId(1L);

        when(userRepository.findById(1L)).thenReturn(Optional.of(user));

        User result = userService.findUserById(1L);

        assertEquals(user, result);
        verify(userRepository, times(1)).findById(1L);
    }

    @Test
    public void testFindUserById_UserNotFound() {
        when(userRepository.findById(1L)).thenReturn(Optional.empty());

        Exception exception = assertThrows(UserNotFoundException.class, () -> {
            userService.findUserById(1L);
        });

        assertEquals("User not found with id: 1", exception.getMessage());
        verify(userRepository, times(1)).findById(1L);
    }
}

```
