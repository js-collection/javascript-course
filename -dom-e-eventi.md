# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 04

#### Il DOM

Il "Document Object Model" è una rappresentazione strutturata e gerarchica di un documento HTML o XML. Essa permette di manipolare e interagire con gli elementi di una pagina web utilizzando JavaScript. Il DOM rappresenta il documento come un albero di nodi, in cui ogni elemento, attributo e testo sono rappresentati da un nodo. Grazie al DOM, è possibile accedere e modificare dinamicamente gli elementi, gli attributi e il contenuto di una pagina web.

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

Da notare che l'HTML non è un linguaggio di programmazione, ma un linguaggio di markup che definisce la struttura di un oggetto statico, simile ad altri oggetti informatici, ma scritto in un file che conserva la sua forma idealizzata in gruppi di contenitori. Se desideri abbellire l'output del codice HTML, esiste un linguaggio apposito chiamato CSS che permette di aggiungere elementi visivi. Puoi trovare maggiori dettagli su ogni proprietà CSS tramite il W3C: [w3c : all-properties](https://www.w3.org/Style/CSS/all-properties.en.html) e molti esempi di tecnica di layouts in ["github: css-layout"](https://github.com/ulivz/css-layout) medio-avanzata nella repo ["github: You-need-to-know-css"](https://github.com/l-hammer/You-need-to-know-css) 

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


---

#### Manipolazione tramite attributi

La manipolazione dei contenuti tramite attributi di JavaScript e HTML è una tecnica molto potente che consente di modificare dinamicamente il contenuto di una pagina web. Attraverso l'uso di JavaScript, è possibile selezionare gli elementi HTML e modificarli aggiungendo, rimuovendo o cambiando i loro attributi.

Per selezionare gli elementi HTML, è possibile utilizzare vari metodi messi a disposizione da JavaScript, come `getElementById`, `getElementsByClassName`, `getElementsByTagName` e `querySelector`. Questi metodi consentono di identificare gli elementi sulla base del loro ID, classe, tag o selettore CSS.

Una volta selezionato l'elemento desiderato, è possibile accedere ai suoi attributi tramite la proprietà attributes. Ad esempio, se si desidera accedere all'attributo src di un'immagine, si può utilizzare la seguente sintassi: elemento.attributes.src.value.

Per modificare un attributo di un elemento HTML, si può assegnare un nuovo valore alla proprietà corrispondente. Ad esempio, per cambiare il testo di un elemento h1, si può utilizzare il seguente costrutto:

```js
elemento = document.getElementById("mioTitolo")
elemento.textContent = "Nuovo titolo"
```

Nell'esempio, getElementById viene utilizzato per selezionare l'elemento con l'ID "mioTitolo", mentre textContent viene utilizzato per assegnare un nuovo valore al testo dell'elemento.

Inoltre, è possibile recuperare vecchi o aggiungere nuovi attributi agli elementi HTML o rimuoverli utilizzando le apposite funzioni di JavaScript. Ad esempio, per aggiungere un attributo href a un elemento a, si può utilizzare il seguente codice:

```js
link = document.getElementById("mioLink")

// recuperare un attributo
linkLink = link.getAttribute("href")

// settare un attributo 
link.setAttribute("href", "https://www.example.com")
```

In questo nuovo esempio, `setAttribute` viene utilizzato per aggiungere l'attributo href all'elemento con l'ID "mioLink" e assegnargli il valore "https://www.example.com".

E' da notare che, come da esempi precedenti, è possibile settare un attributo anche come accade per gli oggetti:
```js
linkLink = document.getElementById("mioLink").getAttribute("href")
linkLink = "https://www.example.com"

// oppure:
document.getElementById("mioLink").href = "https://www.example.com"
```

Questa pratica, anche se sintatticamente più estetica, non è consigliabile per ragioni di compatibilità.

La manipolazione dei contenuti tramite attributi di JavaScript e HTML offre un'ampia gamma di possibilità per rendere le pagine web più dinamiche e interattive. Con queste tecniche, è possibile creare effetti di animazione, aggiornare dinamicamente i dati o personalizzare il contenuto in base alle preferenze dell'utente.

---

#### Gli eventi

In JavaScript, gli eventi sono azioni che si verificano all'interno di una pagina web o di un'app, come un click del mouse, una pressione di un tasto o il completamento del caricamento della pagina. Gli eventi permettono le interzioni utente e di rispondere alle sue azioni direttamente in pagina.
JavaScript fornisce una vasta gamma di eventi predefiniti, come onclick, onload, onchange e molti altri. È possibile ascoltare (intercettare) e gestire questi eventi utilizzando gli event listener.

Per manipolare il DOM utilizzando gli eventi, è possibile seguire questi 3 semplici passaggi:

- Selezionare l'elemento HTML con cui si desidera interagire utilizzando i metodi di selezione del DOM, come getElementById, getElementsByClassName, querySelector, ecc.
- Aggiungere un event listener all'elemento selezionato. Un event listener è una funzione che verrà eseguita quando si verifica un determinato evento sull'elemento.
- Definire la logica da eseguire quando l'evento si verifica all'interno della funzione dell'event listener.

Ecco un esempio di codice JavaScript che mostra come utilizzare un event listener per gestire un click del mouse su un elemento:

```js
button = document.getElementById('myButton')

button.addEventListener('click', function() {
  // Azioni da eseguire quando si verifica il click
})

// o anche:

button.onclick = function() {
  // Azioni da eseguire quando si verifica il click
}

// nota bene: "addEventListener" è un metodo che consente di ascoltare e gestire eventi specifici
// su un elemento specifico, mentre "window.onclick" è una proprietà globale che consente di
// assegnare direttamente una funzione come gestore dell'evento di clic sull'intera finestra del browser.
```

All'interno della funzione dell'event listener, puoi manipolare il DOM come desideri. Puoi cambiare lo stile degli elementi, aggiungere o rimuovere classi, modificare il testo, creare nuovi elementi e molto altro ancora.

```js
button = document.getElementById('myButton')
myElement = document.getElementById('myElement')

button.addEventListener('click', function() {
  myElement.style.color = 'red'
  myElement.textContent = 'Nuovo testo'
  // Altre manipolazioni del DOM
})
```

Quando si verifica l'evento specificato, la funzione dell'event listener verrà eseguita, consentendo di apportare le modifiche desiderate al DOM in base all'azione dell'utente.
Manipolare il DOM tramite gli eventi consente di rendere la pagina web interattiva e reattiva agli input dell'utente. È possibile eseguire una vasta gamma di azioni, come validare i moduli, rispondere ai click del mouse, aggiornare dinamicamente il contenuto, eseguire chiamate AJAX e molto altro ancora. Sfruttando gli eventi, è possibile creare esperienze utente interattive e coinvolgenti.

Prima di proseguire è bene sapere che tutto ciò non rappresenta pienamente l'uso del termine "dinamico" (anche se tutto, umanamente, sembra muoversi). Per un informatico il termine è più collegato alle esigenze di salvataggio e stoccaggio dati nei database e alla creazione dei sistemi server per gestirle... ma realizzare un'interfaccia con dinamismi ne è comunque una parte.

Terminiamo con il processo con cui un listener lavora può essere approfondito [nei manuali del w3c](https://www.w3.org/TR/uievents/), di cui è possibile estrarre la lista di ogni evento che, per comodità, ho riassunto in un file dedicato [qui](https://github.com/js-rt-collection/js-basic-course-ita/blob/main/-all-javascript-event-listeners.md).


