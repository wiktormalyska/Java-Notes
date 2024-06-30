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
- Słowo - ciąg symboli wybranych z pewnego 