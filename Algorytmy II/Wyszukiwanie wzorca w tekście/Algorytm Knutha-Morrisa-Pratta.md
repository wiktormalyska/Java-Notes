Algorytm KNP jest podobny do algorytmu MP, różni się sposobem wypełnienia tablicy $P$ (oznaczymy jako $P`$)

Tablicę $P`$ definiujemy jako
- dla $i<|wzorzec|$ : $P`[i]$ to długość najdłuższego prefikso-sufiksu słowa wzorzec jakiego że $wzorzec[p`[i]+1]!=wzorzec[i+1]$
- jeżeli dla danego i takiego prefikso-sufiksu nie ma to $P`[i]=-1$
- dla $i=|wzorzec|$ to $P`[i]=P[i]$

Aby uniknąć po przesunięciu wzorca natychmiastowej niezgodności musimy dodatkowo zażądać, aby znak leżący tuż za prefikso-sufiksem prefiksu we wzorcu był różny od znaku za wzorcem

- Złożoność obu algorytmów jest taka sama
- Dokładana liczba porównań symboli we właściwe części KMP nie może być mniejsza niż w algorytmie MP
- algorytm MP jest prostszy ze względu na łatwiejsze wypełnianie tablicy $P$

- jeżeli drogą operacyjną jest dla nas sprawdzenie równoważności napisów - uniwersum możliwych napisów długości $s$ jest duże
- to może możemy porównać funkcje haszujące dla tych stringów - rzutując je na obszar rozsądnego rozmiaru
- potrzebujemy pewnej struktury wspomagającej te operacje aby uniknąć przesuwanie się po jednym znaku i obliczania za każdym razem funkcji haszującej (chcemy to robić w czasie stałym)

### Rolling hash - haszowanie rekurencyjne
- abstrakcyjna struktura danych $r$ przechowująca napis udostępnia operacje
	- r.append(c) - dołącz c do końca napisu
	- r.skip(d) - usuń pierwszy znak z napisu d
	- r() - zwróć wartość funkcji haszującej $h(x)$ dla aktualnego napisu
	- kluczowy jest szybki sposób obliczenia wartości $h(x)$ wykorzystując starą wartość funkcji, oraz usunięty i dodany znak do $x$