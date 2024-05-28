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
- Iniekcja przez Konstruktor:
	- polega na przekazywaniu zależności do obiektu poprzez jego konstruktor. Jest to preferowane podejście, ponieważ pozwala na oznaczenie zależności jako już wymagane od momentu tworzenia obiektu
	- Przykład:
```java
@Component
public class MyService {
    private final MyRepository myRepository;

    @Autowired
    public MyService(MyRepository myRepository) {
        this.myRepository = myRepository;
    }
}
```
- Iniekcja przez Setter
	- umożliwia przekazywanie zależności do obiektu za pomocą metod setter
	- to podejście jest używane, gdy zależność może być opcjonalna lub gdy konieczne jest ustawienie zależności po utworzeniu obiektu
	- Przykład:
```java
@Component
public class MyService {
    private MyRepository myRepository;

    @Autowired
    public void setMyRepository(MyRepository myRepository) {
        this.myRepository = myRepository;
    }
}
```
- Iniekcja przez Pole
	- jest to najprostszy sposób iniekcji zależności, gdzie `@Autowired` jest używana bezpośrednio na polu
	- Mimo tego że jest to wygodne, to nie je