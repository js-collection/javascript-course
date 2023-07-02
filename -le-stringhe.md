# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### Le stringhe

In JavaScript, una stringa è considerata una sequenza di caratteri e può essere trattata come un array di caratteri. Ciò significa che puoi applicare molti dei metodi per gli array alle stringhe per manipolarle e ottenere risultati desiderati.<br>
I metodi built-in delle stringhe somigliano -e in alcuni casi sono gli stessi- a quelli degli array:

- **length**: Restituisce la lunghezza della stringa.
```js
const text = 'this is a string'
console.log(text.length)
// 16
```

- **toUpperCase()** e **toLowerCase()**: Restituisce una nuova stringa con tutti i caratteri convertiti in maiuscolo o minuscolo.
```js
const str = 'Hello World';
console.log(str.toUpperCase()); // Output: 'HELLO WORLD'
```

- **includes()**: Restituisce true o false se un elemento è incluso (o non) della stringa.
```js
const str = 'Hello World';
console.log(str.includes('Wor')); // Output: true
```

- **match()**: Restituisce true o false se un elemento è esattamente incluso nella stringa.
```js
const str = 'Hello World';
console.log(str.match(/everyone/g)); // Output: false
```

- **search()**: Restituisce l'index del carattere dentro una stringa.
```js
const str = 'Hello World';
console.log(str.search('Wo')); // Output: 6
```

- **charAt()**: Restituisce il carattere alla posizione specificata nella stringa.
```js
const str = 'Hello';
console.log(str.charAt(1)); // Output: 'e'
```

- **padStart(), padEnd()**: Aggiunge all'inizio o alla fine una serie di caratteri alla stringa.
```js
const str = 'Hello';
console.log(str.padEnd(" world!")); // Output: 'Hello world!'
```

- **concat()**: Concatena una o più stringhe.
```js
const str1 = 'Hello';
const str2 = 'World';
console.log(str1.concat(' ', str2)); // Output: 'Hello World'
```

- **startWith(), endWith()**: Restituisce il true o false se la posizione risulta corretta o non corretta.
```js
const str = 'Hello';
console.log(str.startWith('He')); // Output: true
```

- **indexOf()**: Restituisce l'indice della prima occorrenza di una sottostringa nella stringa, o -1 se non viene trovata.
```js
const str = 'Hello World';
console.log(str.indexOf('World')); // Output: 6
```

- **lastIndexOf()**: Restituisce l'indice dell'ultima occorrenza di una sottostringa nella stringa, o -1 se non viene trovata.
```js
const str = 'Hello World';
console.log(str.lastIndexOf('o')); // Output: 7
```

- **slice()**: Restituisce una porzione della stringa specificata dagli indici di inizio e fine.
```js
const str = 'Hello World';
console.log(str.slice(6, 11)); // Output: 'World'
```

- **substring()**: Restituisce una porzione della stringa specificata dagli indici di inizio e fine, simile al metodo slice(), ma non accetta indici negativi.
```js
const str = 'Hello World';
console.log(str.substring(6, 11)); // Output: 'World'
```

- **replace()** e **replaceAll()**: Restituisce una nuova stringa in cui una sottostringa o un'espressione regolare specificata viene sostituita con un'altra.
```js
const str = 'Hello World';
console.log(str.replace('World', 'Universe')); // Output: 'Hello Universe'
console.log(str.replace(/World/g, 'Universe')); // Output: 'Hello Universe' (meglio di replaceAll)

```

- **split()**: Suddivide la stringa in un array di sottostringhe utilizzando un separatore specificato.
```js
const str = 'Hello,World,Universe';
console.log(str.split(',')); // Output: ['Hello', 'World', 'Universe']
```

- **trim(), trimStart() , trimEnd()**: Rimuove gli spazi vuoti (o altri caratteri di spaziatura) dall'inizio e dalla fine della stringa.
```js
const str = '  Hello World  ';
console.log(str.trim()); // Output: 'Hello World'
```

- **repeat()**: Ripete per N volte la stringa
```js
const str = 'Hello! ';
console.log(str.repeat(3)); // Output: Hello! Hello! Hello! 
```

Le stringhe possono essere trattate come array di caratteri, ma ricorda che sono immutabili, il che significa che i metodi di modifica delle stringhe creano sempre nuove stringhe anziché modificarle direttamente.
