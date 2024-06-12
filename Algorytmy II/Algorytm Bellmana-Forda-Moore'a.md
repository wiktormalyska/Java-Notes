Algorytm obliczający najkrótsze ścieżki z danego wierzchołka do wszystkich pozostałych wierzchołków w **skierowanym grafie z wagami**

Jest wolniejszy od algorytmu Dijkstry dla tego samego problemu, lecz jest bardziej uniwersalny, ponieważ obsługuje grafy, które zawierają krawędzie o ujemnej wadze, ale nie zawierają ujemnych cykli

#### Idea algorytmu
- Wykorzystuje programowanie dynamiczne
- Wyszukuje najkrótsze ścieżki z wybranego wierzchołka do wszystkich wierzchołków w grafie
#### Działanie algorytmu
- Wejście: graf $(V,E)$, gdzie $wag(a,b)$ to waga krawędzi $(a,b)$
- Wyjście: tablica $d$ zawierająca odległości ze źródła $z$ do poszczególnych wierzchołków
- zainicjuj wszystkie elementy tablic oprócz elementu źródła jako $∞$
- for $i=1$ to $|V|-1$ do:
	- dla każdej krawędzi $(a,b)$ powtarzaj:
		- jeżeli $(d[b]>d[a]+wag(a,b))$, to $d[b]=d[a]+wag(a,b)$ oraz opcjonalnie $p[b]=a$
- dla każdej krawędzi $(a,b)$ powtarzaj:
	- jeżeli $(d[b]>d[a]+wag(a,b))$, to zwróć $false$(wystąpił cykl o ujemnej wadze)

Algorytm działa poprawnie dla dowolnych grafów **bez cykli ujemnych(o ujemnej sumie wag krawędzi)**
w przypadku grafów skierowanych wymóg oznacza ż