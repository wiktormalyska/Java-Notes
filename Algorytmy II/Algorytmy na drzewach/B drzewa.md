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
- skrajnie prawy syn robi dosłownie odwrotnie to co lewy syn czyli trzyma większe klucze od ojca
- i-ty syn jest korzeniem drzewa zawierające klucze należące do przedziału pomiędzy $(i-1)$-tym a $i$-tym kluczem ojca

![[Pasted image 20240613000038.png]]

#### t - Minimalny stopień B-Drzewa
- Każdy węzeł różny od korzenia **musi** mieć co najmniej **t-1** kluczy
- Każdy węzeł wewnętrzy różny od korzenia ma zatem **co najmniej t** synów
- Jeśli drzewo jest niepuste to korzeń musi mieć co najmniej jeden klucz
- Każdy węzeł może zawierać **co najwyżej 2t-1** kluczy to znaczy że każdy węzeł wewnętrzny może mieć **co najwyżej 2t synów**
- Powiemy że węzeł jest **pełny** jeżeli zawiera **dokładnie 2t-1** kluczy
- ##### Podsumowując:
	- Liczba kluczy w węźle - od t-1 do 2t-1
	- Liczba synów w węźle - od t do 2t

#### Wyszukiwania (search)
Wyszukiwanie elementu odbywa się analogicznie do [[Drzewo BST]]
Różnica polega na tym, że w każdym węźle B-Drzewa dokonuje się wyboru poddrzewa, w którym ma być kontynuowane wyszukiwanie, spośród poddrzew, których liczba zależy od liczby kluczy w tym węźle
Takich poddrzew w węźle x jest x.n+1, podczas gry w [[Drzewo BST]] zawsze wybiera się jedno poddrzewo z dwóch

#### Insert i Delete
Insert i Delete jest w B-Drzewie jest bardziej skomplikowane niż w przypadku [[Drzewo BST]]
Należy dbać aby zachowane były warunki na liczbę kluczy w węzłach i aby wszystkie liście były na tym samym poziomie.
Potrzebne do tego są pomocnicze operacje: dzielenie węzła ,przesuwanie klucza i łączenie węzłów

##### 1 metoda
Dodaj/Usuń element a następnie odtwórz strukturę B-Drzewa wykorzystując pomocnicze operacje - analogia do metody dla [[Drzewo AVL]]
##### 2 metoda
Schodząc w dół drzewa, szukaj węzła, gdzie należy dodać/usunąć klucz, dbając o to, aby w wyniku tej operacji nie została zaburzona struktura B-Drzewa
- Analogicznie jak w [[Drzewo BST]] szukaj liścia w którym należy wstawić żądany klucz
- Jeżeli napotykasz węzeł zawierający $2t-1$ kluczy to rozbij go na 2 węzły dzięki czemu zagwarantujemy, że liść będzie miał wolne miejsce na klucz
- Dopisz klucz do odpowiedniego liścia

- Szukaj usuwanego klucza $k$
- wchodząc do węzła niebędącego korzeniem i zawierającego $t-1$ kluczy spróbuj przesunąć do niego klucz z sąsiada
- jeżeli przesunięcie się nie udało to scal rozważany węzeł z sąsiadem
- w ten sposób uzyskujemy pewność, że w chwili odnalezienia węzła zawierającego $k$ będzie można usunąć klucz nie zaburzając warunku na minimalną liczbę kluczy w węźle
- po odnalezieniu węzła zawierającego klucz wykonaj jedną z poniższych akcji
	- jeżeli $k$ jest w liściu - usuń $k$
	- jeżeli $k$ znajduje się w węźle wewnętrznym $W$ - odnajdź $x$ i $y$, synów $W$ sąsiadujących z $k$, a następnie
		- weź ten węzeł ($x$ lub $y$) który zawiera co najmniej $t$ kluczy, znajdź w drzewie o wybranym korzeniu klucz najbliższy $k$, zamień go miejscami z $k$ i rekurencyjnie usuń $k$ w drzewie o korzeniu w starym miejscu $k$ (wstawiliśmy tam $x$ lub $y$)
		- jeżeli nie udało się w poprzednim kroku wybrać $x$ ani $y$, czyli oba z

#### Dzielenie węzła
Węzeł zawierający $2t-1$ kluczy można podzielić na 2 węzły przechowujące $t-1$ kluczy - środkowy przenosimy do ojca
![[Pasted image 20240613001942.png]]
![[Pasted image 20240613001949.png]]

#### Przesuwanie klucza
Jeżeli brakuje kluczy w węźle którego brat ma co najmniej t kluczy, to można dokonać przesunięcia kluczy pomiędzy rodzeństwem a ojcem - klucz od brata przenosimy do ojca, a klucz ojca trafi do rozważanego węzła
![[Pasted image 20240613002112.png]]
![[Pasted image 20240613002119.png]]

#### Łączenie węzłów
Jeżeli brakuje klucza w węźle, którego najbliższe rodzeństwo ma minimalną dopuszczalną liczbę kluczy, to można scalić ze sobą 2 węzły - poza kluczami z 2 braci do nowego węzła wchodzi jeden klucz od ojca
![[Pasted image 20240613002243.png]]
![[Pasted image 20240613002302.png]]

