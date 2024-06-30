**Rekurencja** w programowaniu logicznym pozwala na definiowanie złożonych zależności i operacji poprzez odwoływanie się do siebie samego. Jest kluczowa dla wyrażania iteracji i zależności, które nie są stałe.

- **Definicja Rekurencyjna:** Rekurencja w logice oznacza, że reguła może się odwoływać do samej siebie bezpośrednio lub pośrednio.
    
- **Przykład:**
    
    factorial(0, 1).\text{factorial(0, 1).}factorial(0, 1). factorial(N, F)←N > 0∧N1 is N - 1∧factorial(N1, F1)∧F is N * F1.\text{factorial(N, F)} \leftarrow \text{N > 0} \land \text{N1 is N - 1} \land \text{factorial(N1, F1)} \land \text{F is N * F1}.factorial(N, F)←N > 0∧N1 is N - 1∧factorial(N1, F1)∧F is N * F1.
    
    Tutaj, obliczanie silni jest zdefiniowane rekurencyjnie.
    

##### Rekurencja W Prologu:

prolog

Skopiuj kod

`% Definicja silni factorial(0, 1). factorial(N, F) :-     N > 0,     N1 is N - 1,     factorial(N1, F1),     F is N * F1.`

W powyższym przykładzie, `factorial/2` jest definiowana rekurencyjnie, gdzie `N1 is N - 1` oblicza poprzednią wartość, a `F is N * F1` mnoży wynik poprzedniej rekurencji.