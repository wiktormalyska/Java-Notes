- Łączy Paradygmat Imperatywny z Obiektowym
- Definiuje jak osiągnąć wynik, podając dokładne kroki do wykonania

#### Programowanie Imperatywne
- Charakteryzuje się
	- **Sekwencje Instrukcji:** Programy są zorganizowane jako sekwencje instrukcji wykonujących działania, zmieniających stan programu
	- **Zmienne:** Stan programu jest przechowywany w zmiennych
	- **Struktury Kontrolne:** Używanie pętli, instrukcji warunkowych, itp.
	- **Procedury i Funkcje:** Kod jest często organizowany w procedury lub funkcje, które mogą być wywoływane wielokrotnie
```cpp
#include <stdio.h>

int main() {
    int x = 10;
    int y = 20;
    int result = x + y;
    printf("Result: %d\n", result);
    return 0;
}
```
#### Programowanie Obiektywne
- Charakteryzuje się
	- **Obiekty i Klasy:** Obiekty są instancjami klas, które definiują strukturę danych i zachowanie
	- **Hermetyzacja:** Ukrywanie stanu wewnętrznego obiektu i udostępnianie go tylko poprzez metody
	- **Dziedziczenie:** Klasy mogą dziedziczyć cechy innych klas
	- **Polimorfizm:** Możliwość używania różnych typów obiektów zamiennie
```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        raise NotImplementedError("Subclass must implement abstract method")

class Dog(Animal):
    def speak(self):
        return f"{self.name} says Woof!"

class Cat(Animal):
    def speak(self):
        return f"{self.name} says Meow!"

dog = Dog("Rex")
cat = Cat("Whiskers")
print(dog.speak())  # Rex says Woof!
print(cat.speak())  # Whiskers says Meow!
```

#### Programowanie Imperatywne Obiektowe
- Jest podejściem, które integruje instru