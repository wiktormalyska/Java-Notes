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
- Jest podejściem, które integruje instrukcje imperatywne w kontekście obiektowym
- Kluczowe aspekty
	- **Encja jako Jednostka Przetwarzania:** Obiekty są podstawowymi jednostkami, które mogą zawierać stan i metody manipulujące tym stanem.
	- **Użycie Metod:** Zachowanie obiektów jest definiowane poprzez metody, które zawierają instrukcje imperatywne.
	- **Interakcje Obiektów:** Obiekty współpracują ze sobą poprzez wywoływanie metod, co prowadzi do wykonywania sekwencji instrukcji.
```cpp
#include <iostream>
#include <string>

class BankAccount {
private:
    std::string owner;
    double balance;

public:
    BankAccount(std::string owner, double balance) : owner(owner), balance(balance) {}

    void deposit(double amount) {
        balance += amount;
    }

    void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
        } else {
            std::cout << "Insufficient funds\n";
        }
    }

    void display() const {
        std::cout << "Owner: " << owner << ", Balance: " << balance << "\n";
    }
};

int main() {
    BankAccount account("Alice", 1000.0);
    account.display();
    account.deposit(200.0);
    account.display();
    account.withdraw(500.0);
    account.display();
    account.withdraw(1000.0);  // Should display an error message
    return 0;
}

```
##### Przykłady
- C++
- Java
- C#\
- Python

##### **Zalety i Wady**
- **Zalety:**
	- **Modularność:** Kod jest podzielony na obiekty, co ułatwia zarządzanie i modyfikację.
	- **Reużywalność:** Możliwość ponownego użycia kodu dzięki dziedziczeniu i polimorfizmowi.
	- **Klarowność:** Łatwiejsze zrozumienie interakcji w systemie przez modelowanie rzeczywistych encji jako obiektów.
- **Wady:**
	- **Złożoność:** Programowanie obiektowe może dodawać złożoność w porównaniu do podejścia proceduralnego, szczególnie dla prostych problemów.
	- **Wydajność:** Obiektowe podejście może mieć dodatkowy narzut czasowy i pamięciowy w porównaniu do bardziej bezpośredniego podejścia proceduralnego.