**Klauzule Horna** są specjalnym typem klauzul logicznych używanych w programowaniu logicznym i stanowią podstawę systemów wnioskowania w Prologu.

- **Definicja:** Klauzula Horna ma postać:

A←B1∧B2∧…∧BnA \leftarrow B_1 \land B_2 \land \ldots \land B_nA←B1​∧B2​∧…∧Bn​

Gdzie:

- AAA to **główka** (head), a B1,B2,…,BnB_1, B_2, \ldots, B_nB1​,B2​,…,Bn​ to **ciało** (body) klauzuli.
    
- Klauzula Horna jest prawdziwa, gdy AAA jest prawdziwe, o ile wszystkie BiB_iBi​ są prawdziwe.
    
- **Przykład:**
    
    ancestor(X, Y)←parent(X, Y)\text{ancestor(X, Y)} \leftarrow \text{parent(X, Y)}ancestor(X, Y)←parent(X, Y) ancestor(X, Y)←parent(X, Z)∧ancestor(Z, Y)\text{ancestor(X, Y)} \leftarrow \text{parent(X, Z)} \land \text{ancestor(Z, Y)}ancestor(X, Y)←parent(X, Z)∧ancestor(Z, Y)
    
    Pierwsza klauzula stwierdza, że X jest przodkiem Y, jeśli X jest rodzicem Y. Druga mówi, że X jest przodkiem Y, jeśli X jest rodzicem Z, a Z jest przodkiem Y.
    

##### Klauzula Fakt:

parent(john, mary).\text{parent(john, mary).}parent(john, mary).

##### Klauzula Reguły:

ancestor(X, Y)←parent(X, Y).\text{ancestor(X, Y)} \leftarrow \text{parent(X, Y)}.ancestor(X, Y)←parent(X, Y).