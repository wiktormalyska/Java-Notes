Dział algorytmiki zajmujący się algorytmami i strukturami danych pozwalającymi efektywnie wykonać działania na obiektach geometrycznych, takich jak zbiory punktów, odcinków, wielokątów, okręgów

Najczęściej rozpatrywane są problemy na płaszczyźnie czy też przestrzeni
- kiedy 2 odcinki się przecinają
- kiedy punkt należy do wielokąta
- jak znaleźć otoczkę wypukłą zbioru punktów na płaszczyźnie
- jak stwierdzić czy istnieję przecinające się pary odcinków

#### Szukanie przecinających się par odcinków - czy jakakolwiek para odcinków w zbiorze się przecina
- dane - odcinki reprezentują krzywą na mapie - drogę lub rzekę
- problem - nakładając na siebie 2 mapy - dróg i rzek znajdź wszystkie przecięcia par odcinków
- rozwiązanie siłowe - weź każdą parę odcinków, oblicz czy się nie przecinają, jeśli tak to podaj ich punkt przecięcia - $O(n^2)$

#### Metoda zamiatania - przemyślenia
- w praktyce większość odcinków nie ma przecięć lub jest ich niewielka liczba
- czas działania algorytmu powinien zależeć nie tylko od liczby odcinków ale także od liczby punktów przecięcia
- należy uwzględnić geometrię układu

Algorytm wrażliwy na wynik
czas działania algorytmu jest wrażliwy na rozmiar rozwiązania (liczbę przecięć)

- Przeszukujemy płaszczyznę na której wyznaczony jest zbiór punktów od strony lewej do prawej - z wzór pionowej miotły która przesuwa się po płaszczyźnie
- Stan miotły zmienia się w sposób dyskretny w miejscach nazywanych punktami zdarzeń - są nimi współrzędne napotykanych punktów
- Wszystkie obiekty na płaszczyźnie są w jednym z 3 stanów
	- przetworzony (na lewo od miotły)
	- aktywny (na lewo od miotły)
	- oczekujący (na prawo od miotły)
- założenia upraszczające - żaden odcinek nie jest pionowy i żadne 3 odcinki nie przecinają się w 1 miejscu

#### Układ współrzędnych polarnych
Układ współrzędnych na płaszczyźnie wyznaczony przez pewien punkt $O$ zwany biegunem oraz półprostą o początku w punkcie $O$ tzw. oś biegunowa

Sortowanie względem współrzędnych biegunowych wektorów - promień i kąt nachylenia do osi OX

#### Zamiatanie polarne
- miotła to półprosta umocowana w biegunie, wykonująca wokół niego obrót
- czyli punkty przeglądane są w kolejności wyznaczonej przez ich współrzędne w biegunowym układzie współrzędnych

