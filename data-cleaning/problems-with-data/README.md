# Problemi con i dati

Ora supponiamo tu abbia un testo e voglia farci qualcosa. Potrebbe essere allettante immergersi e iniziare a utilizzare uno degli strumenti in questo libro, ma dovresti prenderti un momento per esaminare i materiali con cui stai lavorando. Non ogni testo è uguale e i tuoi risultati possono avere seri problemi se non ti preoccupi di esaminare la qualità dei materiali prima di lavorarci. Il principio di base da ricordare è **Garbage in, garbage out** (letteralmente "spazzatura dentro, spazzatura fuori", **GIGO** in forma abbreviata; anche _rubbish in, rubbish out_):  è una frase utilizzata nel campo dell'informatica e della tecnologia dell'informazione e della comunicazione. È utilizzata soprattutto per richiamare l'attenzione sul fatto che i computer elaborano in modo acritico anche un insieme di dati in entrata palesemente insensati (_garbage in_) producendo, a loro volta, un risultato insensato (_garbage out_).

## OCR

![sherlock holmes article clipping](../../assets/data-cleaning/holmes.jpg)

Prendi questa immagine, tratta da una stampa del 1922 di [_The Duluth Herald_](https://archive.org/details/duluthherald10311922unse), di un annuncio su un giornale per la versione cinematografica americana di Sherlock Holmes.

Per impostazione predefinita, il computer non ha idea della presenza di testo all'interno di questa immagine. Per un computer, un'immagine è solo un'immagine. Il computer potrebbe ruotarla, ritagliarla, ingrandirla o dipingere su parti di essa, ma la tua macchina non può leggere il testo, a meno che tu non le dica come farlo. In effetti, il computer non sa nemmeno che c'è del testo lì. Per quanto lo riguarda, un dipinto astratto e un'immagine come questa contengono la stessa quantità di informazioni testuali. Il computer richiede un piccolo aiuto in più per estrarre le informazioni di testo dall'immagine.

Come hai già appreso in precedenza, il processo di utilizzo del software per estrarre il testo da un'immagine di un testo è chiamato **riconoscimento ottico dei caratteri** o OCR. Occasionalmente utilizziamo l'OCR come sostantivo, come in "l'OCR per quel documento è piuttosto scadente" o come verbo, come in "dobbiamo eseguire l'OCR di questo testo prima di poterlo elaborare". Esistono molti strumenti che possono generare l'OCR per un testo e alcuni sono proprietari, il che significa che devi pagare per poterli utilizzare. Tutti questi strumenti sono solo così efficienti nel processo: ciò che è facile per te richiede molta potenza di calcolo per essere eseguito in modo efficace.

![ocr'd sherlock holmes text](../../assets/data-cleaning/holmes-ocr-text.jpg)

Eseguendo questa immagine attraverso uno strumento gratuito comune per l'OCR del testo, otteniamo un tentativo confuso del computer di tradurre l'immagine in testo.

Il docuemnto iniziale è ancora riconoscibile, ma ci sono evidenti problemi con la riproduzione. A prima vista, potresti pensare: "Dovrebbe essere facile! Ho imparato a leggere molto tempo fa. Riesco persino a leggere le cose scritte in corsivo! Perché il computer fa così fatica?". Questo è uno di quei casi in cui ciò che a te non crea problemi, è molto difficile per un computer. Gli esseri umani sono bravissimi nel riconoscimento dei modelli, funzione che appunto viene chiesta ad un OCR.&#x20;

Questa operazione è in realtà un problema piuttosto complicato per i computer.  [WhatFontis.com](http://www.whatfontis.com) elenca oltre 342.000 caratteri e questo conteggio sembra includere solo caratteri occidentali. Una singola parola avrà un aspetto leggermente diverso in ogni carattere e in ogni dimensione. E questo non tiene nemmeno conto del testo scritto a mano o del testo che è stato parzialmente danneggiato: anche una leggera imperfezione in una lettera può complicare il processo di scansione. Il processo è complicato e richiede molto lavoro e anche il software OCR più costoso è soggetto a errori. Se vedi trascrizioni di testo pulite di un'immagine online, è molto probabile che un essere umano ripulisca l'OCR per renderlo leggibile.

Un notevole aiuto in questo senso in certi contesti viene offerto da [Mirador](mirador.md).

## Data Cleaning

Lasciatemelo dire di nuovo, i computer non possono dedurre. Immagina questo scenario: contiamo fino a dieci!

1,2,3,4,5,6,7,8,10

Probabilmente volevi avere un 9 lì dentro, e una lettura umana molto probabilmente saprebbe che c'è stato un errore. Ma il computer non avrà idea che tu abbia accidentalmente omesso un numero. Dovresti dirlo specificamente per rendere conto di tali errori. Questo semplice fatto sulla logica computazionale diventa un grosso problema nelle discipline umanistiche, perché i dati umanistici sono disordinati. Per vedere cosa intendiamo, dai un'occhiata alla sezione di Wikipedia sul nome di [Sir Arthur Conan Doyle](https://en.wikipedia.org/wiki/Arthur\_Conan\_Doyle#Name).  Puoi verificare, ma tradotto i italiano, leggi quanto segue:

![](../../.gitbook/assets/screenshot-en.wikipedia.org-2022.03.21-10\_08\_09.png)

E' chiaro che Doyle ha una storia di nomi complicata. Ora immagina di mettere insieme un database di autori. Arrivi a Doyle. Come salverai il suo nome? Possiamo pensare a una serie di possibilità:

```
Doyle Arthur Doyle
A.C. Doyle
Doyle, A.C.
Doyle, Sir Arthur
Doyle, Sir Arthur Conan
Sir Arthur Conan Doyle
```

Probabilmente puoi immaginarne altri. Tutti questi sono tecnicamente corretti e potrebbero servire perfettamente ai tuoi scopi. Ma devi essere coerente. Ricordi come i computer non possono dedurre nulla? Immagina questo come parte del tuo database di autori:

```
Author Name
---
Austen, Jane
James Joyce
Arthur Conan Doyle
```

Stai lavorando con diversi formati:

```
Author Name
---
Austen, Jane: last_name, first_name
Arthur Doyle: first_name last_name
```

Un programma per computer avrebbe bisogno di un modo per capire cosa  tu gli stia dando, qualcosa come:&#x20;

1\) Guarda questo database "Nome dell'autore".&#x20;

2\) Ogni autore ha una sua linea.&#x20;

3\) Ottieni il nome dell'autore.

Questi dati causerebbero problemi con il terzo passaggio. Per cominciare, come fa il computer a ottenere i nomi? Ci sono due opzioni qui:

* Cerca una virgola nella riga. Prima della virgola troverai il cognome. Dopo di esso, troverai il nome.
* Cerca uno spazio nella riga. Prima dello spazio troverai il nome. Dopo di esso, troverai il cognome.

Il primo è il modo più comune di rappresentare dati come questo. L'uso delle virgole per denotare le diverse parti di dati è così popolare che il formato ha il proprio nome: **valore separato da virgole** o **csv** (lo abbiamo incontrato nella sezione [La forma dei dati](../../acquisire-e-creare-dati/forma-dei-dati/))**.** Ha un vantaggio rispetto al secondo formato che suddivide i dati in base agli spazi:

```
Author Names
---
Austen Jane
Arthur Doyle
Arthur Conan Doyle
```

If we used spaces to denote breaks between first name and last name, Arthur Conan Doyle would cause our program to error. It would likely interpret 'Arthur' as the first name and 'Conan' as the last name. 'Doyle' would be an unkown. Reformatting this as a csv allows us to handle Conan Doyle's full name:

Se usiamo gli spazi per indicare le interruzioni tra nome e cognome, Arthur Conan Doyle causerebbe errori nel nostro programma. Probabilmente interpreterebbe "Arthur" come nome e "Conan" come cognome. 'Doyle' sarebbe uno sconosciuto. La riformattazione di questo come CSV ci consente di gestire il nome completo di Conan Doyle:

```
Author Names
---
Austen, Jane
Arthur, Doyle
Arthur Conan, Doyle
```

Il  problema che vedi sotto dovrebbe essere ovvio: Jane Austen è in un formato "cognome, nome", mentre gli altri sono al contrario. Quindi la nostra versione finale di questo set di dati sarebbe simile a questa:

```
Author Names
---
Austen, Jane
Doyle, Arthur
Doyle, Arthur Conan
```

We might go further to associate Arthur Doyle and Arthur Conan Doyle as being representations of the same person, a process known as **authority control**. A common way of referring to data that contains inconsistencies and/or errors is as **dirty data**. To keep the metaphor, then, the process of revising data to remove such problems and prepare it for use is called **data cleaning**.

Potremmo andare oltre associando Arthur Doyle e Arthur Conan Doyle come rappresentazioni della stessa persona, un processo noto come **controllo dell'autorità (authority control).** Un modo comune di riferirsi a dati che contengono incoerenze e/o errori è come **dati sporchi (dirty data)**. Per mantenere la metafora, quindi, il processo di revisione dei dati per rimuovere tali problemi e prepararli all'uso è chiamato **pulizia dei dati (data cleaning)**.

## Metadati

Se hai mai cercato un libro utilizzando un'interfaccia di ricerca in biblioteca, hai interagito con le categorie di metadati. M**etadati**, nella sua accezione più elementare, significa dati sui dati. Un testo, dopo tutto, è qualcosa di più delle semplici parole sulla pagina. Abbiamo tutta una serie di altre informazioni che utilizziamo per descrivere il documento. L'autore, la sua data di pubblicazione, il suo editore, il suo stato di copyright, ecc.: potremmo avere molto interesse per queste informazioni e potremmo volerle utilizzare per analisi particolari. Queste categorie ci consentono di fare cose come cercare libri con titoli particolari di periodi di tempo particolari. Nel nostro esempio precedente, stavamo effettivamente lavorando con i metadati senza rendercene conto.

```
Author Names
---
last_name, first_name
Austen, Jane
Doyle, Arthur
Doyle, Arthur Conan
```

We have two metadata categories here: last\_name, and first\_name. Each are separated by a comma. We might even think of author\_name as being its own metadata category for someone else's list of books! Databases are really these sorts of things at their heart: data and metadata, organized in systematic ways to make them easily usable.

Imagine you have started to put together your own table of author names and you notice that your neighbor is putting together one of her own. You want to be able to compare notes and, even more, you want to combine lists. It should be obvious that you will have real problems if you organize things as "first\_name last\_name" and she organizes things as "last\_name, first\_name". You would need to do a lot of extra work to merge your two lists. It would have been easier if you were working with an accepted standard for how author names should be listed.

Qui abbiamo due categorie di metadati: cognome e nome. Ciascuno è separato da una virgola. Ma potremmo anche pensare che nome\_autore sia la categoria di metadati per l'elenco di libri di qualcun altro. I database sono essenzialemente questo: dati e metadati, organizzati in modo sistematico per renderli facilmente utilizzabili.&#x20;

Immagina di aver iniziato a mettere insieme la tua tabella di nomi di autori e di notare che la tua vicina ne sta mettendo insieme una sua. Vuoi essere in grado di confrontare le note e, ancora di più, vuoi combinare elenchi. Dovrebbe essere ovvio che avrai problemi reali se organizzi le cose come "first\_name last\_name" e lei organizza le cose come "last\_name, first\_name". Dovresti fare molto lavoro extra per unire i tuoi due elenchi. Sarebbe stato più facile lavorando con uno standard condivido.

Tali standard di metadati esistono e molto lavoro è necessario per mantenerli (controlla [Dublin Core](https://www.dublincore.org) se sei interessato a [saperne di più](https://it.wikipedia.org/wiki/Dublin\_Core)).&#x20;

![](../../.gitbook/assets/screenshot-www.dublincore.org-2022.03.21-10\_31\_10.png)



Questi standard garantiscono che chiunque produca un nuovo set di dati crei un lavoro che possa facilmente tradursi e comunicare con altri sistemi. Garantiscono che i dati della tua biblioteca locale possano essere eventualmente inseriti nelle biblioteche digitali pubbliche e resi disponibili su larga scala. Il processo potrebbe sembrare facile con questo esempio di nome dell'autore di base, ma immagina di provare a coordinare tali standard di metadati per tutte le persone che lavorano su tutti i tipi di oggetti culturali, in tutto il mondo. Il lavoro non finisce mai.&#x20;

Prendere in considerazione tutti i diversi standard di metadati e i loro usi sarebbe un'impresa folle. Qui l'intento era solo farti prendere familiarità con i concetti.

## Ulteriori risorse

* Chris Woolford offre una spiegazione più dettagliata di come l'OCR lavora [explainthatstuff.com](http://www.explainthatstuff.com/how-ocr-works.html). (Ricorda sempre di usare tasto destro "traduci" se l'inglese ti mette in difficoltà).
