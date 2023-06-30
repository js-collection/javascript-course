# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### Gli Array di dati

Un array è una struttura dati in JavaScript che consente di memorizzare una collezione di elementi ordinati. Gli elementi all'interno di un array possono essere di qualsiasi tipo di dati, inclusi numeri, stringhe, oggetti, funzioni e altri array. Gli array sono ampiamente utilizzati per organizzare e gestire insiemi di dati correlati.

La prima proprietà degli array è il "length", ovvero la loro lunghezza, il conteggio in termini informatici che parte da 0 ed arriva al quantitativo di elementi presenti nel pacco di dati:

```js
const fruits = ['apple', 'banana', 'orange','kiwi']
console.log(fruits.length)
// 3 
```
<i>Ponete attenzione, non 4 ma... 3! Cioè 0,1,2,3!</i>

Il metodo più comune per lavorare l'index, cioè l'indice relativo alla lunghezza dell'array, è l'insieme di funzioni built-in abbinate:

- **indexOf()**: Restituisce l'indice della prima occorrenza di un elemento nell'array, o -1 se non viene trovato.
```js
const fruits = ['apple', 'banana', 'orange'];
const indexOfBanana = fruits.indexOf('banana');
console.log(indexOfBanana); // Output: 1
```

- **lastIndexOf()**: Restituisce l'indice dell'ultima occorrenza di un elemento nell'array, o -1 se non viene trovato.
```js
const fruits = ['apple', 'banana', 'orange', 'banana'];
const lastIndexOfBanana = fruits.lastIndexOf('banana');
console.log(lastIndexOfBanana); // Output: 3
```

- **findIndex()**: Restituisce l'indice del primo elemento dell'array che soddisfa una determinata condizione.
```js
const numbers = [1, 2, 3, 4, 5];
const foundIndex = numbers.findIndex((number) => number > 3);
console.log(foundIndex); // Output: 3
```


Esaminimo alcuni i metodi built-in principali per la lavorare degli array in JavaScript:

- **unshift()**: Aggiunge uno o più elementi all'inizio dell'array.
```js
const fruits = ['banana', 'orange'];
fruits.unshift('apple');
console.log(fruits); // Output: ['apple', 'banana', 'orange']
```

- **shift()**: Rimuove il primo elemento dall'array
```js
const fruits = ['apple', 'banana', 'orange'];
const shiftedFruit = fruits.shift();
console.log(shiftedFruit); // Output: 'apple'
console.log(fruits); // Output: ['banana', 'orange']
```

- **push()**: Aggiunge un elemento alla fine dell'array.
```js
const fruits = ['apple', 'banana'];
fruits.push('orange');
console.log(fruits); // Output: ['apple', 'banana', 'orange']
```

- **pop()**: Rimuove l'ultimo elemento dall'array.
```js
const fruits = ['apple', 'banana', 'orange'];
const removedFruit = fruits.pop();
console.log(removedFruit); // Output: 'orange'
console.log(fruits); // Output: ['apple', 'banana']
```

- **slice()**: Restituisce una copia superficiale di una porzione dell'array, specificata dagli indici di inizio e fine.
```js
const fruits = ['apple', 'banana', 'orange', 'grape', 'mango'];
const slicedArray = fruits.slice(1, 4);
console.log(slicedArray); // Output: ['banana', 'orange', 'grape']
```

- **splice()**:Modifica l'array rimuovendo, sostituendo o aggiungendo elementi in posizioni specifiche.
```js
const fruits = ['apple', 'banana', 'orange', 'grape'];
// Rimuove 1 elemento a partire dall'indice 2
fruits.splice(2, 1);
console.log(fruits); // Output: ['apple', 'banana', 'grape']

// Sostituisce 1 elemento a partire dall'indice 1 con 'mango'
fruits.splice(1, 1, 'mango');
console.log(fruits); // Output: ['apple', 'mango', 'grape']

// Aggiunge 'peach' e 'kiwi' a partire dall'indice 2
fruits.splice(2, 0, 'peach', 'kiwi');
console.log(fruits); // Output: ['apple', 'mango', 'peach', 'kiwi', 'grape']
```

- **join()**: Restituisce una stringa che rappresenta gli elementi dell'array concatenati con un separatore specificato.
```js
const fruits = ['apple', 'banana', 'orange'];
const joinedString = fruits.join(', ');
console.log(joinedString); // Output: 'apple, banana, orange'
```

- **concat()**: Combina due array in un nuovo array.
```js
const array1 = [1, 2];
const array2 = [3, 4];
const combinedArray = array1.concat(array2);
console.log(combinedArray); // Output: [1, 2, 3, 4]
```

- **map()**: Crea un nuovo array con i risultati dell'applicazione di una funzione a ogni elemento dell'array.
```js
const numbers = [1, 2, 3];
const doubledNumbers = numbers.map((number) => number * 2);
console.log(doubledNumbers); // Output: [2, 4, 6]
```

- **filter()**: Crea un nuovo array con gli elementi che soddisfano una determinata 
```js
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter((number) => number % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

- **find()**: Restituisce il primo elemento dell'array che soddisfa una determinata condizione.
```js
const numbers = [1, 2, 3, 4, 5];
const foundNumber = numbers.find((number) => number > 3);
console.log(foundNumber); // Output: 4
```

- **reduce()**: Applica una funzione riduttore a un accumulatore e a ogni elemento dell'array, restituendo un singolo valore.
```js
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((accumulator, number) => accumulator + number, 0);
console.log(sum); // Output: 15
```

- **reverse()**: Inverte l'ordine degli elementi nell'array.
```js
const numbers = [1, 2, 3, 4, 5];
numbers.reverse();
console.log(numbers); // Output: [5, 4, 3, 2, 1]
```

- **sort()**: Ordina gli elementi dell'array in ordine crescente (di default) o secondo una funzione di confronto specificata.
```js
const fruits = ['orange', 'apple', 'banana'];
fruits.sort();
console.log(fruits); // Output: ['apple', 'banana', 'orange']
```

- **includes()**: Verifica se un determinato elemento è presente nell'array, restituendo true o false.
```js
const numbers = [1, 2, 3, 4, 5];
const includesThree = numbers.includes(3);
console.log(includesThree); // Output: true
```
