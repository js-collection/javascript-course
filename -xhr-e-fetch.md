# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04


#### Js, definizione di Asincronismo

Il concetto di asincronismo in JavaScript si riferisce alla capacità del linguaggio di eseguire operazioni in modo non bloccante. Di solito, le operazioni asincrone coinvolgono l'interazione con il server, l'accesso al filesystem, il recupero di dati da un database o l'esecuzione di operazioni intensive che richiedono tempo.

In JavaScript, le operazioni asincrone sono implementate utilizzando callback nelle chiamate xhr e fetch, le promesse o le più recenti async/await. Questi meccanismi consentono di avviare un'operazione asincrona e specificare cosa fare quando l'operazione è completata o se si verifica un errore.

un esempio di systema asyncrono:

```js

// Simuliamo un'attesa per ottenere un nome, facciamolo definendo una "promise"...
function getUser() {
  return new Promise((resolve, reject) => {
    setTimeout( () => resolve('John Doe'), 2000) // Simuliamo un ritardo di 2 secondi nella richiesta
  })
}

// TEST1: Funzione asincrona che utilizza async/await per ottenere il nome di un utente
async function getUsername() {
  try {
    const user = await getUser()
    console.log(user.name)
  } catch (error) {
    console.error('Si è verificato un errore:', error)
  }
}

// TEST2: Funzione asincrona che utilizza una promise per ottenere il nome di un utente
function getUsername() {
  getUser()
    .then( user => {
      console.log(user.name);
    })
    .catch( error => {
      console.error('Si è verificato un errore:', error);
    });
}

//... eseguire uno dei due test
getUsername()

```
Non è semplice afferrare il concetto e lavorare su questi argomenti, normalmente molto più vicini ad utenti di maggiore esperienza... Tutto il materiale è a scopo di visione didattica e serve a far comprendere il "dinamismo" di una chiamata ed il suo concetto di attesa, di asincronismo.

#### Le chiamate XHR

L'XMLHttpRequest è un oggetto JavaScript che consente di effettuare richieste HTTP asincrone verso un server. È stato tradizionalmente utilizzato per l'interazione asincrona con il server e per il recupero di dati senza dover ricaricare l'intera pagina web.

Ecco un esempio di base per effettuare una chiamata XHR:

```js
// Creazione di un'istanza di XMLHttpRequest
var xhr = new XMLHttpRequest();

// Definizione della funzione di gestione dell'evento di completamento della richiesta
xhr.onload = function() {
  if (xhr.status === 200) {
    // Richiesta completata con successo
    console.log(xhr.responseText);
  } else {
    // Si è verificato un errore durante la richiesta
    console.error('Si è verificato un errore:', xhr.status);
  }
};

// Definizione della funzione di gestione dell'evento di errore della richiesta
xhr.onerror = function() {
  console.error('Si è verificato un errore durante la richiesta.');
};

// Configurazione della richiesta
xhr.open('GET', 'URL_DEL_SERVER', true);

// Invio della richiesta
xhr.send();
```

Se l XHR è quello più conosciuto, il metodo più è però il Fetch...


#### Le chiamate FETCH

Fetch è un'API JavaScript moderna per effettuare richieste HTTP. È progettato per essere più semplice e flessibile rispetto a XHR.

Ecco un esempio di base per effettuare una chiamata Fetch:

```js
// Effettuare una richiesta GET
fetch('URL_DEL_SERVER')
  .then(function(response) {
    if (response.ok) {
      // Risposta ricevuta con successo
      return response.text()
    } else {
      // Si è verificato un errore durante la richiesta
      throw new Error('Si è verificato un errore: ' + response.status)
    }
  })
  .then(function(data) {
    // Elaborare i dati ricevuti
    console.log(data)
  })
  .catch(function(error) {
    console.error('Si è verificato un errore durante la richiesta:', error)
  })
```

È importante notare che Fetch è supportato solo dai browser più recenti, mentre XHR è supportato da quasi tutti i browser. Pertanto, se devi supportare browser più vecchi, potresti dover utilizzare XHR come alternativa.
