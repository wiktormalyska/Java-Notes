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