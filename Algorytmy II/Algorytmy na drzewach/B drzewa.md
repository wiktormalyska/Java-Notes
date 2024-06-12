### (Perfectly Balanced Multiway Tree)
[[Drzewo BST]] nawet w wersji [[Drzewo AVL]] nie nadają się do przechowywania danych na dysku z powodu:
- długi czas dostępu do pamięci dyskowej
- odczyt i zapis porcjami
- chaotyczny zapis węzłów BST bez uwzględnienia struktury pamięci generuje niepotrzebne dostępy
- B-drzewo jest drzewem poszukiwań wyższych rzędów
- jest słownikiem na dysku

### Idea Algorytmu
- Uogólnienie [[Drzewo BST]] poprzez zwiększenie liczby kluczy, które są przechowywane w pojedynczym węźle (arność drzewa)
- BST - w węźle mamy 2 wskaźniki: lewy i prawy syn oraz klucz, który rozdziela wartości przechowywane w lewym i prawym poddrzewie
- B-drzewo rzędu $I$ - w węźle jest $I$ wskaźników do synów oraz $I-1$ kluczy które rozdzielają elementy poszczególnych poddrzew (klucze są posortowane)
- wartości w poddrzewie wskazywanym przez $pi$ (syna) muszą mieścić się w przedziale $(ki-1..ki)$ (kluczy)
### Idea Algorytmu prościej
- skrajnie lewy syn jest korzeniem poddrzewa zawierającego klucze mniejsze od kluczy przechowywanych w ojcu
- 