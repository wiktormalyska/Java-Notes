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
- nowy klucz zawsze wstawiamy jako liść
- zacznij od korzenia i robisz tak jak przy operacji search aż dojdziesz do NULL
- jeżeli doszedłeś do liścia wstaw tam nowy węzeł w miejsce NULL, podpinając wskaźnik do i od rodzica

##### Działanie delete(key)
- zacznij od korzenia i postępuj tak jak przy operacji search aż znajdziesz węzeł do usunięcia 
- gdy znajdziesz węzeł możliwe są 3 warianty:
	- nie ma synów - usuń węzeł, wskaźnik od rodzica ustaw na NULL
	- 1 syn - usuń węzeł, syna wraz z całym poddrzewem podepnij do rodzica usuniętego węzła
	- 2 synów - usuń węzeł i zastąp go węzłem x zawierającym klucz, który jest bezpośrednim następnikiem klucza usuwanego węzła, potem podepnij jedynego syna węzła x do rodzica 

#### Złożoność czasowa
- proporcjonalna do wysokości drzewa