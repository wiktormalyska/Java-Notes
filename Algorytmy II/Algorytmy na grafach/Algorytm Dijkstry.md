#### Idea algorytmu
- Przyjmij startowy wierzchołek o numerze $v$
- Tablica pomocnicza $d$, po zakończeniu działania algorytmu będzie zawierała odległości poszczególnych wierzchołków od źródła
- $wag(a,b)$ jest wagą krawędzi $(a,b)$
#### Działanie algorytmu
- Dopóki istnieje nieodwiedzony wierzchołek powtarzaj:
	- wybierz nieodwiedzony wierzchołek $w$ o najmniejszej wartości $d[w]$
	- odwiedź $w$
- dla każdego $q$ sąsiada $w$ wykonaj:
	- jeżeli $d[q]>d[w]+wag(w,d)$ przypisz $d[q]=d[w]+wag(w,q)$


![[Pasted image 20240612172935.png]]
![[Pasted image 20240612173017.png]]

Złożoność: $O(|V|^2), O(|E|\log |V|)$