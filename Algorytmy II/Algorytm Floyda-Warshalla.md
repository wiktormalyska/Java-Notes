Algorytm oblicza najkrótszą ścieżkę w grafie
potrafi obliczyć **najkrótsze odległości pomiędzy każdą parą wierzchołków w grafie**

#### Idea algorytmu
- wykorzystuje programowanie dynamiczne
- wyszukuje najkrótsze ścieżki pomiędzy dwoma dowolnymi wierzchołkami w grafie
- ścieżki są najkrótsze w obie strony
#### Działanie algorytmu
- Wejście: graf $(V,E)$, gdzie $wag(a,b)$ oznacza wagę krawędzi $(a,b)$
- tablica $M$, gdzie $M[a][b]=wag(a,b)$, jeżeli krawędź $(a,b)$ należy do grafu, w przeciwnym wypadku wartość jest równa $∞$
- Wyjście: tablica $M$, gdzie $M[a][b]$ jest najkrótszą odległością od wierzchołka $a$ do $b$
- Dla każdego wierzchołka $v$ należącego do grafu potarzaj:
	- dla każdej pary $(a,b)$ wykonaj:
		- jeżeli $(M[a][b]>M[a][v]+M[v][b])$ to $M[a][b]=M[a][v]+M[v][b]$
- 