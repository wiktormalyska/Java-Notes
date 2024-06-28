#### Program w języku imperatywnym
- ściśle powiązany z koncepcją maszyny von Neumanna (z pamięcią jednolitą) 
- polega na wydawaniu sekwencji uszeregowanych czasowo (z ustaloną kolejnością) rozkazów zmieniających stan maszyny
- stan maszyny oznacza stan jej procesora i zawartość pamięci oraz rejestrów
- języki niskiego poziomu (asemblery) operują niemal bezpośrednio na jednostkach pamięci
- języki wysokiego poziomu wprowadzają twory abstrakcyjne reprezentujące składowe maszyny, np. zmienne reprezentują jednostki pamięci
```pascal
program silnia;
var i, n, s: integer;
begin
	read(n);
	s := 1;
	for i := 2 to n do
		s := s*i;
	write(s)
end.
```
```fortran
		program silnia
		integer i, n, s
		read (*,*) n
		s = 1
		do 10 i=2, n
			s = s * i
10	continue
		write(*,*) s
		end program
```


#### Paradygmat Obiektowy
- Jest to rodzina imperatywna, więc struktura i logika kodu jest taka sama
- zmiana następuje na poziomie struktury danych
	- dane grupowane są z operacjami, które można na nich wykonać, w nowy twór (obiekt)
- **hermetyzacja (enkapsulacja)** polega na ukryciu implementacji obiektu, zaś udostępnieniu jedynie niektórych danych i metod w postaci **interfejsu**
- obiekty można grupować w hierarchicznie definiowane klasy, które mają pewne wspólne cechy (mechanizm dziedziczenia w ramach hierarchii)
- hierarchia klas implikuje zawieranie się , co prowadzi do **polimorfizmu dynamicznego**
	- metody dobierane są automatycznie, zgodnie z przynależnością do klasy
- **abstrakcja danych** pozwala na definiowanie klas w postaci ogólnych szablonów, a na ich podstawie dopiero tworzenia szczegółowych definicji

##### Główne pojęcia paradygmatu obiektowego
- Klasa - abstrakcyjny typ danych, definiowany programowo poprzez podanie dopuszczalnych na nim operacji oraz jego reprezentację
- Obiekt - element należący do pewnej klasy
- Klasa potomna - klasa wywiedziona poprzez dziedziczenie z innej klasy
- Klasa macierzysta - klasa, z której wywodzi się klasa potomna
- Metoda - podprogram (operacja) działający na obiektach danej klasy zgodnie z jej i jego definicją
- Pole - zmienna zamknięta wewnątrz obiektu
- Komunikat - wywołanie metody
- Protokół obiektu - zbiór sposobów odwołania się do obiektu

#### Specyfikatory dostępu
- public - nieograniczona dostępność z zewnątrz klasy
- private - ukrycie przed dostępem z zewnątrz i pozwala przez to na definiowanie typów abstrakcyjnych
- protected - ukrycie dla wszystkich za wyjątkiem klas potomnych
```C++
unsingned int factorial (unsigned int x) {
	unsigned int value = 1;
	for (unsigned int i=2; i<=x; i++)
		value *= i;

	return value;
}
```
```ruby
class Song
	def initialize(name, artist, duration)
		@name = name
		@artist = artist
		@duration = duration
	end
end

aSong = Song.new("Bicylops", "Fleck", 260)
aSobg.inspect
```
#####  Języki obiektowe: C++, C#, Delphi/Object Pascal, Java, Ada, Python, Ruby

###### Ruby
- jest językiem niezwykle elastycznym, do tego stopnia, że struktura klas nie jest sztywna, mówi się że ruby posiada **otwarte klasy**
	- definicje klas i metod są dostępne dla programisty
	- można je dowolnie modyfikować
- Z powodu dziedziczenia zmiany w klasie nadrzędnej będą propagowały do klas potomnych co może prowadzić do trudnych do wykrycia błędów
```ruby
class Fixnum
	alias old_plus +
	
	def +(wyrażenie)
		(self.old_plus wyrażenie) % 7
	end
end
a = 4 + 4
puts a    #1
```

#### Programowanie deklaratywne
##### Definicja funkcji silnia w Haskellu
```haskell
silnia :: Integer -> Integer
silnia o = 1
silnia x = x * silnia (x-1)
```
#### Definicja predykatu silnia w Prologu
```prolog
silnia(0,X) :- X=1, !.
silnia(N,X) :- N>0, L is N-1,
								silnia(L,Y), X is Y*N
```
