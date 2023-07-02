# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### Il DOM e gli eventi

<b>Il DOM (Document Object Model):</b> Il DOM è una rappresentazione strutturata e gerarchica di un documento HTML o XML. Essa permette di manipolare e interagire con gli elementi di una pagina web utilizzando JavaScript. Il DOM rappresenta il documento come un albero di nodi, in cui ogni elemento, attributo e testo sono rappresentati da un nodo. Grazie al DOM, è possibile accedere e modificare dinamicamente gli elementi, gli attributi e il contenuto di una pagina web.

I manuali didattici del W3C (World Wide Web Consortium), disponibili all'indirizzo [https://w3c.github.io/](https://w3c.github.io/) e [https://www.w3.org/](https://www.w3.org/), contengono tutte le informazioni sui nodi disponibili. Il W3C è l'ente ufficiale che determina lo standard di qualità del web moderno e definisce [tutti i componenti HTML](https://w3c.github.io/elements-of-html/) e la loro validazione strutturale, che può essere verificata attraverso il [validatore ufficiale](https://validator.w3.org/#validate_by_input).

JavaScript può recuperare e manipolare la struttura, gli attributi e i valori di questi componenti direttamente in tempo reale durante l'esecuzione del codice, poiché è una parte integrante dell'ecosistema web. JavaScript è stato creato specificamente per manipolare i dati del DOM e il lato utente, ovvero l'HTML o qualsiasi altro markup per la struttura dei dati che fornisca le API adeguate.

Ecco un esempio di codice HTML che illustra l'idea del DOM:

```html
<!DOCTYPE html>

<html lang="it">

    <head>
        <title>Js: Un corso per dev!</title>
    </head>

    <body>

        <h1>Hello Mondo!</h1>
        <p>Questa è la mia prima pagina web!</p>

    </body>

</html>
```

Da notare che l'HTML non è un linguaggio di programmazione, ma un linguaggio di markup che definisce la struttura di un oggetto statico, simile ad altri oggetti informatici, ma scritto in un file che conserva la sua forma idealizzata in gruppi di contenitori. Se desideri abbellire l'output del codice HTML, esiste un linguaggio apposito chiamato CSS che permette di aggiungere elementi visivi. Puoi trovare maggiori dettagli su ogni proprietà CSS tramite il W3C: https://www.w3.org/Style/CSS/all-properties.en.html

Proviamo ad applicare il CSS alla pagina HTML precedente per modificarne l'aspetto:

```html
<!DOCTYPE html>

<html lang="it">

    <head>
        <title>Js: Un corso per dev!</title>
        <style>
            h1{
                color:blue;
                font-size: 22px;
                font-weight: bold;
            }
            p{
                color: teal;
                font-size: 15px;
            }
        </style>
    </head>

    <body>

        <h1>Hello Mondo!</h1>
        <p>Questa è la mia prima pagina web!</p>

    </body>

</html>
```

In questo modo abbiamo modificato il colore, la dimensione del carattere e lo stile del titolo e del paragrafo nella pagina web. CSS può fare molto di più e, per la maggior parte dei casi standard, è consigliabile utilizzarlo al posto di JavaScript, che è più adatto per compiti più complessi anziché per la modifica dei colori dei pulsanti e dei testi (almeno nel contesto del web standard).

Tuttavia, anche con l'uso di CSS, le modifiche apportate al codice HTML sono ancora considerate "statiche". Per apportare modifiche significative ai dati concreti della pagina, è necessario che qualcosa accada e che qualcuno raccogla e modifichi fisicamente la struttura del DOM. E questo "qualcuno" è proprio JavaScript!

JavaScript non può agire da solo, ma richiede che accada qualcosa, una "circostanza di avvenimenti", sia essa determinata dalla macchina o da un'azione dell'utente. JavaScript è un linguaggio event-driven, interpretato runtime da un motore (solitamente scritto in C++ come il motore V8). Il codice JavaScript viene eseguito linea per linea da un interprete durante l'esecuzione del programma. L'interprete legge il codice sorgente, analizza le istruzioni una alla volta e le esegue immediatamente.

DaÈ importante notare che alcuni motori di interpretazione, come il V8, utilizzano anche la compilazione JIT (Just-In-Time Compilation) per ottimizzare l'esecuzione del codice durante l'esecuzione. Ciò significa che parte del codice JavaScript viene compilato in codice macchina in tempo reale per migliorare le prestazioni. Tuttavia, l'interprete viene comunque utilizzato per l'esecuzione complessiva del codice.

Detto quanto, cerchiamo di comprendere meglio gli eventi... 

<b>Gli eventi:</b> In JavaScript, gli eventi sono azioni che si verificano nella pagina web, come un click del mouse, una pressione di un tasto o il caricamento completo della pagina. Gli eventi consentono di interagire con l'utente e di rispondere alle azioni dell'utente sulla pagina. JavaScript fornisce un'ampia gamma di eventi predefiniti, come onclick, onload, onchange, e così via. Puoi ascoltare e gestire gli eventi utilizzando gli event listeners.

Per manipolare il DOM utilizzando gli eventi, puoi seguire questi passaggi:

Seleziona l'elemento HTML con cui desideri interagire utilizzando i metodi di selezione del DOM, ad esempio getElementById, getElementsByClassName, querySelector, ecc.

Aggiungi un event listener all'elemento selezionato. Un event listener è una funzione che verrà eseguita quando si verifica un determinato evento sull'elemento. Puoi "ascoltare" (intercettare) un evento specifico, come un click del mouse, o puoi ascoltare più eventi utilizzando i metodi addEventListener o on[evento] dell'elemento.

```js
const button = document.getElementById('myButton');

button.addEventListener('click', function() {
  // Azioni da eseguire quando si verifica il click
});

// oppure

button.onclick = function() {
  // Azioni da eseguire quando si verifica il click
};
```

All'interno della funzione dell'event listener, puoi manipolare il DOM come desideri. Puoi cambiare lo stile degli elementi, aggiungere o rimuovere classi, modificare il testo, creare nuovi elementi e molto altro ancora.

```js
const button = document.getElementById('myButton');
const myElement = document.getElementById('myElement');

button.addEventListener('click', function() {
  myElement.style.color = 'red';
  myElement.textContent = 'Nuovo testo';
  // Altre manipolazioni del DOM
});
```

Quando si verifica l'evento specificato, la funzione dell'event listener verrà eseguita, consentendo di apportare le modifiche desiderate al DOM in base all'azione dell'utente.
Manipolare il DOM tramite gli eventi consente di rendere la pagina web interattiva e reattiva agli input dell'utente. È possibile eseguire una vasta gamma di azioni, come validare i moduli, rispondere ai click del mouse, aggiornare dinamicamente il contenuto, eseguire chiamate AJAX e molto altro ancora. Sfruttando gli eventi, è possibile creare esperienze utente interattive e coinvolgenti.
