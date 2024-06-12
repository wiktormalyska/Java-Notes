#### Idea algorytmu
- Algorytm oparty o metodę zachłanną i polega na łączeniu wielu poddrzew w jedno za pomocą krawędzi o najmniejszej wadze
- algorytm buduje wiele drzew jednocześnie - na początku każdy wierzchołek wejściowego grafu jest oddzielnym drzewem
- następnie korzystamy z faktu, że jeżeli połączymy ze sobą dwa dowolne wierzchołki różnych drzew to otrzymamy jedno duże drzewo

#### Działanie algorytmu
- Wejście : graf $(V,E)$
- Wyjście: $D$ - zbiór drzew, na wyjściu zawierający drzewo rozpinające $G$
- zainicjuj zbiór $D=V$, zbiór wierzchołków grafu interpretowany jako zbiór drzew o jednym wierzchołku
- Dopóki $D$ zawiera więcej niż 1 element powtarzaj:
	- Ze zbioru $D$ wybierz krawędź o minimalnej wadze łączącej dwa drzewa $(d1$ i $d2)$
	- W zbiorze $D$ zastąp drzewa $d1$ i $d2$ przez jedno drzewo połączone krawędzią $e$

![[Pasted image 20240612210122.png]]

Algorytm składa się z dwóch głównych części:
- sortowanie krawędzi - które bez dodatkowych założeń ma złożoność $O(|E|\log |E|)$
- przeglądania krawędzi i scalania drzew - złożoność zależna od implementacji zbiorów rozłącznych. Możliwe do uzyskania jest $O(|E|+|V|\log |V|)$, a z zastosowaniem lasu zbiorów rozłącznych $O(|E|\alpha (|V|))$ gdzie $\alpha$ jest funkcją odwrotną do funkcji Ackermanna