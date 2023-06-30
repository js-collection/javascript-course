# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 03

#### Introduzione alle funzioni

Le "function" è il primo concetto da apprendere nell'informatica. Seppur di origine algebrica, il nome suggerisce da subito che si tratta di un costrutto per realizzare delle "funzionalità", l'esecuzione di istruzioni in un pacchetto che può essere richiamato all'occorrenza.<br>
Di base, la dichiarazione di una funzione avviene in questo modo:

```js
TIPO-FUNZIONE NOME-DELLA-FUNZIONE () {
    // COSE DA FARE...
}

// ovvero:

function nameOfMyFunc () {
  // Operations ...
}

// si può chiamare tramite il nome stesso:

nameOfMyFunc ()
```

Esistono diversi tipi di funzioni, le vedremo in seguito, per ora ci basta spare che richiamandone il nome è possibile avviarle e che le parentesi tonde servono sia a definirle che a passare ulteriori "dati", le cosidette "variabili"

```js
IL-MIO-DATO-ESTERNO

TIPO-FUNZIONE NOME-DELLA-FUNZIONE (IL-MIO-DATO-ESTERNO) {
    // COSE DA FARE, ANCHE CON IL-MIO-DATO-ESTERNO...
}
```

---

#### Le Variabili (Const, Var, Let)

Abbiamo visto che è possibile definire e passare "dati" tra le funzionalità di un programma citando il termine "variabile", ma cos'è una variabile per l'esattezza?<br>
Le variabili sono il principale modo per salvare ed elaborare dati in un programma o, per meglio dire, sono i "contenitori" in cui il dato viene stivato per essere poi manipolato.
Difatti, ogni variabile ha un indirizzo di memoria associato, che rappresenta la sua posizione nella memoria del computer. Quando una variabile viene dichiarata, viene riservato uno spazio nella memoria per memorizzarne il valore.
Ecco come va dichiarata una variabile

```js
TIPO-DI-VARIABILE NOME-DI-RIFERIMENTO-IN-MEMORIA = VALORE

// esempio:

var nomeAnimale = 'Drago'
```

I tre tipi di variabile in javascript sono: "CONST", "VAR" e "LET". Questi tre modelli hanno delle caratteristiche specifiche sulla loro "reperibilità" e modifica all'interno del programma.

- La *const*:<br>
è una variabile che non è variabile... ovvero che non può essere modificata, sia per tipo che per contenuto, durante l'esecuzione del programma.<br>Se volessimo dunque trasformare in una scritta un numero non sarà possibile.<br>Le constant sono ottime per un uso "globale".
- La *var*:<br>
è la variabile originaria, come la constant è ottima per un uso globale, può dunque passare tra diverse parti del programma e può assumere ogni sorta di cambiamento di tipo. E' possibile quindi riassegnarla e darle nuove tiplogie.
- La *let*:<br>
identica a var ha la particolarità di non passare oltre a dove viene dichiarata rimanendo utile esclusivamente allo "scopo di esecuzione".

```js

const numeroDiAnimali = 3
var nomeAnimali = 'Draghi'

// dunque:

function stampaNome () {
  nomeAnimali = 'coccodrilli'
  console.log('abbiamo',nomeroDiAnimali,nomeAnimale,'in cucina!')
}

// abbiamo 3 coccodrilli in cucina!
```

Nell'esempio precedente vediamo che una "funzione" (una "funzionalità"), defisce una stringa (un testo) cambiando il nome dell'animale da _Draghi_ a _Coccodrilli_. Questo è possibile solo per Var e Let, le Const non possono farlo. E' da notare che le Const non possono nemmeno cambiare il loro "tipo", dunque, in questo caso, essendo un numero non potranno essere riassegnate come stringa di testo.
Se provassimo a fare:

```js
const numeroDiAnimali = 3

function cambiaInTesto () {
  numeroDiAnimali = '3'
}
```

Andremmo incontro ad un errore.
Seguendo gli errori possibili evidenziamo il limite, invece, di tutte le variabili: Non poter risalire dallo scopo... cioè dalla posizione in cui vengono assegnate:

```js
function cambiaInTesto () {
  const numeroDiAnimali = '3'
}

console.log(numeroDiAnimali)
```

Questa esecuzione darebbe un errore perchè la variabile è dentro una funzione e non può dunque essere letta dal console.log, che è fuori.
In un modo analogo funzionano le variabili di tipo "let", che hanno la particolarità di essere univoce per il solo scopo in uso... Facciamo un esempio:

```js
const numeroDiAnimali = '2'
let nomeAnimale = 'Drago'

function esempio_1 (){
  let nomeAnimale = 'Papera'
  const numeroDiAnimali = '3'
}

function esempio_2 (){
  let nomeAnimale = 'Coccodrillo'
  const numeroDiAnimali = '5'
}
```

Nel costrutto precedente avverrà un errore dovuto alle const che, come le var, non posso essere riassegnate con lo stesso nome. Le constant, in più, non possono essere nemmeno modificate per tipo e contenuto. Diffrentemente, le let, possono essere riassegnate in ogni modo purchè con scopo diverso come se, per ogni contesto, fosse una differente allocazione di memoria pur avendo lo stesso nome.

Infine, le variabili tutte possono anche essere e contentere delle funzioni... con altre variabilie così via...

```js

LA-MIA-VARIABILE-E'-ORA-UNA = FUNZIONALITA' () {
  // Cose da fare...
}

// ossia:

const myFunctionality = function () {
  // Do...
}

```

---

#### Altri tipi di dati
