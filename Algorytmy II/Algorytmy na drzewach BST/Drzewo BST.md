#### Idea algorytmu
- Dla każdego węzła nie będącego liściem, wszystkie wartości przechowywane w lewym poddrzewie są mniejsze od wartości węzła, natomiast wartości przechowywane w prawym poddrzewie są większe od wartości w tym węźle
- Cel - reprezentacja słownika z liniowym porządkiem na zbiorze kluczy
- Wykorzystujemy drzewa binarne, ale konstruowane tak aby wypisując przechowywane klucze w kolejności INORDER otrzymać ciąg rosnący
- **lewy syn jest zawsze mniejszy**
- **prawy syn jest zawsze większy**

#### Implementacja
 - można zaimplementować za pomocą struktury dowiązaniowej, gdzie każdy węzeł jest obiektem klasy posiadającym następujące pola:
	 - dane węzła (key i value)
	 - wskaźnik do rodzica
	 - wskaźnik do dzieci (left i right)
 - aby pamiętać drzewo przechowujemy wskaźnik do jego korzenia
 - dodatkowo zapamiętujemy węz