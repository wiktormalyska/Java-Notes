#### Idea Algorytmu
- Algorytm zachłanny (wybiera najlepszą opcję w danym momencie), podobny do [[Algorytm Dijkstry]]
- Budowę drzewa zaczynamy od dowolnego wierzchołka, w kolejnych krokach dodając jedną krawędź i jeden wierzchołek
- Za każdym razem dodajemy krawędź o minimalnej wadze spośród krawędzi łączących wierzchołki odwiedzone z nieodwiedzonymi
![[Pasted image 20240612205341.png]]
- Algorytm działa poprawnie dla dowolnych grafów
- Złożoność obliczeniowa zależy od przejętego sposobu wyszukiwania krawędzi dodawanej do drzewa i wynosi:
	- $O(|V|^2)$ - przeszukanie tablicy $d$
	- $O(|E|*\log |V|)$ - kolejka priorytetowa z wykorzystaniem kopca
	- $O(|E| + |V|*\log |V|)$ - kolejka priorytetowa z wykorzystaniem kopca Fibonacciego