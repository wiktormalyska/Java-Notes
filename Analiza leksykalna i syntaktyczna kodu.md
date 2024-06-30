

#### Analiza leksykalna 
![[Pasted image 20240630224251.png]]

- Jest wykorzystywana przez skaner
- jest wykonywana na podstawie reguł, które do skanera dostarczone są z zewnątrz
- polega na analizie kodu i klasyfikacji poszczególnych łańcuchów znaków za pomocą znaczników
- Tokeny to zmienne późniejszej gramatyki
- skaner tworzy plik z rozbiorem leksykalnym analizowanego kodu, który staje się jednym z plików wejściowych dla parsera
- w linuksie używane jest flex kompatybilny z lex

#### Analiza syntaktyczna
![[Pasted image 20240630230252.png]]
- wykorzystywane jako parser
- opiera się na regułach parsera oraz pliku z danymi pochodzącymi od skanera
- reguły parsera to produkcje gramatyki zdefiniowane na tych samych tokenach, które były używane w regułach skanera
- parser tworzy pełną gramatykę (w postaci drzewa wyprowadzeń, tu nazywanym drzewem parsowania)
- w linuksie parser generuje bison, kiedyś yacc


#### Analiza semantyczna
![[Pasted image 20240630230518.png]]
- analiza znaczeniowa - przypisania konkretnych wartości do abstrakcyjnych tworów opisywanych tokenami (zmiennymi gramatyki) takimi jak wyrażenie, etykieta, zmienna itd. 
- analizowany jest kod pośredni generowany przez skaner i parser
- zajmuje się tym część kompilatora (interpretera)
- sprawdzane są zgodności typów zmiennych
- wyszukiwane są takie same etykiety w programie i twory im przypisane są utożsamiane
- analizowane są pętle i rekurencje
- generowane komu