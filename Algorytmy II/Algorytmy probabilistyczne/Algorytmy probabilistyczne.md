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