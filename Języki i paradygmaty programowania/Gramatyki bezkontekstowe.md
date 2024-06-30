Bezkontekstowa → niezależnie od tego w jakim kontekście wyrażenia zostaną użyte (program zostanie uruchomiony), wynik będzie taki sam
Nie wchodzimy w znaczenie, wchodzimy tylko w składnię

#### Gramatyka bezkontekstowa
- nazywamy czwórkę $G = (V,T,P,S)$, gdzie
	- V - zbiór zmiennych, każda zmienna jest utożsamiana z jednym językiem. Jedna ze zmiennych jest wyróżniona, odpowiadając symbolowi początkowemu S, reszta to pomocnicze klasy łańcuchów
	- T - zbiór symboli końcowych, niepusty zbiór skończony, zawierający łańcuchy definiowanego języka
	- P - zbiór produkcji - skończony zbiór reguł pozwalających na rekurencyjne definiowanie języka
	- S - symbol początkowy 

##### Produkcja
- Każda produkcja jest parą (A,C) gdzie A należy do zmiennych i jest pojedynczą zmienną, C jest dowolnym symbolem terminalnym lub nie terminalnym, również łańcuchem pustym
- Reguła określa sposób tworzenia łańcuchów w języku reprezentowanym przez zmienną będącą głową
- W praktyce produkcje tożsame są wyrażeniom regularnym, jednak tych ostatnich nie używa się jawnie na poziomie gramatyk

#### Podsumowanie
Gramatyka jest konstrukcją szerszą niż omawiane do tej pory
- operuje na więcej niż jednym języku, a więc odpowiada jej zestaw automatów lub pojedynczy automat złożony
- RE spełnia rolę wzorców łańcuchów akceptowanych przez ten automat
- produkcje wykorzystują RE do określania reguł budowania akceptowalnych łańcuchów
- SZEROKOŚĆ gramatyki nie polega na tym, że zawiera w sobie informacje, których nie ma w DAS i RE ale informacje te podane są w sposób jawny poprzez produkcję, które można utworzyć rozkładając RE na czynniki pierwsze