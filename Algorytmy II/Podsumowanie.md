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
- Dijkstra
	- algorytm zachłanny
	- zawsze poprawny wynik
	- wyszukuje od pierwszego wierzchołka do wszystkich innych
- Ford-Bellman
	- dla grafu skierowanego z wagami
	- wolniejszy od [[Algorytm Dijkstry]]
	- 