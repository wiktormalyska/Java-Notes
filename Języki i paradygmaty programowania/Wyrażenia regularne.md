- wykorzystywane w zadaniach dopasowania i rozpoznawania łańcuchów, m.in. w wyszukiwarkach, parserach, analizatorach treści
- technicznie, wyrażenie regularne jest przez aplikację zamieniane na odpowiedni automat
- prowadzi to do słusznego podejrzenia, że automaty RE nawet jeśli nie są sobie równoważne, to mają wiele wspólnego
- konkretne symbole używane do budowania RE różnią się pomiędzy aplikacjami i systemami, ale podstawowe zasady są niezmienne

##### Na językach można wykonywać trzy podstawowe operacje
- suma - definiuje się jako sumę zbiorów łańcuchów należących do obu języków
- konkatenacja - definiuje się jako zbiór łańcuchów utworzonych jako konkatenacje łańcuchów należących do obu języków
- domknięcie - zdefiniowane jako suma łańcuchów należących  do kolejnych konkatenacji języka z samym sobą

#### Definicja: algebra RE
- Algebrę wyrażeń regularnych definiuje się następująco
	- ε﻿ jest RE reprezentującym język {𝜀}{ε}﻿, czyli 𝐿(𝜀)={𝜀}L(ε)={ε}﻿
	- ∅﻿ jest RE reprezentującym język ∅∅﻿, czyli 𝐿(∅)=∅L(∅)=∅﻿
	- jeśli 𝑅1R1​﻿ i 𝑅2R2​﻿ są RE, to:
    $$(𝑠𝑢𝑚𝑎)𝐿(𝑅1+𝑅2)=𝐿(𝑅1)∪𝐿(𝑅2)$$
    
    $$(𝑘𝑜𝑛𝑘𝑎𝑡𝑒𝑛𝑎𝑐𝑗𝑎)𝐿(𝑅1𝑅2)=𝐿(𝑅1)𝐿(𝑅2)$$
    $$(𝑑𝑜𝑚𝑘𝑛𝑖ę𝑐𝑖𝑒)𝐿(𝑅1∗)=(𝐿(𝑅1))∗$$

- jeśli 𝑅﻿ jest RE, to (𝑅)﻿ jest również RE reprezentującym ten sam język co 𝑅,𝐿((𝑅))=𝐿(𝑅)R
- **Uwagi:**
	- pojedyncze symbole alfabetu są RE
	- suma i konkatenacja RE (domknięcie (dopełnienie) jest kombinacją obu tych operacji) tworzą poprawne RE
	- RE możemy grupować za pomocą nawiasów

##### Kolejność wykonywania operacji na RE:
1. domknięcie (_”potęgowanie”_)
2. konkatenacja (_”mnożenie”_)
3. suma

##### Twierdzenia o odpowiedniości automatów i RE
