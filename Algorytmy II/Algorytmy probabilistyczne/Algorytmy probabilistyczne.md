Algorytm probabilistyczny to taki, który oprócz danych wejściowych otrzymuje dodatkowo losowy ciąg liczb.
Polega na losowym przeszukiwaniu przestrzeni rozwiązań, przy czym kolejne próby znalezienia rozwiązania są wykonywane na podstawie wskazań losowych
W konsekwencji, taki algorytm dla tych samych danych wejściowych może się różnie zachowywać
Zachowanie algorytmu jest zmienną losową zależną od wartości losowych - może być to czas działania, wyniki lub obie te cechy

#### Strategia
- Dla danej przestrzeni rozwiązań wylosuj próbkę do sprawdzenia
- Sprawdź potencjalne rozwiązanie
- Jeśli uzyskane rozwiązanie nie jest akceptowalne, przejdź do etapu pierwszego

#### Po co losowość
- Możemy zrezygnować z pełnej poprawności wyników na rzecz ich dużego prawdopodobieństwa
- Zredukować przestrzeń przeglądanych rozwiązań na rzecz krótkiego oczekiwania na odpowiedź
- Niedeterministyczne - wymagają przypadkowego wskazania potencjalnego rozwiązania
- Stosunkowo odporne na dane złośliwe
- Prostsze i szybsze od swoich deterministycznych wersji

#### Typy algorytmów probabilistycznych
- Monte Carlo - ograniczony czas działania, poprawne wyniki z dużym prawdopodobieństwem, nie ma gwarancji ustalenia wyniku, np. obliczanie pól figur, algorytm szukania pokrycia macierzy przez wielokrotny losowy wybór kolejnych kolumn
- Las Vegas - zawsze dobre wyniki, randomizacja służy poprawieniu szybkości działania, np. szukanie liczby pierwszej, random Quick Sort

- Random Quick Sort - LV
- znajdź  liczbę pierwszą w podanym przedziale - LV
- policz pole figury $F$ - MC
- problem najmniejszego rozcięcia ( zbiór rozspajający krawędzi grafu ) - MC
- problem długiej ścieżki (długości $k$)
- problem ucztujących filozofów