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
 - dodatkowo zapamiętujemy węzły MAX i MIN odpowiednio o największym i najmniejszym kluczu

Drzewo BST nie musi być zupełne - wolne miejsca mogą być nie tylko na ostatnim poziomie

![[Pasted image 20240612211822.png]]

##### Działanie search(key)
- zacznij od korzenia
- dopóki nie dojdziesz do NULL, porównuj key z kluczem bieżącego węzła
- jeżeli jest równy to zwróć wartość przechowywaną w tym węźle
- jeżeli jest mniejszy to idź do lewego syna
- jeżeli jest większy to idź do prawego syna
- jeżeli dojdziesz do NULL to nie ma takiego klucza

##### Działanie insert(key, value)
- nowy klucz 