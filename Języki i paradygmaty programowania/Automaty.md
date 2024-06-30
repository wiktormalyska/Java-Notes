- **Automat** to abstrakcyjny **model** opisu pewnej klasy maszyn obliczeniowych i oprogramowania
- Użyteczny w przypadku procesów, w których można wyodrębnić zbiór parametrów w całości je definiujący
- W przypadku oprogramowania może symulować instrukcje warunkowe, skoki i pętle/rekurencje
- Automat składa się ze zbioru stanów i reguł przejścia między nimi
	- stan - definiowany wartościami parametrów opisujących cały układ, można go porównać z położeniem zatrzymanego układu trybów w mechanizmie, stanu napięcia sprężyn, stanu wahadła 
	- reguły przejścia - określają, jak zmieniają się parametry aby dokonało się przejście z pewnego stanu do innego 

##### Automat skończony
- Automat skończony zawiera skończoną liczbę stanów, w odróżnieniu od automatów nieskończonych, które są nieograniczone
- Przykład wyłącznika światła:![[Pasted image 20240630130414.png]]
- zapalone i zgaszone to stany przełącznika
- przejście między nimi następuje poprzez zaistnienie sytuacji "naciśnij"
- ta sytuacja jest odczytywana z wejścia automatu (nie zaznaczonego na rysunku), czyli automat odczytuje, analizuje i reaguje na dane wejściowe

#####  Podstawowe definicje
- Alfabet - skończony, niepusty zbiór symboli
- Słowo - ciąg symboli wybranych z pewnego alfabetu
	- istnieje specjalne słowo, łańcuch pusty, który należy do każdego alfabetu
- Język to zbiór wszystkich słów podlegających pewnej regule, jakie można ułożyć z danego alfabetu

###### Przykładowe alfabety
- Σ={0,1,2,3,4,5,6,7,8,9}Σ={0,1,2,3,4,5,6,7,8,9}﻿ ← dziesiętny
- Σ={0,1}Σ={0,1}﻿ ← binarny
- Σ={𝑎,𝑏,...,𝑧}Σ={a,b,...,z}﻿ ← małe litery
- Σ=𝐴𝑆𝐶𝐼𝐼Σ=ASCII﻿ ← znaki ASCII

###### Przykładowe słowa w alfabecie binarnym
- ε,0,1,00,01,10,11,000,001,010,011,100,101,110,111,...

Wprowadza się potęgi alfabetu, oznaczające wybór słów pewnej długości