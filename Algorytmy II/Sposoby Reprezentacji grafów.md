## Macierz sąsiedztwa
##### Graf $(V,R)$ przedstawiony zostaje jako dwuwymiarowa tablica A o wymiarach $V*V$ gdzie element $A[i][j]≠0$ gdy między wierzchołkami $Vi$ i $Vj$ istnieje krawędź

oznacza to że istnieje macierz 2 wymiarowa o wielkości grafu gdzie wypełnione komórki odpowiadają krawędzi pomiędzy dwoma wierzchołkami

 - Złożoność pamięciowa: $O(|V|^2)$
 - Czas wstawienia: $O(1)$
 - Czas usunięcia: $O(1)$
 - Czas zapytania: $O(1)$
 
![[Zrzut ekranu 2024-06-12 170855.png]]
![[Pasted image 20240612171542.png]]

są preferowanym sposobem reprezentacji grafów gdy zagęszczenie krawędzi jest bliska maksymalnej możliwej ich liczbie
## Lista sąsiedztwa (incydencji)
#### Graf $(V,R)$ przedstawiamy jako tablicę list taką że lista $tab[a]$ zawiera sąsiadów wierzchołka $a$

- Złożoność pamięciowa $O(|V|+|E|)$ - list jest tyle co wierzchołków, a elementów list tyle co krawędzi
- Czas wstawiania $O(1)$
- Czas usunięcia, zapytania - jak na liście uporządkowanej
![[Pasted image 20240612171521.png]]
![[Pasted image 20240612171531.png]]
## Lista krawędzi
## Macierz incydencji