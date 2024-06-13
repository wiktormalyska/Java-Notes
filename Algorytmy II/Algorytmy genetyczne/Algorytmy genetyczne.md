Algorytmy ewolucyjne nie gwarantują znalezienia optimum globalnego, jednak generalnie zapewniają znalezienie rozwiązania wystarczająco dobrego w akceptowalnym przedziale czasu
Stąd głównym zastosowaniem tych algorytmów powinny być problemy, dla których nie istnieję techniki specjalizowane. Nawet jeśli techniki takie istnieją, można osiągnąć poprawę ich działania poprzez ich połączenie z algorytmami ewolucyjnymi

#### Ewolucja Darwinowska - survival of the fittest
- Każde środowisko ma ograniczone zasoby
- Osobniki żyjące w środowisku rozmnażają się
- Osobniki, które najlepiej rywalizują o zasobu mają największą szansę na rozmnożenie się
- U potomstwa występują niewielkie losowe zmiany (mutacje), które mogą poprowadzić do powstania osobników lepiej dopasowanych do środowiska
- W wyniku zmian mogą powstać osobniki słabo dopasowane do środowiska - małe szanse na przeżycie i potomstwo
- Wraz z upływem czasu dobór naturalny sprawia, że przystosowanie osobników w populacji rośnie

#### Algorytmy Ewolucyjne (EA)
Są procedurami heurystycznego przeszukiwania opartymi na mechanizmach doboru naturalnego i dziedziczenia, wykorzystując zasadę przeżycia osobników najlepiej przystosowanych
Od klasycznych metod odróżnia je kilka istotnych cech:
- Nie przetwarzają bezpośrednio parametrów zadania lecz ich zakodowaną postać
- Nie wychodzą z pojedynczego punktu, lecz wykorzystuję pewną ich populację
- Nie korzystają z pochodnych ani innych informacji pomocniczych
- Nie stosują reguł deterministycznych lecz probabilistyczne
Algorytm ewolucyjne przetwarza populację **osobników**, z których każdy jest propozycją rozwiązania postawionego problemu. Działa on w **środowisku**, które można zdefiniować na podstawie problemu rozwiązywanego przez algorytm
W środowisku każdemu osobnikowi jest przyporządkowana wartość liczbowa, określająca jakość reprezentowanego poprzez niego rozwiązania - **przystosowanie osobnika**
Każdy osobnik jest wyposażony w informację stanowiącą jego **genotyp**, będący przepisem na utworzenie **fenotypu** - zestawu cech określanych przez genotyp, podlegających ocenie środowiska.
Mówi się o kodowaniu fenotypu przez genotyp
FENOTYP - punkt w przestrzeni rozwiązań
GENOTYP - punkt w przestrzeni kodów

Środowisko można opisać **funkcją przystosowania**, za pomocą której osobnikowi przypisuje się przystosowanie na podstawie jego fenotypu. Może ona być stacjonarna lub zmienna w czasie, może też zawierać element losowości, Funkcja przystosowania jest określona dla genotypów. Genotyp osobnika składa się z **chromosomów**. Każdy z chromosomów składa się z elementarnych jednostek zwanych **genami**. Działanie algorytmu ewolucyjnego sprowadza się do wykonania pętli, w której występują po sobie:
- reprodukcja
- operacje genetyczne
- ocena
- sukcesja

#### Strategia Ewolucyjna - Schemat Działania
- Utwórz losową populację złożoną z N osobników
- Wygeneruj M osobników potomnych dla losowo wybranych osobników poprzedniego pokolenia z zastosowaniem mutacji i krzyżowania
- Spośród M+N osobników wybierz N najlepszych względem funkcji dopasowania
- Wróć do punktu 2

![[Pasted image 20240613102919.png]]

#### Algorytm Genetyczny - Schemat Działania
- Inicjacja pętli ewolucji - utworzenie poprzez wybór lub wylosowanie populacji bazowej z opcjonalnym uwzględnieniem wpływu środowiska złożonej z osobników reprezentowanych przez ciągi binarne określonej długości
- Ocena przystosowania osobników na podstawie obliczonej funkcji przystosowania
- Sprawdzenie warunku zatrzymania na podstawie jakości przystosowania najlepszego osobnika w populacji lub stwierdzenia stagnacji algorytmu
- Selekcja - populacja poddawana jest ocenie, najlepiej przystosowane osobniki mają największe szanse wylosowania do grupy rodziców, którzy wezmą udział w rekombinacji genów
- Zastosowanie operatorów genetycznych
	- Krzyżowanie - proces rekombinacji genów, prowadzący do powstania nowych chromosomów w wyniku wymiany fragmentów chromosomów rodziców
	- Mutacja - proces zmiany pojedynczego genu w chromosomie, występuje na ogół z bardzo małym prawdo