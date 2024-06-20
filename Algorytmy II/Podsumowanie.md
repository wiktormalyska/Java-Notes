#### Sposoby reprezentacji grafów
- ##### Macierz sąsiedztwa
	- 2 wymiarowa tablica gdzie zapisywane są łączenia
	- Preferowane kiedy duże zagęszczenie
	- Duża złożoność pamięciowa
	- ![[Zrzut ekranu 2024-06-12 170855.png]]
- ##### Lista sąsiedztwa
	- Lista posiadająca wierzchołki sąsiadujące
	- Preferowane kiedy małe zagęszczenie
	- ![[Pasted image 20240612171521.png]]
- ##### Lista krawędzi (nie omówione)
- ##### Macierz incydencji (nie omówione)

#### Problem szukania najkrótszej ścieżki
- ##### Dijkstra
	- algorytm zachłanny
	- zawsze poprawny wynik
	- wyszukuje od pierwszego wierzchołka do wszystkich innych
	- Złożoność
		- $O(|E|\log |V|)$ - oczekiwana
		- $O(|V|^2)$ - pesymistyczna
- ##### Ford-Bellman
	- dla grafu skierowanego z wagami
	- wolniejszy od [[Algorytm Dijkstry]]
	- bardziej uniwersalny
	- Złożoność
		- $O(|V|*|E|)$
- ##### Relaksacja krawędzi
	- Próba poprawienia obecnie znanej najkrótszej odległości do danego wierzchołka poprzez przejście przez inną krawędź
	- współpracuje z wagami

#### Minimalne drzewo rozpinające
- ##### [[Algorytm Kruskala]]
	- Złożoność taka jak [[Algorytm Dijkstry]]
- ##### [[Algorytm Prima]]
	- Złożoność taka jak [[Algorytm Dijkstry]]
- Dla jednego drzewa może istnieć wiele drzew rozpinających

#### [[Słownik]]
- Abstrakcyjna struktura danych
- Elementy są złożone z (key, value)
- Operacje:
	- Search
	- Insert
	- Delete
- Sposoby implementacji słowników
	- Lista (naiwny sposób)
		- nieuporządkowane
		- uporządkowane
	- Drzewa
		- [[Drzewo BST]]
		- [[Drzewo AVL]]
		- [[B drzewa]]
	- Tablice haszujące

#### [[Haszowanie]]
- Proces przekształcania danych wejściowych dowolnej długości w dane wyjściowe o stałej długości, zwane **kodem haszującym**
- Proces jest realizowany przez funkcję haszującą
- ##### Rozwiązywanie konfliktów
	- ###### Haszowanie otwarte (metoda łańcuchowa)
		- po kolizji szuka kolejnego wolnego miejsca w tablicy według określonego schematu
		- Liniowe próbkowanie - przesuwa o jedno miejsce aż do znalezienia
		- Kwadratowe próbkowanie - przesuwa według rosnącego kwadratu liczb
		- Podwójne haszowanie - użycie drugiej funkcji haszującej do określenia kroku przesunięcia
	- ###### Haszowanie zamknięte (adresowanie otwarte)
		-  podczas kolizji robi rehash, czyli szuka kolejne miejsce, gdzie potencjalnie można umieścić zapisywany rekord
		- ponawia próbę aż znajdzie miejsce
- ##### Funkcja haszująca
	- powinna mieć stały czas wykonania $O(1)$
	- każdemu elementowi ze zbioru dopuszczalnych kluczy daje liczbę całkowitą
	- powinna być
		- łatwa w implementacji
		- łatwo obliczalna co do złożoności
		- losowa

#### [[Wyszukiwanie wzorca w tekście]]
- [[Algorytm Morrisa-Prata]]
	- Liniowy czas przetwarzania
	- Efektywna metoda wyszukiwania wzorców
	- Przodek [[Algorytm Knutha-Morrisa-Pratta]]
	- Buduje tablicę prefiksów dla wzorca
	- Używa tablicy aby przeskakiwać w tekście
	- Unika niepotrzebnych porównań
- ##### [[Algorytm Knutha-Morrisa-Pratta]]
	- Wypełnianie tablicy prefiksów jest bardziej zaawansowane niż w [[Algorytm Morrisa-Prata]]
	- Tworzy tablicę prefiksów, która przechowuje info o najdłuższych prefiksach wzorca
	- Porównuje wzorzec z tekstem używając tablicy aby przesuwać w przypadku niezgodności
	- Unika niepotrzebnych porównań
- ##### [[Algorytm Karpa-Rabina]]
	- Wykorzystuje technikę [[Haszowanie]]
	- Haszuje wzorzec i stopniowo przechodzi po tekście
	- W przypadku kolizji porównuje wnętrze
	- Po znalezieniu tego samego hasza, sprawdza wnętrze
	- Najbardziej wydajny

#### Algorytmy Geometryczne
[[Geometria Obliczeniowa]]
- Analiza położenia odcinków, prostych i wielokątów
- [[Algorytm Grahama]] 
	- Szukanie wypukłej otoczki z punktów
	- $O(n\log n)$
- Metoda zamiatania
	- większość odcinków nie ma przecięć lub jest ich niewielka liczba
	- czas działania powinien zależeć od przecięć i liczby odcinków

#### [[Algorytmy probabilistyczne]]
- Monte Carlo
	- Ograniczony czas działania
	- Poprawne wyniki z dużym prawdopowobieństwem
	- Losuje wyniki z zakresu określoną ilość razy i bierze ich średnią
- Las Vegas
	- Zawsze poprawny wynik
	- Losowa liczba przeszukań
- Benefity z randomizacji
	- Redukujemy ilość przeglądanych rozwiązań na rzecz poprawności wyniku
	- Proste w implementacji
	- Niedeterministyczne
	- Mniejsza złożoność obliczeniowa

#### [[Kolorowanie grafów]]
- Przypisujemy każdemu wierzchołkowi kolor w taki sposób że sąsiadujące wierzchołki nie mają tego samego koloru
- k-chromatyczny jeżeli graf można pokolorować 3 kolorami
- liczba chromatyczna to minimalna ilość kolorów