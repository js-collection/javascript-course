# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 06

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

// in pratica:

let animali = ["mario","anna","paolo"]

for (let i; i<=animali.length; i++) {
  console.log('l\'animale è: ',animali[i]
}

// l'animale è: drago
// l'animale è: papera
// l'animale è: leone
```

L'inizializzazione viene eseguita una volta all'inizio del ciclo e solitamente viene utilizzata per dichiarare e inizializzare la variabile di controllo. La condizione viene valutata all'inizio di ogni iterazione e, se è vera, il blocco di codice viene eseguito. Dopo ogni iterazione, l'iterazione viene eseguita per modificare la variabile di controllo. Se la condizione diventa falsa, il ciclo termina.

Seguendo lo stesso concetto abbiamo anche il *FOR OF* ed il *FOR IN* dove l'index è direttamente sostituito dagli elementi del loop.<br>

Il ciclo FOR-OF è utilizzato per iterare sia array che oggetti, stringhe ecc. Itera sui valori dell'oggetto e non le loro proprietà:

```js
for (elemento *di un* lista) {
  // blocco di codice da eseguire
}

// dunque:

for (let value of myList) {
  // blocco di codice da eseguire
}

// in pratica:

let animali = ["drago","papera","leone"]

for (let nome of animali) {
  console.log('l\'animale è: ',nome)
}

// l'animale è: drago
// l'animale è: papera
// l'animale è: leone
```

Il ciclo FOR IN serve ad iterare le proprietà enumerabili di un oggetto (ad esempio le coppia chiave:valore).

```js
for (elemento-e/o-valore *contenuto in* oggetto-o-lista) {
  // blocco di codice da eseguire
}

// dunque:

for (const [key,value] in myObject) {
  // blocco di codice da eseguire
}

// in pratica:

let animale = {
  nome: 'Leone',
  tipo: 'Mammifero',
  habitat: 'Savana',
  dieta: 'Carnivoro'
};

for (let proprietà in animale) {
  console.log(proprietà + ': ' + animale[proprietà]);
}

// nome: Leone
// tipo: Mammifero
// habitat: Savana
// dieta: Carnivoro
```

Infine ciclo FOREACH, il must degli array e delle funzioni. Questo particolre costrutto esegue direttamente una funzione per ogni elemento dell'array:

```js
IL-MIO-ARRAY.CICLAMI-ED-ESEGUI ( FUNZIONE ( ELEMENTO-ESTRATTO ) {
  // blocco di codice da eseguire sull'elemento estratto
}

const numbers = [1, 2, 3];
numbers.forEach( function (number) {
  console.log(number); // Output: 1 2 3
});
```

Seguendo tali logiche troviamo il ciclo *WHILE*.<br>
Questo ciclo è usato per iterare elementi fintanto che la condizione risulta veritiera:

```js
while (condizione) {
  // blocco di codice da eseguire
}

// dunque

while (true) {
  // blocco di codice da eseguire
}

// in pratica

let animali = ['Leone', 'Tigre', 'Orso', 'Lupo'];
let indice = 0;

while (indice < animali.length) {
  console.log(animali[indice]);
  indice++;
}

//Leone
//Tigre
//Orso
//Lupo
```
*DO-WHILE*, invece, si preoccupa che sia eseguita almeno una volta l'operazione, e poi a seguire tutte le altre volte fintanto che la condizione risulti vera:

```js
do {
  // blocco di codice da eseguire
} while (condizione)

// dunque

do {
  // blocco di codice da eseguire
} while (true)

// alla pratica identico  while, ma verrà eseguita immediatamente l istruzione do.
```
