Algorytm KNP jest podobny do algorytmu MP, różni się sposobem wypełnienia tablicy $P$ (oznaczymy jako $P`$)

Tablicę $P`$ definiujemy jako
- dla $i<|wzorzec|$ : $P`[i]$ to długość najdłuższego prefikso-sufiksu słowa wzorzec jakiego że $wzorzec[p`[i]+1]!=wzorzec[i+1]$
- jeżeli dla danego i takiego prefikso-sufiksu nie ma to $P`[i]=-1$
- dla $i=|wzorzec|$ to $P`[i]=P[i]$

Aby uniknąć po przesunięciu wzorca natychmiastowej niezgodności musimy dodatkowo zażądać, aby znak le