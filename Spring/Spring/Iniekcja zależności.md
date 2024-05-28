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
- Iniekcja przez Konstr