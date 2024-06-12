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

##### Przykład Rotacji LR (prawo+lewo)
![[Pasted image 20240612220640.png]]
Rotacja RL jest połączeniem rotacji LL i rotacji RR
Węzeł C zastępuje węzeł A
Węzeł A staje się lewym dzieckiem węzła C i przejmuje syna węzła C w miejsce swojego prawego syna
Węzeł B staje się prawym synem C i przejmuje prawego syna węzła C w miejsce swojego lewego syna

##### Przykład Rotacji RL
![[Pasted image 20240612220917.png]]
Rotacja RL jest połączeniem rotacji LL i rotacji RR
Węzeł C zastępuje węzeł A
Węzeł A staje się prawym dzieckiem węzła C i przejmuje prawego syna węzła C w miejsce swojego lewego syna
Węzeł B staje się lewym synem C i przejmuje lewego syna węzła C w miejsce swojego prawego syna

##### Operacja Insert
- Insert jest taki jak w [[Drzewo BST]]
- Przy pomocy rotacji przywracaj zrównoważenie drzewa
- Idź do wstawionego liścia ku górze aktualizując współczynniki zrównoważenia
- Jeżeli gdzieś różnica w wysokości poddrzew wyniesie 0 to kończymy równoważenie
- Jeżeli gdzieś różnica wynosi 2 (BF=2 lub -2) to dokonaj jednej (pojedynczej lub podwójnej) rotacji i skończ równoważenie

##### Operacja Delete
- Delete jest taki jak w [[Drzewo BST]]
- Przy pomocy rotacji przywracaj zrównoważenie drzewa
- Idź do usuniętego liścia ku górze aktualizując współczynniki zrównoważenia BF
- Jeżeli różnica poddrzew wynosi 1 lub -1 skończ równoważenie
- Jeżeli różnica wynosi 2 lub -2 dokonaj rotacji i w zależności od przypadku zakończ działanie algorytmu lub kontynuuj aktualizację współczynników zrównoważenia BF
- **Możliwe jest to że będzie więcej niż 1 rotacja**

Złożoność operacji rotacji: $O(\log n)$
