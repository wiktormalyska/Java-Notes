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
- 