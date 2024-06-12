Mieszanie jest zupełnie odmiennym rozwiązaniem problemu słownika od [[Drzewo BST]]
Wykorzystuje się w nim własności numeryczne przechowywanych elementów (w [[Drzewo BST]] jedyna informacja o elementach pochodzi z wyników porównań)

Umiemy wykonać operację SEARCH w czasie logarytmicznym przy pomocy [[Drzewo AVL]] $O(\log n)$
Chcemy uzyskać czas stały $O(1)$

### Adresowanie bezpośrednie - direct access table
- Prosta metoda, skuteczna jeżeli uniwersum kluczy $U$ jest rozsądnie małe
- Zbiór dynamiczny o $n$ (unikalnych) kluczach można reprezentować za pomocą tablicy z adresowaniem bezpośrednim, w której każdej pozycji odpowiada klucz należący do uniwersum
![[Pasted image 20240613004102.png]]
- na pozycji $k$ znajdujj