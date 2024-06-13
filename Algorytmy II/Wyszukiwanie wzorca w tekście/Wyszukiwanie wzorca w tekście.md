Problem pattern matchingu - Dany jest tekst $T$ i wzorzec $P$ które są ciągami znaków o długości $n$ i $m$ nad pewnym ustalonym i skończonym alfabetem $A$. Należy znaleźć wszystkie wystąpienia wzorca $P$ w tekście $T$

Jeśli istnieje prefiks $s$, który jest równy sufiksowi $s$ to mówimy że tworzą one PREFIKSO-SUFIKS
Jeśli dany łańcuch posiada prefikso-sufiks o długości $k$ to okresem nazywamy taką liczbę całkowitą $d$, że zachodzi warunek $s[0..k]=s[d..n],d=|s|-|prefSuf(s)|$

![[Pasted image 20240613091157.png]]

W algorytmie naiwnym nie wykorzystujemy informacji uzyskanych podczas nieudanych prób dopasowania wzorca, a chcielibyśmy wiedzieć ile znaków tekstu można pominąć przy kolejnych porównaniach
Rozważamy tablicę $P$ o rozmiarze wielkości wzorca, która w komórkach o indeksie $j$ będzie zawierała maksymalną długość prefikso-sufiksu dla pierwszych $j$ znaków wzorca

#### Złożoność algorytmu
- 2 pętle sugerują złożoność $O(|wzorzec|*|tekst|)$ ale
- Algorytm wypełniania tablicy $P$ działa w $O(|wzorzec|)$
- Każdy znak tekstu który znajduje swój odpowiednik we wzorcu nie jest więcej porównywany
- Jeżeli zostaje stwierdzona niezgodność ze wzorcem i zostaje zwiększone i co najmniej 1
- złożoność algorytmu MP jest rzędu $O(|tekst|)$
## Algorytm Morrisa-Pratta
## Algorytm Knutha-Morrisa-Pratta
## Algorytm Karpa-Rabina
