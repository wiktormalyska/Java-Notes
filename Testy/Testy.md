
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
- Wyjaśnienie: 
	- `@InjectMocks`: Tworzy instancję `UserService` i wstrzykuje do niej mocki.
	- `@Mock`: Tworzy mock `UserRepository`.
	- `MockitoAnnotations.openMocks(this)`: Inicjalizuje mocki przed każdym testem.
	- `when(...).thenReturn(...)`: Definiuje zachowanie mocka.
	- `assertThrows`: Sprawdza, czy rzucony został określony wyjątek.