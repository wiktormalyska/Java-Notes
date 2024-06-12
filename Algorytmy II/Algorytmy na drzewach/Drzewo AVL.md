Są to [[Drzewo BST]], w których dla każdego węzła wysokość poddrzewa o korzeniu w lewym synu różni się od wysokości poddrzewa o korzeniu w prawym synu o co najwyżej 1

![[Pasted image 20240612215416.png]]

$BF=hl-hr$, gdzie hl, hr to odpowiednio wysokości lewego i prawego poddrzewa
- BF=1 - lewe poddrzewo jest wyższe o 1 poziom od prawego hl > hr
- BF=0 - oba poddrzewa są równej wysokości hl=hr
- BF=-1 - prawe poddrzewo jest wyższe o 1 poziom od lewego hl < hr

Każdy węzeł drzewa AVL posiada dodatkowe pole tzw. **współczynnik równowagi** - BF *(balance factor)* - czyli różnicę pomiędzy wysokościami lewego i prawego poddrzewa

#### Operacje na drzewach AVL
- Operacje nie wymagające modyfikacji wykonujemy w drzewach AVL tak samo jak w [[Drzewo BST]]
- W przypadku INSERT i DELETE, po odpowiednio wstawieniu lub usunięciu węzła trzeba jeszcze zrównoważyć drzewo


#### Rotacje
Jeżeli w wyniku jakiejś operacji na drzewie zostaje zachwiana własność drzewa AVL (BF=2 lub -2), przywracamy ją za pomocą dodatkowych operacji zwanymi ROTACJAMI, które odpowiednio przemieszczają 3 węzły

Istnieję 4 rodzaje rotacji - dwie pojedyncze oraz dwie podwójne będące faktycznie złożeniem rotacji pojedynczych

- Rotacja pojedyncza LL - PRAWO
- Rotacja pojedyncza RR - LEWO
- Rotacja podwójna - RL - LEWO-PRAWO
- Rotacja podwójna - LR - PRAWO-LEWO

RR,LL,RL,LR określają sposób połączenia węzłów przed wykonaniem rotacji
Jeśli węzły łączą się prawymi krawędziami to przypadek RR, jeśli tylko lewymi to przypadek LL, Mieszane połączenia to LR i RL\

##### Przykład Rotacji RR (w lewo)
![[Pasted image 20240612220323.png]]
W rotacji uczestniczą węzły A i B. Węzeł B zajmuje miejsce węzła A, węzeł A staje się lewym synem węzła B, Lewy syn węzła B (BL) staje się prawym synem węzła A

##### Przykład Rotacji LL (w prawo)
![[Pasted image 20240612220452.png]]
Rotacja LL jest lustrzanym odbiciem rotacji RR. W rotacji uczestniczą węzły A i B. Węzeł B zajmuje miejsce węzła A, węzeł A staje się prawym synem węzła B. Prawy syn węzła B staje się lewym synem węzła A

##### Przykład 