#### Otoczka wypukła
Dla zbioru $S$ n-punktów określonych przez ich współrzędne kartezjańskie, **WYPUKŁĄ OTOCZKĄ** nazywamy najmniejszy wielokąt wypukły zawierający wszystkie punkty ze zbioru $S$
![[Pasted image 20240613095555.png]]

Algorytm rozwiązujący problem otoczki wypukłej powinien zwrócić jej wierzchołki w kolejności ich występowania na obwodzie

#### Idea algorytmu
- zastosuj zamiatanie polarne
- weź punkt który na pewno należy do otoczki wypukłej i ustal go jako biegun w biegunowym układzie współrzędnyvh
- przeglądaj pozostałe wierzchołki w kolejności wyznaczonej przez ich amplitudę (kąt) w przyjętym biegunowym układzie współrzędnych o środku $P$
- analizując kolejne punkty sprawdzaj czy leżą na prawo czy na lewo od ostatnio wyznaczonej krawędzi

#### Działanie algorytmu
- Wybierz punkt $p0$ o najmniejszej wartości drugiej współrzędnej $(y)$ - jeżeli jest ich kilka, weź ten o najmniejszej wartości pierwszej współrzędnej $(x)$
- w