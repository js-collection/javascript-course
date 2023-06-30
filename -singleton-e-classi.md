# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### I singleton

Un singleton è un pattern di progettazione che permette di creare una sola istanza, ossia un "copia fantasma" di un costrutto con delle specifiche proprietà.
In JavaScript, il singleton non è particolarmente apprezzato perchè considerato "poco elegante" considerando che js è un linguaggio basato sugli oggetti e funzioni stessi, il che significa che l'uso di quest'ultimi già fornisce un'alternativa più semplice.
In alcuni casi è però una forma semplice da applicare e vale la pena studiarla anche come semplice anticipazione alle classi qualora si è a conoscenza di funzioni e oggetti.

Un singleton è:

```js
const Singleton = {
  // Metodi e proprietà del singleton
}

const singletonInstance1 = Singleton
const singletonInstance2 = Singleton

console.log(singletonInstance1 === singletonInstance2); // Output: true

// o, più realistico:

const singleton = {
	proprieta: "abc",
	metodo: function() {
		// ...
	}
}
singleton.metodo()
```

In sintesi abbiamo definito un'allocazione della memoria dove esistono delle proprietà e metodi per poterle lavorare.
Quando si utilizza il singleton, basta fare riferimento all'oggetto Singleton direttamente. In questo caso, singletonInstance1 e singletonInstance2 fanno riferimento allo stesso oggetto, quindi il confronto tra di loro restituirà true.

Diventando facilemente una struttura complessa e non "eplicita", il singleton è una soluzione vista di cattivo occhio dalla maggior parte degli sviluppatori. Se si necessita di oggetti e funzionalità pacchettizzate è bene imparare l'uso delle classi.

#### Le Classi e le istanze

Una *classe rappresenta un modello o un'astrazione di un oggetto nel mondo reale.
Le classi consentono di definire proprietà e comportamenti che gli oggetti dovrebbero avere.
In JavaScript, le classi possono essere utilizzate per creare molteplici istanze di oggetti con le stesse caratteristiche e metodi, ma viariate nei valori in base alla necessità.

Faccimo un sempio: Creiamo una classe "Persona" per rappresentare le persone con nome, età e modo, un "metodo" per presentarsi.

```js
// Definizione della classe "Persona"
class Persona {
  constructor(nome, eta) {
    this.nome = nome
    this.eta = eta
  }

  presentati() {
    console.log(`Ciao, sono ${this.nome} e ho ${this.eta} anni.`)
  }
}


// Creazione di istanze della classe "Persona"
const persona1 = new Persona("Mario", 25)
const persona2 = new Persona("Luigi", 30)

// Utilizzo dei metodi dell'istanza
persona1.presentati() // Output: Ciao, sono Mario e ho 25 anni.
persona2.presentati() // Output: Ciao, sono Luigi e ho 30 anni.
```

Abbimo quindi istruito il computer a definire questo "schema" d poter replicare chiamato "Persona", e dentro abbiamo inserto il costruttore dello schema per definire le proprietà "nome" ed "eta".
Quando "istanziamo" Persona stiamno letteralmente costruendo ogni volta un nuovo prodotto di quello schema, come fosse un clone, una copia fantasma, che prende però le caratteristiche assegnategli in fase di lancio.
Tra le caratteristiche abbiamo anche un comportamento predefinito, una funzione che stampa in video le caratteristiche dell'istanza stessa.

La cosa carina è che è possibile usufruire dei dati stessi delle classi per creare costrutti estremamente complessi che restituiscono oggetti e dati in base alle proprie stesse impostazioni.
Supponiamo di voler definire intrinsecamente un nuovo nome e una nuova eta:

```js
class Persona {

  constructor(nome, eta) {
    this._nome = nome
  }

  get nome() {
    return this._nome
  }

  set nome(nuovoNome) {
    this._nome = nuovoNome
  }

  presentati() {
    console.log(`Ciao, sono ${this._nome}`)
  }
}

const persona1 = new Persona("Mario")

console.log(persona1.nome) // Output: Mario

persona1.nome = "Luigi"

console.log(persona1.nome) // Output: Luigi

persona1.presentati() // Output: Ciao, sono Luigi
```

Come abbiamo notato, in questo modo, abbiamo ridefinito "runtime" le proprietà di Mario, diventato Luigi. E' possibile costruire ogni tipo di funzione, anche automatica all'istanziarsi della classe stessa:


```js
class Persona {
  constructor(nome, eta) {
    this._nome = nome
    this.presentati()
  }
  presentati() {
    console.log(`Ciao, sono ${this._nome}`)
  }
}

const persona1 = new Persona("Mario")
// Ciao, sono Mario

```

Alla creazione dell'istanza verrà inserito un nome e automaticamente lanciata la funzione interna "presentati" (la quale, come abbiamo fatto prima, potrebbe costruire e modificare altro, rendendo il sistema un approccio per semi-automatizzato)
