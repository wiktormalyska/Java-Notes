#### Definicja słownika
- Słownik jest abstrakcyjną strukturą danych służącą do operowania na elementach $→$ kluczach o następującym zbiorze operacji
	- SEARCH(S,x)
	- INSERT(S,x)
	- DELETE(S,x)
- można ten zbiór rozszerzyć o operacje dodatkowe wspomagające pracę:
	- CREATE()
	- EMPTY(S)
	- BROWSE(S)
	- MINIMUM, MAXIMUM, SUCCESSOR, PREDECESOR

#### Implementacje
- Listy lub tablice (naiwne)
	- nieuporządkowane
	- uporządkowane
- Drzewa
	- [[Drzewo BST]]
	- AVL, (czerwono-czarne)
	- B-drzewa
	- samoorganizujące drzewa BST $(*)$
	- (a,b) -drzewa (w szczególności 2-3trees) $(*)$
- Tablice haszujące