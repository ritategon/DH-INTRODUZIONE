# Classifying Texts

A questo punto, potresti dire: "La classificazione supervisionata va bene, ma come si collega all'analisi del testo? Me ne torno a cercare su Google foto di animali".&#x20;

Aspetta! Ce n'è qui uno per te. Se pensi di essere stanco, come pensi che si senta questo cane? Impersonare i bagel è estenuante. Forza!

![](../assets/sleepingstarbuck.jpg)

Bene: sei rimasto. Ti va riconosciuto un punto a favore :thumbsup:. L' ultima lezione voleva essere semplice in modo che tu potessi avere un'idea delle basi della classificazione supervisionata. Ora bisogna pensare a come applicare questo metodo ai testi. Il [capitolo 6](https://www.nltk.org/book/ch06.html)  del libro [NLTK ](https://www.nltk.org)(Natural Language Toolkit) che potresti consultare nel caso tu voglia approfondire la text analysis usando il linguaggio Python (vedi anche Further Resources alla fine della [sezione precedente](supervised-classifiers.md)) elenca alcune attività comuni di classificazione del testo:

> * Decidere se un' email sia spam o meno.
> * Decidere quale sia l'argomento di un articolo di notizie da un elenco fisso di aree tematiche come "sport", "tecnologia" e "politica".&#x20;
> * Decidere se una determinata occorrenza ad esempio della parola _bank_ (in inglese) sia usata per riferirsi alla riva di un fiume, a un istituto finanziario, all'atto di inclinarsi di lato o all'atto di depositare qualcosa in un istituto finanziario.

Analizziamo ciascuno di questi compiti. Ricorda, un classificatore supervisionato si basa sui dati etichettati per un set di addestramento. Questi dati di esempio che utilizzerai dipendono direttamente dal tipo di problema che ti interessa. Potresti lavorare a ritroso e capire di che tipo di dati di allenamento avresti bisogno a partire dalla domanda che è oggetto del tuo interesse:

* Per decidere se un'e-mail è spam, avrai bisogno di molti esempi di posta indesiderata.&#x20;
* Per contrassegnare un articolo di notizie come appartenente a una particolare categoria, avrai bisogno di esempi di articoli di ciascuna di queste categorie.&#x20;
* Per determinare l'uso della parola "bank", avrai bisogno di esempi della parola usata in tutti questi possibili contesti.

In ogni caso, non è sufficiente scaricare i dati nel classifier (classificatore). Dovresti anche decidere quali set di funzionalità vuoi esaminare per il training set per ciascuna attività. Decidi di creare un filtro antispam. Per determinare se un testo sia spam o meno, dovresti decidere quali caratteristiche ritieni indicative della posta indesiderata. E hai molte opzioni! Qui ci sono solo alcuni:

* Potresti decidere che la scelta delle parole sia indicativa di spam. Un'email che dice "Acquista ora! Fai clic su questo collegamento per visualizzare un messaggio urgente!" è probabilmente spam. Quindi dovresti suddividere i tuoi messaggi di spam rappresentativi in elenchi di vocaboli tokenizzati. Da lì lavoreresti per dare al classifier un senso di quelle parole che potrebbero comparire in messaggi indesiderati.&#x20;
* Potresti però anche notare che tutte le tue notifiche di spam provengono da email simili. E dunque potresti addestrare il classifier a identificare determinati indirizzi email, estrarre quelli che hanno indirizzi di spam noti e contrassegnarli come spam.

Potresti sicuramente trovare altri approcci. In ogni caso bisognerebbe pensare ad una serie di domande comuni a tutti i progetti di analisi del testo:

* Qual è la mia domanda di ricerca?&#x20;
* Come è possibile suddividere la mia domanda di grandi dimensioni in parti più piccole?&#x20;
* Quale di questi può essere misurata dal computer?&#x20;
* Che tipo di dati di esempio sono necessari per questo problema? Di quali dispongo già?

All'inizio rispondere a queste domande può essere difficile, ma, con la pratica, sarai in grado di separare le domande fattibili sulle discipline umanistiche da quelle a cui è impossibile rispondere. Inizierai ad avere un'idea di ciò che potrebbe essere misurato e analizzato, oltre a capire se valga o meno la pena farlo. Inizierai anche a farti un'idea di che tipo di progetti sono interessanti e valga la pena perseguire. (Aggiungi il fatto che da un punto di vista cognitivo questo tipo di operazione hanno un gran impatto nella testa di uno studente).

Ora, esercitiamoci su un approccio supervisionato a un problema comune nell'analisi del testo: l'attribuzione della paternità. A volte i testi arrivano a noi senza alcun autore attribuito loro e potremmo voler sapere chi li abbia scritti. O forse un singolo testo potrebbe essere scritto sotto uno pseudonimo, ma potresti avere una buona idea di chi potrebbe essere l'autore. Potresti affrontare questo problema in una varietà di modi senza supervisione, rappresentando graficamente la somiglianza o la differenza di autori particolari sulla base di una serie di algoritmi. Ma se hai un'idea abbastanza precisa di chi potrebbe essere l'autore di un particolare testo, puoi adottare un approccio supervisionato al problema. Vediamo l' elenco dei passaggi necessari:

* Qual è la mia domanda di ricerca?
  * Vogliamo identificare l'autore ignoto di un testo.
* Come è possibile suddividere la mia domanda di grandi dimensioni in parti più piccole?
  * Abbiamo un'ipotesi ragionevole su alcuni possibili autori, quindi possiamo usarli come oggetti di studio. Assumiamo anche che la paternità possa essere associata allo stile.
* Quale di questi può misurare il computer?
  * Bene, lo stile è la somma totale di vocabolario, punteggiatura e schemi retorici, tra le altre cose. Si possono contare tutti!
* Che tipo di dati di esempio abbiamo che possiamo usare per risolvere questo problema?
  * Abbiamo il testo sconosciuto. E abbiamo anche diversi testi dei miei potenziali autori che possiamo confrontare con esso.

sostituisci con questo [https://towardsdatascience.com/no-fear-stylometry-with-expert-ai-163892fd234](https://towardsdatascience.com/no-fear-stylometry-with-expert-ai-163892fd234) &#x20;

Processi simili sono stati utilizzati per una varietà di casi di attribuzione della paternità. Il più famoso degli ultimi tempi è probabilmente quello di Robert Galbraith, uscito con The Cuckoo's Calling nel 2013. Utilizzando un processo simile di misurazione della somiglianza linguistica, Patrick Juola è stato in grado di testare un'ipotesi che J.K. Rowling aveva pubblicato il romanzo poliziesco con uno pseudonimo. Puoi leggere di più sul processo [qui](https://www.scientificamerican.com/article/how-a-computer-program-helped-show-jk-rowling-write-a-cuckoos-calling/).  Un altro caso interessante si riferisce a Elena Ferrante: numerosi approcci sono raccolti dalla Padova University Press in [_Drawing Elena Ferrante's Profile_](http://www.padovauniversitypress.it/system/files/preview/9788869381300.pdf) __ gli atti del convegno svoltosi a Venezia nel 2017.

Abbiamo appena scalfito la superficie del campo della **stilometria**, o dello studio dello stile linguistico utilizzando una varietà di metriche statistiche. Puoi portare avanti questo processo di ricerca utilizzando diversi linguaggi di programmazione:

* [R con Stylo](https://computationalstylistics.github.io); [qui](https://computationalstylistics.github.io/stylo\_nutshell/) puoi esplorare un tutorial passo passo, ma anche [qui.](http://dh2013.unl.edu/abstracts/ab-136.html)
*



### Text Classification con Deep Learning

prendi da qua ess [https://monkeylearn.com/text-classification-examples/](https://monkeylearn.com/text-classification-examples/) [https://monkeylearn.com/text-classification/#:\~:text=Deep%20learning%20architectures%20offer%20huge,Recurrent%20Neural%20Networks%20(RNN).](https://monkeylearn.com/text-classification/#:\~:text=Deep%20learning%20architectures%20offer%20huge,Recurrent%20Neural%20Networks%20\(RNN\).)

poi metti come ess guidato per il greco ithaca [https://ithaca.deepmind.com/](https://ithaca.deepmind.com) prima con questo e poi con drive [https://colab.research.google.com/drive/1Pef1Q-lteXLYxBFT2Zd6t9kfu-7rekyY#scrollTo=hnK8uNKnDZlD](https://colab.research.google.com/drive/1Pef1Q-lteXLYxBFT2Zd6t9kfu-7rekyY#scrollTo=hnK8uNKnDZlD)  fonti usabili [https://epigraphy.packhum.org/](https://epigraphy.packhum.org)
