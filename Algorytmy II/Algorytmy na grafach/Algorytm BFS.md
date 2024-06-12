#### Idea algorytmu
- Szuka najkrótszych ścieżek z wierzchołka $v$ do pozostałych wierzchołków w grafie **bez wag** $(V,E)$
Algorytm oparty jest na przeszukiwaniu grafu wszerz

#### Działanie algorytmu
- Wstaw na koniec kolejki wierzchołek $v$
- Dopóki kolejka nie jest pusta powtarzaj:
	- Weź z kolejki wierzchołek $w$ i dla każdego jego sąsiada $(q)$ wykonaj:
		- jeżeli $d[q] == ∞$: 
			- $d[q]=d[w]+1$
			- dodaj $q$ na koniec kolejki

Złożoność: $O(|E|)$