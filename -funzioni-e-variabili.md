# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 03

#### Introduzione alle funzioni

Le "function" è il primo concetto da apprendere nell'informatica. Seppur di origine algebrica, il nome suggerisce da subito che si tratta di un costrutto per realizzare delle "funzionalità", l'esecuzione di istruzioni in un pacchetto che può essere richiamato all'occorrenza.<br>
Di base, la dichiarazione di una funzione avviene in questo modo:

```js
FUNZIONE NOME-DELLA-FUNZIONE () {
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

FUNZIONE NOME-DELLA-FUNZIONE (IL-MIO-DATO-ESTERNO) {
    // COSE DA FARE, ANCHE CON IL-MIO-DATO-ESTERNO...
}
```

La funzione serve quindi ad elaborare i dati che possono essere definiti e tornare in deverse forme.<br> Al di la della definizione di un dato, che vedremo nel prossimo step, i concetti di ritorno di base in una  funzione javascript sono due: il *return* e la *callback*:

```js
IL-MIO-DATO-ESTERNO

FUNZIONE NOME-DELLA-FUNZIONE (IL-MIO-DATO-ESTERNO) {
    // COSE DA FARE, ANCHE CON IL-MIO-DATO-ESTERNO...

    "TORNA" IL-MIO-DATO-MODIFICATO
}

// alla pratica:

a = 3
b = 5
function somma () {
  return a+b
}

console.log(somma(a,b))

// somma torna un risultato che sarà il numero 8
```
Senza il return non potremmo vere il valore 8, tornerebbe "undefined" ossia "non definibile".<br>

E' anche possibile attendere il risultato per utilizzarlo a cascata, annidando una funzione dentro l'altra, il concetto è detto "callback"

```js
a = 3
b = 5
x = 2
function somma (a,b,callback) {
  return callback(a+b)
}

console.log( 
  somma( a,b, function sottrai_2(r){ 
    return r-2 
  })
)
```

Nell'esempio sopra abbiamo annidato una funzione che attende l'esecuzione della precedente e ne utilizza il risultato.<br>
Esistono concetti più avanzati per le funzioni? La risposta è "SI", ma li vedremo più avanti.

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

I tre tipi di variabile in javascript sono: "CONST", "VAR" e "LET". Questi tre modelli hanno delle peculiarità sull'eventuale modifica all'interno del programma.

- La *var*:<br>
è la variabile originaria, assume ogni sorta di cambiamento di tipo e valore. E' possibile quindi riassegnarla e darle nuove tiplogie.
- La *let*:<br>
identica ed erede moderna di var.
- La *const*:<br>
è un'allocazione di memoria che non non può essere modificata nel suo "tipo" e non può essere riassegnata se nello stesso scopo

```js
// non possibile:

const test = "ciao Giulio!"
test = "ciao Marzio!" // errore!

// invece con var e let:

let test = "ciao Giulio!"
test = "ciao Marzio!"
console.log("test",test) // "test_2 ciao Marzio!"

```

Un esempio più complesso:

```js

var nomeAnimale = 'Draghi'
const numeroDiAnimali = 3

function stampaLog () {
  //numeroDiAnimali = numeroDiAnimali+'3'  // Error: Cannot assign to "numeroDiAnimali" because it is a constant
  nomeAnimale = 'coccodrilli'
  console.log('abbiamo',numeroDiAnimali,nomeAnimale,'in cucina!')
}

stampaLog()
// abbiamo 3 coccodrilli in cucina!
```

La funzione definisce una stringa (un testo) che cambia da _Draghi_ a _Coccodrilli_. Questo è possibile solo per var e let, le const non possono farlo perchè, appunto, "costanti".
L'altra cosa da notare è che, fintanto che non verrà definito nessun elemento dentro le parentesi tonde, le variabili passeranno alle funzioni di livello più basso, in alternativa la funzione farà uso e farà passare solo le variabili con lo stesso nome espresso nelle parentesi stesse.<br>
Se definiamo quindi una variabile potrà questa essere recuperata dalla funzione sullo stesso livello di annidamento e nelle sue sottofuzioni (il concetto prende il nome di ereditarietà, inhiterance) ma è da comprendere che non sarà possibile che avvenga il contrario (il limite è detto hoisting, elevazione) perchè quel preciso dato ancora non esiste. Sottolineaiamo che <i>tutti i dati non possono risalire dallo scopo... cioè dalla posizione in cui vengono creati</i>:

```js
function cambiaInTesto () {
  const numeroDiAnimali = '3'
}

console.log(numeroDiAnimali)
```

Questa esecuzione darebbe un errore (o meglio un "null", "inseistente") perchè la variabile è dentro una funzione e non può dunque essere letta dal console.log, che è fuori.
Esclusi specifici casi, le variabili sono  univoce per il solo scopo in uso e se ridichiarate verranno prese in considerazione per il nuovo contesto come nuova variabile.

```js
var coloreAnimale = 'grigio'
const numeroDiAnimali = '2'
let nomeAnimale = 'Drago'

function esempio_1 (){
  var coloreAnimale = 'blue' 
  const numeroDiAnimali = '3'
  let nomeAnimale = 'Papera'
  return [coloreAnimale,numeroDiAnimali,nomeAnimale]
}

function esempio_2 (){
  var coloreAnimale = 'rosso' 
  const numeroDiAnimali = '5'
  let nomeAnimale = 'Coccodrillo'
  return [coloreAnimale,numeroDiAnimali,nomeAnimale]
}

console.log(
  coloreAnimale,numeroDiAnimali,nomeAnimale,
  esempio_1 (),
  esempio_2 ()
)

// "grigio"
// "2"
// "Drago"
// ["blue","3", "Papera"]
// ["rosso","5", "Coccodrillo"]
```

Tutte le variabili possono essere riassegnate in ogni modo purchè con scopo diverso come se, per ogni contesto, fosse una differente allocazione di memoria pur avendo lo stesso nome.

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

Abbiamo visto che le variabili possono contenere dati e abbiamo citato spesso il termine "Tipo"... ma cos'è?
Il "tipo" è il modello che viene applicato al dato dalla macchina.
I tipi di base da dover conoscere in js sono:
- *le funzioni*;<br>Rappresentano un blocco di codice riutilizzabile che può essere chiamato per eseguire determinate azioni
- *I numeri*;<br>Tutti i numeri, inclusi numeri interi e numeri decimali.
- *Le stringe*;<br>Ovveri i caratteri, i testi, intesi come "elenco di caratteri", difatti una stringa è un array
- *Gli array*;<br>Elenchi (come le stringhe) di dati
- *Booleano*;<br> Il True/False, il Vero e Falso
- *L'Oggetto*;<br> Una collezione di dati organizzata contenente altri dati e funzioni

ed i due elenti per definire quando il dato è:<br>

- *null*;<br>il dato, semplicemente, non esiste o non è recuperabile in alcun modo
- *undefined*;<br>il dato esiste ma non è possibile definirlo in alcun modo

esistono altri tipi di dati validi per corsi più avanzati come: Date, RegExp, symbol nonchè il concetto di prototype.<br>
Per ragioni di mera esperienza si consiglia lo studio di quest'ultime in un contesto più avanzato. 

Nella prossima lezione impareremo ad usare ad usare array e stringhe, manipolandoli.
