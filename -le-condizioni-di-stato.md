# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### La condizione di stato IF-ELSE

L'istruzione if-else consente di eseguire un blocco di codice se una condizione è vera e un blocco di codice alternativo se la condizione è falsa. Di seguito troverai la struttura generale di un'istruzione if-else:

```js
if (condizione) {
  // blocco di codice se la condizione è vera
} else {
  // blocco di codice se la condizione è falsa
}
```
Supponiamo di voler verificare se un numero è positivo o negativo e visualizzare un messaggio appropriato
```js
numero = -5

if (numero > 0) {
  console.log("Il numero è positivo, puoi proseguire")
} else {
  console.log("Il numero è negativo. Fine dei giochi!")
}
```

In questo esempio, se numero è maggiore di 0, verrà visualizzato il messaggio "Il numero è positivo." Altrimenti, se numero non è maggiore di 0 (ovvero è minore o uguale a 0), verrà visualizzato il messaggio "Il numero è negativo.".

Ovviamente i casi reali sono più complessi e posso concatenarsi tramite gli <b>operatori logici</b> più complessi del semplice "maggiore". Facciamo un esempio che comprenda una soddisfacente quantità di possibilità:

```js
numero = 3
nome = 'Mario'
eta = 18 
rangeMin = -5
rangeMax = 5

if (numero >= rangeMin && numero <= raangeMx) {

  console.log("Il numero è positivo, ma sei davvero Mario?");

  if (name == 'Mario' && age >== 18 ) {

    console.log("Ciao Mario!!");

  } else {

    console.log("no! Non sei Mario!");

  }

} else {

  console.log("Il numero è negativo. Fine dei giochi!");

}
```

Come da esempio abbiamo contollato se un numero corrispondesse ad un range "minimo e massimo", che un nome corrisponda poi effettivamente a "Mario" e che un'età sia tanto maggiore a 18, quanto prettamente di tipo numero.

Ovviamente lo statement IF-ELSE, in alcuni casi, non è la migliore soluzione...

---

#### La condizione di stato SWITCH-CASE

Immaginate un programma che in base ad un singolo parametro possa cambiare stato. Ebbene questa casistica non è rarissima nell'informatica e una delle più ordinate soluzioni è rappresentat dal "gemello ordinato" di IF-ELSE: lo SWITCH-CASE.

L'istruzione switch-case viene utilizzata per selezionare uno dei molti blocchi di codice da eseguire in base al valore di una variabile. È un'alternativa più compatta a una serie di istruzioni if-else. Di seguito troverai la struttura generale di un'istruzione switch-case:

```js
switch (espressione) {
  case valore1:
    // blocco di codice se espressione è uguale a valore1
    break
  case valore2:
    // blocco di codice se espressione è uguale a valore2
    break
  // altri casi...
  default:
    // blocco di codice se nessun caso corrisponde a espressione
}
```

Dove si applica tale costrutto con facilità? Per puro esempio didattico supponiamo di avere una chiamata di sistema ad un server dove chiediamo al nostro database qualcosa. Non è importante sapere adesso come si fa ma è importate sapere che il server ci restituirà, quasi sicuramente, una risposta in formato numerico, ad esempio: 200 se la chiamat è ok, 404 se il server non ha trovatto nulla, 500 se è capitato un errore ed altri, tanti, numeri, per definire lo stato della chiamata.
In base a tale stato vogliamo avviare un "meccanismo" che chiameremo "funzionalità" (function, lo vedremo poi) adatto. Ecco come sarebbe il costrutto:

```js
switch (serverResponse) {
  case 200:
    // do...
    break
  case 404:
    // do...
    break;
  case 500:
    // do...
    break
  // altri casi, ne sono davvero tanti...
  default:
    // do...
}
```

Sicuramente risulta molto più leggibile di un concatenamento infinito di IF-ELSE!

Un altro esempio ancora per capire meglio:

```js
numeroGiorno = 2
nomeGiorno

switch (numeroGiorno) {
  case 1:
    nomeGiorno = "Lunedì"
    break
  case 2:
    nomeGiorno = "Martedì"
    break
  case 3:
    nomeGiorno = "Mercoledì"
    break
  // altri casi per gli altri giorni della settimana...
  default:
    nomeGiorno = "Giorno non valido"
}
```

E' facile notare come sia limpida l'assegnazione del valore in base al diretto numero selezionato, magari, in una pagina web

---

#### La condizione di stato TRY-CATCH-FINALLY

Supponiamo che in uno dei ragionamenti computerizzati che abbiamo pensato possa accadere una falla. Un sistema potrebbe non funzionare e noi dobbiamo necessariamente avere un piano B, come fare?
E' la logica TRY-t-FINALLY, ossi: "prova" "cattura" "esegui", dove si intende:

```js
try {
  // Blocco di codice che potrebbe generare un'eccezione
} catch (errore) {
  // Blocco di codice eseguito se un'eccezione viene generata nel blocco try
} finally {
  // Blocco di codice eseguito sempre, indipendentemente dal fatto che un'eccezione sia stata generata o meno
}
```

Esempio: Supponiamo di voler dividere due numeri inseriti dall'utente e gestire il caso in cui l'utente inserisce uno 0 come secondo numero. Utilizzeremo il sistema try-catch-finally per gestire l'eccezione.

```js
numero1 = 10
numero2 = 0
risultato

try {
  risultato = numero1 / numero2
  console.log("Il risultato della divisione è:", risultato)
} catch (errore) {
  console.log("Si è verificato un errore durante la divisione:", errore.message)
} finally {
  console.log("Operazione di divisione completata.")
}
```

E' facile notare che questo è un meccanismo essenziale nello sviluppo moderno dove molte delle interazioni utente e dei parallelismi possono risultare incerti o instabili per loro stessa condizione iniziale.<br>
La gestione delle eccezioni con try-catch-finally è utile per prevenire l'interruzione del programma e per gestire gli errori in modo controllato, consentendo al codice di continuare l'esecuzione o di adottare azioni appropriate per gestire l'eccezione.

