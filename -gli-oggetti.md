# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### Gli Oggetti informatici in Javascript

Gli oggetti in JavaScript sono strutture dati che consentono di organizzare e memorizzare dati correlati. Un oggetto è costituito da una raccolta di coppie chiave-valore, in cui la chiave è una stringa (o simile a una stringa) che identifica univocamente il valore associato ad essa. Questo rende gli oggetti molto flessibili e adatti per rappresentare concetti complessi.

Immagina un oggetto come una scatola con diversi scomparti, dove ogni scomparto contiene un valore specifico. Ogni scomparto è identificato da una chiave univoca che consente di accedere al valore corrispondente. Questo è ciò che rende gli oggetti potenti: puoi accedere ai dati in modo più descrittivo e organizzato rispetto ad un semplice array.

Ecco un esempio didattico che rappresenta un oggetto "persona":

```js
const person = {
  name: 'John',
  age: 30,
  profession: 'Developer',
};

console.log(person.name); // Output: 'John'
console.log(person.age); // Output: 30
console.log(person.profession); // Output: 'Developer'
```

In questo esempio, l'oggetto person ha tre proprietà: name, age e profession. Ogni proprietà è una coppia chiave-valore, dove la chiave rappresenta il nome della proprietà e il valore rappresenta il dato associato. Puoi accedere ai valori delle proprietà utilizzando la sintassi "nomeOggetto.nomeProprietà".

Puoi anche aggiungere nuove proprietà o modificare quelle esistenti. Ecco un esempio:

```js
person.gender = 'Male';
person.age = 31;

console.log(person.gender); // Output: 'Male'
console.log(person.age); // Output: 31
```

Puoi anche utilizzare valori di diversi tipi come proprietà degli oggetti, compresi array, funzioni e altri oggetti. Questa flessibilità rende gli oggetti uno strumento potente per rappresentare dati complessi.
```js
const car = {
  brand: 'Tesla',
  model: 'Model 3',
  colors: ['red', 'white', 'blue'],
  startEngine: function() {
    console.log('Engine started!');
  },
  owner: {
    name: 'Alice',
    age: 35
  }
};

console.log(car.colors[0]); // Output: 'red'
car.startEngine(); // Output: 'Engine started!'
console.log(car.owner.name); // Output: 'Alice'
```

In questo esempio, l'oggetto car ha proprietà di diversi tipi, come una proprietà di tipo array (colors), una proprietà di tipo funzione (startEngine) e una proprietà di tipo oggetto (owner). Puoi accedere ai valori delle proprietà annidate utilizzando la stessa sintassi di accesso: "nomeOggetto.nomeProprietà.nomeProprietà".

Gli oggetti in JavaScript sono molto versatili e consentono di organizzare e manipolare dati in modo efficace. Sono ampiamente utilizzati per rappresentare entità complesse e consentono di scrivere codice più leggibile ed esplicativo.
