- wykorzystywane w zadaniach dopasowania i rozpoznawania łańcuchów, m.in. w wyszukiwarkach, parserach, analizatorach treści
- technicznie, wyrażenie regularne jest przez aplikację zamieniane na odpowiedni automat
- prowadzi to do słusznego podejrzenia, że automaty RE nawet jeśli nie są sobie równoważne, to mają wiele wspólnego
- konkretne symbole używane do budowania RE różnią się pomiędzy aplikacjami i systemami, ale podstawowe zasady są niezmienne

##### Na językach można wykonywać trzy podstawowe operacje
- suma - definiuje się jako sumę zbiorów łańcuchów należących do obu języków
- konkatenacja - definiuje się jako zbiór łańcuchów utworzonych jako konkatenacje łańcuchów należących do obu języków
- domknięcie - zdefiniowane jako suma łańcuchów należących  do kolejnych konkatenacji języka z samym sobą

#### Definicja: algebra RE
- 