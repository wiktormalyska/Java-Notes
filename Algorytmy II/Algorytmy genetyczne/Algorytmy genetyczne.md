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
- Nie korzystają z pochodn