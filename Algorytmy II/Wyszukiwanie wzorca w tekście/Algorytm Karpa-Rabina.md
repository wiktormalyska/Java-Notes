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
- jako $q$ możemy przxu