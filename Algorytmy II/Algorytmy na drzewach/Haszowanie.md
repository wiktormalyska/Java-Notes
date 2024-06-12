Mieszanie jest zupełnie odmiennym rozwiązaniem problemu słownika od [[Drzewo BST]]
Wykorzystuje się w nim własności numeryczne przechowywanych elementów (w [[Drzewo BST]] jedyna informacja o elementach pochodzi z wyników porównań)

Umiemy wykonać operację SEARCH w czasie logarytmicznym przy pomocy [[Drzewo AVL]] $O(\log n)$
Chcemy uzyskać czas stały $O(1)$

### Adresowanie bezpośrednie - direct access table
- Prosta metoda, skuteczna jeżeli uniwersum kluczy $U$ jest rozsądnie małe
- Zbiór dynamiczny o $n$ (unikalnych) kluczach można reprezentować za pomocą tablicy z adresowaniem bezpośrednim, w której każdej pozycji odpowiada klucz należący do uniwersum
![[Pasted image 20240613004102.png]]
- na pozycji $k$ znajduje się do elementu o kluczy $k$, lub cały element jest umieszczany w taj komórce tablicy
- trywialna implementacja operacji słownikowych - search, insert, delete - każda działa w czasie $O(1)$
- Problem 1 - klucze mogą nie być dodatkowymi liczbami całkowitymi
- Problem 2 - duże zużycie pamięci - jeżeli kluczy jest dużo lub chociaż niewiele, ale mają wartości z dużego zakresu

Chcemy skorzystać z małej tablicy w której za pomocą funkcji $h$ będziemy przechowywać klucze z $S$
Jeśli $h$ będzie odwzorowaniem losowym, to możemy liczyć na mało kolizji

#### Funkcja haszująca
Jest to funkcja, która każdemu elementowi ze zbioru dopuszczalnych kluczy przyporządkowuje liczbę całkowitą

#### Tablica haszująca - Idea
- n-elementowa tablica rekordów postaci (key, value)
- h - funkcja haszująca
- wstawienie pary $(k,v)$ do tablicy haszującej to wykonanie przypisania $tab[(k)]=(k,v)$

#### Konflikty
- Obliczona wartość funkcji haszującej daje indeks w tablicy, pod którym można odnaleźć poszukiwany element
- Jeżeli okaże się że na pozycji o danym indeksie znajduje się kilka elementów zbioru $S$, mówimy o wystąpieniu zjawiska KOLIZJI

Kolizję nazywamy sytuację gdy dla różnych kluczy, funkcja h przyjmuje tę samą wartość

#### Rozwiązywanie konfliktów
- metoda łańcuchowa (haszowanie otwarte)
- adresowanie otwarte (haszowanie zamknięte)

##### Haszowanie otwarte (chaining)
- Elementy tablicy haszującej **tab** to listy wskaźnikowe przechowujące pary **(k,v)**.
- Element tablicy **tab** o indeksie $I$ zawiera listę przechowującą pary **(k,v)** takie, że $h(k)=I)$ a $h$ jest funkcją haszującą

##### Haszowanie zamknięte - adresowanie liniowe/kwadratowe
- m (ilość miejsc) $>=$ n (liczba elementów)
- w przypadku kolizji dokonaj rehaszowania czyli oblicz/znajdź kolejne miejsce, gdzie potencjalnie można umieścić zapisywany rekord
- ponawiaj próbę aż znajdziesz wolne miejsce

#### Haszowanie zamknięte - podwójne (double hashing)
- Zamiast przyrostu 1 (lub kwadrat) można wziąć przyrost określony przez drugą funkcję mieszającą $h`(v)$
- $r(i,k)=((h(k)+i*h`(k)))