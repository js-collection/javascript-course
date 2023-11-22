# Javascript corso base
Materiale didattico a cura di @berto-dev - https://berto.dev


### LEZIONE 03

#### Cos'è Js, a cosa serviva, a cosa serve oggi, a cosa servirà!

JavaScript (JS) è un linguaggio di programmazione nato negli anni '90, sviluppato da Brendan Eich per la piattaforma Netscape Navigator. Inizialmente concepito come un semplice strumento per manipolare il comportamento delle pagine web, JS ha acquisito una popolarità enorme nel corso degli anni grazie alla sua flessibilità e alla capacità di essere eseguito direttamente dal browser.

Al suo inizio, JavaScript era principalmente utilizzato per aggiungere funzionalità dinamiche alle pagine web, consentendo agli sviluppatori di interagire con gli elementi HTML, manipolare il DOM e rispondere agli eventi dell'utente. L'obiettivo principale era migliorare l'esperienza di navigazione per gli utenti, rendendo le pagine più interattive e coinvolgenti.

Tuttavia, la storia di JavaScript è caratterizzata anche da una guerra tra i browser, con Netscape Navigator e Internet Explorer che implementavano versioni diverse del linguaggio. Questa frammentazione ha creato difficoltà agli sviluppatori, che dovevano scrivere codice diverso per ogni browser. Per risolvere questo problema, sono state introdotte le librerie JavaScript, tra cui spicca jQuery. jQuery ha semplificato la scrittura del codice e fornito una serie di funzionalità comuni, rendendo più agevole lo sviluppo web multi-browser.

Tuttavia, il punto di svolta per JavaScript è avvenuto con l'introduzione degli standard ECMAScript, che ha portato alla pubblicazione della versione ES6 nel 2015. Questo aggiornamento ha introdotto molte nuove caratteristiche e miglioramenti nel linguaggio, rendendolo più moderno e potente. Con l'adozione degli standard, la necessità di librerie come jQuery è diminuita gradualmente.

Parallelamente agli sviluppi lato client, JavaScript ha aperto nuove porte non solo nel campo del server, ma anche nello sviluppo di app mobili ibride. Con il proliferare dei framework come React Native, Ionic e NativeScript, gli sviluppatori sono in grado di utilizzare JavaScript per creare applicazioni mobili che possono essere eseguite su diverse piattaforme, come iOS e Android. Questo approccio ibrido offre vantaggi come la condivisione del codice tra diverse piattaforme, facilitando lo sviluppo e riducendo i tempi di produzione.

Inoltre, l'esplosione di nuove librerie JavaScript per il rendering avanzato ha aperto nuove opportunità per la creazione di interfacce utente complesse e coinvolgenti. Librerie come React.js, Angular.js e Vue.js hanno rivoluzionato lo sviluppo front-end, consentendo agli sviluppatori di creare interfacce utente dinamiche e reattive. Queste librerie si basano sul concetto di componenti riutilizzabili, semplificando lo sviluppo e la manutenzione del codice.

Grazie all'adozione di Node.js lato server e allo sviluppo di app ibride, JavaScript si è affermato come un linguaggio di programmazione full-stack. Gli sviluppatori possono utilizzare JavaScript sia per la parte client che per la parte server delle applicazioni web, consentendo un'implementazione coerente e semplificata dell'intero stack tecnologico. Questa capacità di utilizzare lo stesso linguaggio su entrambi i lati del perimetro ha accelerato lo sviluppo di applicazioni web complesse e ha favorito l'adozione di JavaScript come linguaggio dominante nello sviluppo web moderno.

Guardando al futuro, JavaScript continua a evolversi e ad essere ampiamente utilizzato. Grazie alla sua popolarità e alla vasta comunità di sviluppatori, il linguaggio è diventato una pietra angolare dello sviluppo web moderno. È sempre più comune trovare JavaScript anche in ambiti come l'intelligenza artificiale, l'apprendimento automatico e lo sviluppo di applicazioni mobili, ampliando ulteriormente le sue possibilità e la sua rilevanza nel panorama tecnologico attuale e futuro.


#### Perchè Js risulta apprezzatissimo? Capiamolo costruendo il nostro primo programma!

Della fruibilità di js ne abbiamo già parlato ma uno tra i motivi per cui js è adorato da molti sviluppatori è la capacità, rispetto al vecchio PHP, di poter essere tracciato e corretto velocemente. Per fare ciò è necessaria una semplice console di sistema o un terminale.

Possiamo dunque eseguire già da adesso il nostro primo programma e comprendere, sin da subito, quanto sia relativamente semplice usufriure di js:

- apri il browser
- per aprire la Console puoi:
    - clicca F12,
    - clicca Fn+F12
    - premere Command + Option + J (Mac)
    - Control + Maiusc + J
    - o semplicemente... tasto destro > ispeziona
- Hai ora un nuovo pannello... clicca su "console"

in 3 passaggi, pur non avendo un ecosistema un engine javascript dedicato (come nodejs) installato nella nostra macchina, possiamo testare quanto più ci piace in totale sicurezza.

Proviamo dunque a mettere subito mano alla cosa... Su quel pannello possiamo scrivere:

```js
console.log("HELLO WORLD!)
```

Premendo invio js ci restituirà il messaggio per la console stessa, ed abbiamo quindi realizzato il nostro primo, seppur minimale, programma in js.

Allo stesso modo possiamo sostituire quella scritta (che in informatica prende il nome di "stringa") con una qualsiasi parte o elemento del programma stesso, riuscendo sempre a controllare cosa funziona e... cosa no.

E' da notare che la console ha divesi label a disposizione. come il "console.warning" e il "console.debug", ma per un uso rapido va benissimo il classico "log".

Proviamo adesso a implementare qualcosa di più avanzato, ad esempio, supponiamo di voler salvare e poi stampare un numero conservato in memoria. Ecco come potremmo fare:

```js
ilMioNumero = 3
console.log("IL MIO NUMERO IN MEMORIA:",ilMioNubero)
```

In questo esempio abbiamo assegnato al computer uno spazio chiamato "ilMioNumero" con un valore "=" di quantità 3.
Ponete attenzione su un particolare: Numeri e parole, sono diversi.

In javascript è possibile incrementare, sottrarre, cambiare e operare matematicamente i numeri, ma se questi sono delle scritte diventerà un'operazione diversa... un "concatenamento di stringhe", un susseguirsi di caratteri.

Per capire meglio costruiamo due nuovi programmi...
In questo caso addizioniamo dei numeri:

```js
ilMioNumero_1 = 3
ilMioNumero_2 = 5
console.log("IL MIO NUMERO IN MEMORIA:", ilMioNubero_1+ilMioNubero_2 )
```
Il risultato sarà "IL MIO NUMERO IN MEMORIA: 8"

Il sistema ha palesemente fatto due cose: la prima è stata addizionare 3 con 5, proprio come un numero, la seconda è stata accostare la stringa "il mio numero in memoria:". Questo accade perchè siamo sulla console e perchè i due valori sono separati dalla virgola, quindi sono due cose distinte.
Supponiamo tuttavia di eseguire quanto segue:

```js
ilMioNumero_1 = "3"
ilMioNumero_2 = 5
console.log("IL MIO NUMERO IN MEMORIA:", ilMioNubero_1+ilMioNubero_2 )
```

Il risultato sarà molto diverso da prima perchè "ilMioNumero_1" non è un numero, ma un carattere! Dunque il sistema tornerà: "IL MIO NUMERO IN MEMORIA: 35" 
Ovvero "3"+ "converti in stringa 5"

Capito questo, proviamo a fare qualcosa di più divertente: proviamo ad usare due funzioni specifiche, il `timeout` e l'`interval` per indurre il programma a fare qualcosa quando volgiamo noi, con dei tempi prestabiliti.

Il setTimeOut, in js, ci permette di ritardare l'esecuzione di N millisecondi:

```js
nome = "Anna"
numeroBicchieri = "2"
millisecondi = 2000

setTimeout(()=>{
    console.log(nome, " ha bevuto più di ",numeroBicchieri, " bottiglie di vodka alla festa di Paolo!" )
},millisecondi)
```

Il sistema restituirà un divertente "Anna ha bevuto più di 2 bottiglie di vodka alla festa di Paolo!"

Se notate, stiamo effettivamente constrollando l'esecuzione di tutto ciò che accade. Abbiamo settato diverse allocazioni di memoria con diversi tipi di contenuto e abbiamo anche deciso che questi dovessero essere mostrati solo dopo N secondi. Stiamo decidendo noi tutto ciò, lo stiamo impostando di nostro pugno.

Proviamo a farla ancora più divertente... A che bicchiere sarà arrivata Anna oggi?

```js
nome = "Anna"
numeroBicchieri = 2
millisecondi = 2000

setInterval(()=>{
    console.log(nome, " ha bevuto già bevuto  ",numeroBicchieri++, " bicchieri di vodka!!" )
},millisecondi)
```

Adesso Anna sta bevendo il numero di bicchieri di sempre... +1 ogni due secondi!
Ponete attenzione, il "2" è ora un numero da addizionare. Lascio a voi vedere cosa succede se rimensse una stringa tra le virgolette.

Scherzi a parte, tutto ciò ci approccia alla giusta condizione di partenza per affrontare tutto ciò che dovremo imparare e che, dunque, adrà messo a schermo.

I vari tipi di dati e la loro elaborazione verranno ovviamente meglio affrontati in seguito, per ora abbiamo fatto i primi due grandi passi per avvicinarci al mondo dell'infromatica e di javascript: allocare qualcosa in memoria ed usarla a piacimento... cioè, un programma!

Buon divertimento per le prossime lezioni!
