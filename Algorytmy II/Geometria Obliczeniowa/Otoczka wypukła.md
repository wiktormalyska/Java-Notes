#### Otoczka wypukła
Dla zbioru $S$ n-punktów określonych przez ich współrzędne kartezjańskie, **WYPUKŁĄ OTOCZKĄ** nazywamy najmniejszy wielokąt wypukły zawierający wszystkie punkty ze zbioru $S$
![[Pasted image 20240613095555.png]]

Algorytm rozwiązujący problem otoczki wypukłej powinien zwrócić jej wierzchołki w kolejności ich występowania na obwodzie

#### Idea algorytmu
- zastosuj zamiatanie polarne
- weź punkt który na pewno należy do otoczki wypukłej i ustal go jako biegun w biegunowym u