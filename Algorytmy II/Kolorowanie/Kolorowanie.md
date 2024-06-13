Mówimy że $G$ jest grafem $k$-kolorowanym, jeśli każdemu wierzchołkowi można przypisać jeden z $k$ kolorów w taki sposób by wierzchołki przyległe miały różne kolory

Jeżeli graf $G$ jest $k$-kolorowany ale nie jest $(k-1)$-kolorowany to mówimy że jest on $k$-chromatyczny

Najmniejszą liczbę $k$ różnych kolorów potrzebnych do pokolorowania wierzchołków grafu $G$ nazywamy liczbą chromatyczną tego grafu

#### Algorytm dokładny kolorowania wierzchołków
- koloruj wierzchołki kombinacjami 2 kolorów
- przy każdej kombinacji sprawdź warunek pokolorowania
- jeżeli warunek spełniony - zakończ
- w przeciwnym wypadku zwiększ liczbę kolorów i powtórz proceduję aż do znalezienia właściwej kombinacji

- Sprawdza wszystkie możliwe układy kolorów wierzchołków i wybiera ten z najmniejszą liczbą użytych kolorów
- złożoność wykładnicza - realnie możliwy do wykonania jedynie dla bardzo małych grafów - około 10 wierzchołków

#### Zachłanny algorytm kolorowania wierzchołków grafu
Algorytm RS - naiwny
- Wejście: graf prosty $G$ o $n$ wierzchołkach
- Wyjście: pokolorowany graf $G$ - do wierzchołków przypisano liczbę oznaczającą kolor
- 