# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### Il DOM e gli eventi

<b>Il DOM (Document Object Model):</b> Il DOM è una rappresentazione strutturata e gerarchica di un documento HTML o XML, che consente di manipolare e interagire con gli elementi della pagina web utilizzando JavaScript. Il DOM rappresenta il documento come un albero di nodi, in cui ogni elemento, attributo e testo sono rappresentati da un nodo. Il DOM offre un'API che consente di accedere e modificare dinamicamente gli elementi, gli attributi e il contenuto di una pagina web.

Tutti i nodi disponibili sono presenti tra i manuali didattici del w3c [[1](https://w3c.github.io/)][[2](https://www.w3.org/)] che, tra le altre cose, rappresenta l'ente ufficiale che determina lo standard di qualità del web moderno e "<a href='https://w3c.github.io/elements-of-html/' target='_blank'>tutti i suoi componenti html</a>" ed la loro <a href='https://validator.w3.org/#validate_by_input' target='_blank'>validazione strutturale</a>. Questi componenti possono essere recuperati e manipolati per struttura, attributi e valori, da javascript direttamente in runtime (mentre il codice è in funzione) perchè Js è parte integrante dell'ecosistema web... è letteralmente nato per la manipolazione dei dati del DOM e del lato utente, quindi dell'HTML o di qualsiasi markup (di cui si disponga delle API adatte) per la struttura di dati.

JavaScript, tuttavia, non si muove da solo e necessita che qualcosa "capiti"... questa "circostanza di avvenimenti" dettati dalla macchina in uso o da un'azione utente è appunto detta "evento". Per l'esattezza: Js è un linguaggio event driven, interpretato runtime da un motore (solitamente scritti in c++ come il V8) ovvero il cui codice viene eseguito linea per linea da un interprete durante l'esecuzione del programma stesso. L'interprete legge il codice sorgente, analizza le istruzioni una alla volta e le esegue immediatamente.
Da notare che alcuni motori di interpretazione, proprio come il V8, utilizzano "anche" la compilazione JIT (Just-In-Time Compilation) per ottimizzare l'esecuzione del codice durante l'esecuzione, traformando l'interpretazione in linguaggio a basso livello, quindi da "istruzione" a "macchina" letteralmente. Questo significa che parte del codice JavaScript, talvolta, viene compilato in codice macchina in tempo reale per migliorare le prestazioni, ma rimane che l'interprete viene comunque utilizzato per l'esecuzione complessiva del codice.

Chiarito ciò, cerchiamo di comprendere meglio gli eventi... 

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
