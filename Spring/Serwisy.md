Kluczowy element architektury aplikacji opartej na Springu.
Serwisy są używane do implementacji logiki biznesowej oddzielając ją od warstwy kontrolerów oraz warstwy repozytoriów.

- Adnotacja `@Service`
	- Serwisy są oznaczane adnotacją `@Service`. Dzięki temu Spring automatycznie wykrywa i rejestruje klasy serwisów jako komponenty w kontekście aplikacji
	- Przykład:
```java
import org.springframework.stereotype.Service;

@Service
public class UserService {
    // logika biznesowa
}
```
```