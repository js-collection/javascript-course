# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE X

#### I cicli FOR, WHILE e DO-WHILE

Ciclo *FOR*: Il ciclo for è ampiamente utilizzato per iterare su un blocco di codice un numero noto di volte.<br>È costituito da tre parti principali: l'inizializzazione, la condizione di continuazione e l'iterazione. La sintassi del ciclo for è la seguente:

```js
for (inizializzazione; condizione; iterazione) {
  // blocco di codice da eseguire
}

// dunque:

for (let index; index<=elments.length; index++) {
  // blocco di codice da eseguire
}
```

L'inizializzazione viene eseguita una volta all'inizio del ciclo e solitamente viene utilizzata per dichiarare e inizializzare la variabile di controllo. La condizione viene valutata all'inizio di ogni iterazione e, se è vera, il blocco di codice viene eseguito. Dopo ogni iterazione, l'iterazione viene eseguita per modificare la variabile di controllo. Se la condizione diventa falsa, il ciclo termina.

Seguendo lo stesso concetto abbiamo anche il *FOR IN* ed il *FOR OF* dove l'index è direttamente sostituito dagli elementi del loop.<br>

Nel primo caso:

```js
for (elemento *contenuto in* lista) {
  // blocco di codice da eseguire
}

// dunque:

for (let element in myArray) {
  // blocco di codice da eseguire
}
```

Nel secondo caso possiamo ciclre valori ed lementi di un oggetto informatico:

```js
for (elemento/valore *di un* oggetto/chiave) {
  // blocco di codice da eseguire
}

// dunque:

for (let value of myObject) {
  // blocco di codice da eseguire
}
```
