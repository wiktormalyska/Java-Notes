- Blisko spokrewniony z [[Algorytm Knutha-Morrisa-Pratta]]
- Mniej popularny
- Służy do znalezienia wszystkich wystąpień wzorca w tekście
- Przetwarza tekst w jednym przebiegu i czasie liniowym względem długości

#### Działanie
- Tworzy tablicę prefixów dla wzorca
- Pomaga określić ile znaków można pominąć po znalezieniu niezgodności
- Przechodzi tekst korzystając z tablicy prefixów, aby uniknąć niepotrzebnych porównań

#### Różnice między [[Algorytm Knutha-Morrisa-Pratta]]
- KMP jest bardziej zoptymalizowany
- MP wskazuje długość najdłuższego dopasowanego prefiksu/sufiksu
- W KMP tablica prefixów jest dostosowana do uniknięcia niepotrzebnego cofania w tekście