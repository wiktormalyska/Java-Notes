#### Idea algorytmu
- Algorytm oparty o metodę zachłanną i polega na łączeniu wielu poddrzew w jedno za pomocą krawędzi o najmniejszej wadze
- algorytm buduje wiele drzew jednocześnie - na początku każdy wierzchołek wejściowego grafu jest oddzielnym drzewem
- następnie korzystamy z faktu, że jeżeli połączymy ze sobą dwa dowolne wierzchołki różnych drzew to otrzymamy jedno duże drzewo

#### Działanie algorytmu
- Wejście : graf $(V,E)$
- Wyjście: $D$ - zbiór drzew, na wyjściu zawierający drzewo rozpinające $G$
- zainicjuj zbiór $D=V$, zbiór