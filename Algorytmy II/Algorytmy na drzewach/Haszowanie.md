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