- $n=|wzorzec|$
- $r$ - krotność używanego alfabetu
- $q$ - największa liczba pierwsza taka, że $(r+1)*q$ nie przekracza zakresu
- $h$ - funkcja haszująca, zwraca pewną wartość
- $h(a[i..i+n-1])=(ai+n−1 + ai+n−2r + ai+n−3r^2 + ... + air^n−1) mod q$
- $h(a[i...i+n-2])=(h(a[i-1...i+n-1])-ai−1r^(n−1) )r + ai+n)$ ← WAŻNA WŁASNOŚĆ

### Przykład funkcji h
- Alfabet : $[A,B,C]$
- Badany tekst: $CBBAB$
- czyli $r=3$, cyfry posiadają wartości $A=0$,$B=1$,$C=2$
- jako $q$ możemy przyjąć np.23
- $h(CBBAB) = (1* 3^0 + 0*3^1 + 1*3^2 + 1*3^3 + 2*3^4)\mod23=199\mod23=15$
- Funkcja haszująca musi być taka aby w prosty sposób hasz okna po przesunięciu o 1 pozycję w obrębie łańcucha łatwo obliczyć

#### Złożoność
- pesymistyczna $O(|wzorzec|*|tekst|)$
- oczekiwana $O(|wzorzec|+|tekst|)$
- w praktyce $O(|tekst|)$

Algorytm może mieć problem przy obliczaniu dużych wartości np. wszystkie znaki z alfabetu ASCII - rozwiązaniem jest algorytm szybkiego potęgowania modulo