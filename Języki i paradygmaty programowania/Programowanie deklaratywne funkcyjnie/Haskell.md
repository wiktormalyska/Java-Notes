**Haskell** to język programowania funkcyjnego, który w pełni realizuje idee programowania deklaratywnego. Jego kluczowe cechy to:

- **Czystość:** Wszystkie funkcje są czyste, tzn. nie mają efektów ubocznych.
- **Leniwe Ewaluowanie:** Wyrażenia są oceniane tylko wtedy, gdy ich wyniki są potrzebne.
- **Silny System Typów:** Haskell korzysta z zaawansowanego systemu typów z polimorfizmem, typami algebraicznymi, i typami wyższego rzędu.

##### Przykład w Haskell:

haskell

Skopiuj kod

```haskell
-- Funkcja, która mnoży liczbę przez dwa
multiplyByTwo :: Int -> Int
multiplyByTwo x = x * 2

-- Lista liczb
numbers :: [Int]
numbers = [1, 2, 3, 4, 5]

-- Mnożenie każdej liczby przez dwa przy użyciu funkcji map
doubledNumbers :: [Int]
doubledNumbers = map multiplyByTwo numbers
```

Powyższy kod definiuje funkcję `multiplyByTwo`, która mnoży liczbę przez dwa, a następnie stosuje tę funkcję do listy liczb za pomocą `map`, co jest charakterystyczne dla stylu funkcyjnego.