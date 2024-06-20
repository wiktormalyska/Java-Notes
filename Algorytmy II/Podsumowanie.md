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
	- każdemu elementowi 