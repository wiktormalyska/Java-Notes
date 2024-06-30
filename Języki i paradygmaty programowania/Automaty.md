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
- $Σ={0,1,2,3,4,5,6,7,8,9}Σ={0,1,2,3,4,5,6,7,8,9}﻿ ← dziesiętny$
- $Σ={0,1}Σ={0,1}﻿ ← binarny$
- $Σ={𝑎,𝑏,...,𝑧}Σ={a,b,...,z}﻿ ← małe litery$
- $Σ=𝐴𝑆𝐶𝐼𝐼Σ=ASCII﻿ ← znaki ASCII$

###### Przykładowe słowa w alfabecie binarnym
- ε,0,1,00,01,10,11,000,001,010,011,100,101,110,111,...

Wprowadza się potęgi alfabetu, oznaczające wybór słów pewnej długości
$$Σ0={ε}$$
$$Σ1={w:∣w∣=1}=Σ$$
$$Σ2={w:∣w∣=2}=ΣΣ$$
$$Σ+=Σ1∪Σ2∪...$$
$$Σ∗=i=0⋃∞​Σi=Σ0∪Σ1∪Σ2∪...=$$

##### Język
- Językiem nad alfabetem nazywamy każde znaki znajdujące się w słowniku
- nie musi wykorzystywać wszystkich symboli alfabetu, dlatego jest językiem nad alfabetem
- zbiór pusty jest językiem nad dowolnym alfabetem
- język ze słowem pustym również jest językiem nad dowolnym alfabetem
- język nie musi być skończony

#### Automat deterministyczny
- przejścia między stanami są dokładnie określone
- dla danego wejścia istnieje dokładnie jeden stan wyjściowy

#### Automat niedeterministyczny
- w danych warunkach istnieją przejścia do kilku stanów wyjściowych jednocześnie. automat taki może znajdować się w kilku stanach jednocześnie

#### Definicje
- ##### Deterministyczny automat skończony (DAS)
	- DAS to skończony automat, deterministyczny, zdefiniowany, gdzie
	- Q - zbiór stanów
	- Σ - zbiór symboli wejściowych (alfabet)
	- 𝛿 - funkcje przejścia między stanami
	- 𝑞0∈𝑄 - stan początkowy
	- 𝐹⊂𝑄 - zbiór stanów akceptujących
	- ![[Pasted image 20240630134134.png]]$$𝑄={𝑞0,𝑞1}Q={q0​,q1​}$$$$Σ={𝑛}Σ={n}$$$$𝛿(𝑞0,𝑛)=𝑞1, 𝛿(𝑞1,𝑛)=𝑞0δ(q0​,n)=q1​, δ(q1​,n)=q0$$$$𝐹={𝑞1}F={q1​}$$
	- ![[Pasted image 20240630134302.png]]
	-   “→” oznacza stan wejściowy, zaś “*” stany akceptowane
	- Mamy 3 równoważne zapisy definiujące DAS
		- zapis "piątkowy"
		- diagram
		- tabela
	- Przykład:
		- Automat DAS rozpoznający w tekście ciąg UMCS (ciąg liter)
		- Alfabetem jest alfabet polski + znaki interpunkcyjne
		- ![[Pasted image 20240630150511.png]]
		- Gdyby DAS miał rozpoznawać wyraz “UMCS” to należałoby zacząć szukać dopasowania do znaku spacji, a zakończyć na znaku spacji lub znaku przestankowym.
		- Definicje stanów:
			- 𝑞0q0​﻿ → nie przeczytałem niczego interesujące
			- 𝑞1q1​﻿ → przeczytałem U
			- 𝑞2q2​﻿ → przeczytałem UM
			- 𝑞3q3​﻿ → przeczytałem UMC
			- 𝑞4q4​﻿ → przeczytałem UMCS

#### Rysowanie diagramów (umowa)
##### Reguły rysowania diagramów definiujących DAS
- każdemu stanowi Q odpowiada jeden wierzchołek, są podpisane oznaczeniem stanu i rysujemy je w postaci kółka
- na stan wejściowy wskazuje strzałka z napisem START
- stany akceptujące oznaczone są podwójnym kółkiem
- jeśli istnieje funkcja przejścia to stan łączymy strzałką ze stanem, a strzałkę podpisujemy symbolem s
- dla każdego stanu muszą istnieć funkcje dla każdego symbolu używanego alfabetu
- fragment diagramu, do których nie można się dostać ze stanu początkowego, są z niego usuwane

#### Rozszerzona funkcja przejścia
- Niekiedy wygodnie jest określić funkcję przejścia od łańcucha a nie pojedynczego symbolu
- ##### Rozszerzona funkcja przejścia DAS
	- Rozszerzona funkcja przejścia zdefiniowana jest rekurencyjnie tak, że
		- jeśli m jest łańcuchem składającym się z łańcucha i symbolu
		- oraz jeśli DAS będący w stanie q po przetworzeniu łańcucha l znajduje się w stanie p
		- to:
			- $$δ^(q,ε)=q$$
			- $$δ^(q,m)=δ(p,x)=δ(δ^(q,l),x)$$
##### Rozszerzona funkcja przejścia a języki
- rozszerzone funkcje przejścia mogą posłużyć do zdefiniowania języka DAS
##### Język DAS
- nazywamy zbiór łańcuchów przeprowadzających stan początkowy automatu A w jeden z jego stanów akceptujących

##### Język regularny
- język jest regularny jeśli jest językiem pewnego DAS


#### Niedeterministyczny Automat Skończony (NAS)
- NAS to automat skończony, niedeterministyczny, gdzie
	- Q - skończony zbiór stanów
	- Σ - skończony zbiór symboli wejściowych (alfabet)
	- 𝛿 - funkcje przejścia między stanami
	- 𝑞0∈𝑄 - stan początkowy
	- 𝐹⊂𝑄 - zbiór stanów akceptujących
- Jedyna różnica w definicjach DAS i NAS to postać funkcj