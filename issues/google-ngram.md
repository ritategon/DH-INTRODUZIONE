# Google NGram Viewer

Il [Google NGram Viewer](https://books.google.com/ngrams) è spesso la prima cosa che viene fuori quando le persone discutono di analisi testuali su larga scala e serve bene come introduzione di base alle possibilità della lettura assistita dal computer.

![](../.gitbook/assets/screenshot-books.google.com-2022.02.19-12\_12\_32.png)

Google NGram Viewer fornisce un modo semplice e veloce per esplorare i cambiamenti nella lingua nel corso di molti anni in molti testi. Digita una parola o una frase separata da virgole e il visualizzatore NGram rappresenterà un grafico della frequenza con cui questi termini di ricerca si verificano in un determinato corpus per un determinato numero di anni. Puoi specificare un numero di anni e un particolare corpus di Google Libri.&#x20;

Lo strumento consente di cercare rapidamente centinaia di migliaia di testi e, tracciando alcune parole o frasi, trarre inferenze sui cambiamenti culturali e storici. Se cerchiamo ad esempio "science" e "religion", potremmo trarre conclusioni sulla loro importanza relativa in vari momenti degli ultimi secoli.

![](../assets/issues/science-religion.jpg)

Guardando il grafico, si potrebbero vedere le prove di un'argomentazione sulla crescente secolarizzazione della società negli ultimi due secoli. Il costante aumento dell'uso della parola scienza negli ultimi 200 anni, accompagnato dal precipitoso declino della parola religione a partire dalla metà del diciannovesimo secolo, potrebbe fornire prove concrete di ciò che altrimenti potrebbe essere aneddotico. Ma meglio andare con calma: cosa viene effettivamente misurato qui? Abbiamo bisogno di porre domande su un certo numero di elementi di questo argomento, compresi quelli riguardanti:

* Corpus
* Methodologia
* Interpretazione

## Corpus

Con qualsiasi analisi del testo su larga scala, i dati sottostanti sono tutto. Immagina di eseguire la stessa ricerca di parole per "science" e "religion" su oltre 1000 testi utilizzati nelle scuole o nei servizi religiosi. Lo stesso sarebbe vero se prendessimo di mira i libri di testo di biologia, botanica e fisica nello stesso periodo di tempo. Dagli esempi risulta abbastanza evidente lo stesso principio: l'input influisce sull'output. I dati che scegliamo per uno studio possono distorcere le nostre conclusioni ed è importante per noi riflettere attentamente sulla loro selezione come parte del processo.

* Qual è il corpus, o insieme di testi, utilizzato per generare questi dati?&#x20;
* Da dove provengono questi dati?

Google NGram Viewer offre un menu a discesa in cui è possibile selezionare un corpus da studiare. I nostri risultati sono molto diversi a seconda del corpus che abbiamo selezionato. I corpora per queste opzioni vengono estratti dal progetto di scansione di Google Libri (per vedere visualizzazioni simili del tuo corpus, puoi provare a lavorare con [Bookworm](http://bookworm.library.yale.edu/#), uno strumento correlato; [qui ](http://dh.library.yale.edu/projects/vogue/student\_work/)puoi vederne un uso avanzato). Ciò solleva una serie di difficoltà. Come hanno notato [Eitan Adam Pechenick, Christopher M. Danforth e Peter Sheridan Dodds](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0137041), il corpus ha solo una copia di ogni libro nel suo set di dati. Quindi le cose non vengono ridimensionate per la circolazione o la popolarità. **Un libro che vende una sola copia ha lo stesso peso di un libro che vende mille copie**: sono entrambi una sola copia **secondo i metodi di Google**.

Il corpus di [Google Books](https://it.wikipedia.org/wiki/Google\_Libri) è stato anche, a volte, criticato per la sua forte **dipendenza da scansioni di testi di scarsa qualità** per generare i propri dati (ne parleremo più avanti nei capitoli successivi). Il computer non può dedurre, ad esempio, che l'errore di ortografia "scyience" debba essere unito ai risultati di "science". Eventuali problemi di fondo nella scansione o nel caricamento di testi distorceranno i risultati. Inoltre, i risultati sono migliori dopo il 1820. Prima di allora c'erano molti meno libri pubblicati e ancora meno sono su Google Books.

Come suggerisce [Ted Underwood](https://tedunderwood.com/2010/12/30/several-varieties-of-noise-and-the-theme-to-love-story/), se affrontati con un sano senso di scetticismo, molti di questi problemi permettono di non scartano l'uso dello strumento per "relative comparisons between words and periods" (Trad. confronti relativi tra parole e periodi) dopo il 1820 circa. Non possiamo conoscere le verità dirette attraverso lo spettatore, ma possiamo comunque usare i dati per l'analisi. Per ora, ricorda solo che i grafici possono sembrare esprimere fatti quando, **in realtà, i dati sono oscuri**, soggetti a dibattito o distorti.

Di seguito trovi una lista di banche dati/archivi:

* [OPAC SBN ](https://opac.sbn.it/opacsbn/opac/iccu/free.jsp)Istituto Centrale per il Catalogo Unico delle Biblioteche Italiane e per le Informazioni Bibliografiche
* [Worldcat](https://www.worldcat.org)
* [Europeana](https://www.europeana.eu/it)
* [Gallica](https://gallica.bnf.fr/accueil/it/content/accueil-it?mode=desktop)
* [Wiki GLAM](https://it.wikipedia.org/wiki/Progetto:GLAM)

## Metodologia

Anche con un corpus perfetto, le nostre scelte possono fare una grande differenza sui risultati che produciamo. La ricerca di cui sopra tiene conto solo di singole parole, ma ci sono modi più sfumati di utilizzare NGram Viewer. Un **n-gram** è un altro nome per una sequenza di parole di lunghezza n. Prendi questa breve frase:

'frase di prova.'

Abbiamo tre n-grammi di lunghezza 1 ("frase", "di" e "prova"), due n-grammi di lunghezza 2 ("frase di" e "di prova") e 1 n-gram di lunghezza 3 ("frase di prova"). Oppure, potremmo usare un'abbreviazione: abbiamo 3 **unigrammi** o **tokens**, 2 **bigrammi** e 1 **trigramma**. Questi sono solo modi per descrivere diversi modi di spezzettare un pezzo di testo in modo che possiamo lavorarci. E possiamo fare la stessa cosa in NGram Viewer. Prendi questo Ngram per il token 'scandal' in un corpus inglese:

![](../assets/issues/scandal.jpg)

Sembra che qualcosa di abbastanza drammatico sia accaduto intorno al 1660 che ha causato un enorme picco nell'uso di "scandalo". Questo di per sé potrebbe essere significativo, ma potremmo essere interessati a letture più sfumate di questi dati. Potremmo voler vedere, per esempio, biggrammi contenenti scandali come "scandalo politico" e "scandalo religioso" da osservare quando certi tipi di scandali diventano importanti. Il visualizzatore NGram consente una serie di ricerche sfumate di cui puoi leggere [qui](https://books.google.com/ngrams/info). Per ora, proviamo una ricerca con caratteri jolly - '\*scandal':

![](../assets/issues/wildcard-scandal.jpg)

L'asterisco in ricerche come questa corrisponde a qualsiasi cosa, quindi restituirà tutte le frasi di due parole contenenti "scandal" come seconda parola. E, utile per noi, ci mostrerà i primi dieci usi. In questo caso, sono quasi tutti articoli o preposizioni: ‘the scandal,’ ‘a scandal,’ ‘of scandal,’ ecc. E sembrano tutti aumentare anche intorno al 1660. Avremmo bisogno di maggiori informazioni su questo periodo di tempo per dire esattamente cosa sta succedendo qui, e per farlo potremmo voler escludere specificamente questi usi comuni. Data la relativa inaffidabilità di N-Grams prima del 1820, questo drammatico aumento potrebbe essere dovuto solo a poche opere che usavano il termine "scandalo" in questo periodo e potrebbe non essere rappresentativo di modelli più ampi.

Potremmo anche voler esaminare diverse forme della stessa parola. Dopotutto, la ricerca di cui sopra cattura solo la forma singolare di "scandal", ma qualsiasi parola può presentarsi in più forme nel corso di un corpus. Il visualizzatore NGram può tenere conto anche di questo:

![](../assets/issues/forms-of-scandal.jpg)

L'enorme picco che vediamo nell'uso di "scandal" non è del tutto eguagliato da altre forme della parola. In particolare, l'aggettivo 'scandalous' gode di maggiore uso fino alla metà dell'Ottocento. Forse scandalo come sostantivo, come idea, come cosa a sé stante esplode sulla scena a metà del diciasettesimo secolo, prima che fosse qualcosa di più legato ad altre persone, luoghi ed eventi.

Per approfondire un altro termine rilevante per questo corso, dai un'occhiata a questo ngram della parola "crime" nel corpus inglese:

![](../.gitbook/assets/screenshot-books.google.com-2022.02.19-12\_57\_09.png)

Secondo questo grafico, dopo un calo all'inizio del diciottesimo secolo, gli scrittori inglesi hanno discusso del crimine in modo onnipresente. Ma che dire degli autori che scrivono in altre lingue? Ecco la stessa ricerca in francese e di seguito in italiano:

![](../assets/issues/french-crime-ngram.jpg)

![](../.gitbook/assets/screenshot-books.google.com-2022.02.19-13\_27\_05.png)

Prova a vedere cosa succede se per le stesse parole (inglese _crime_, francese _crime_ e italiano _crimine_ porti la finestra cronologia al 2019. Ne sarai sorpreso,

La tendenza generale di più menzioni di crimine nel 19° secolo rispetto al 20° vale sia nei corpora francesi che in quelli inglesi. Tuttavia, se presti molta attenzione all'asse y, noterai che gli autori francesi in realtà menzionano il crimine molto più frequentemente rispetto al resto degli scritti dell'epoca. Le tendenze sono simili, ma la percentuale di volte in cui si manifesta "criminalità" è molto più alta in Francia. In Inghilterra durante questo periodo, gli usi della parola oscillano intorno a 0,0045. La scrittura francese che menziona "criminalità" è più del doppio di quella percentuale nello stesso periodo e non scende a quel numero fino al 1880.

Noterai anche una traiettoria diversa da questi due N-Gramm. Nel corpus in lingua inglese, le menzioni di "crimine" diminuiscono gradualmente nel corso del diciannovesimo secolo. Al contrario, c'è un grande picco nel corpus francese che inizia a diminuire in modo abbastanza drammatico negli anni '30 dell'Ottocento. Se leggessi parti di Louis Chevalier's _Laboring Classes and Dangerous Classes in Paris during the First Half of the Nineteenth Century_, potresti trovare le ragioni per cui l' interesse per la criminalità aumenta all'inizio del diciannovesimo secolo e poi si attenua.

Se dovessimo usare N-Grams per qualcosa di più di una semplice dimostrazione, vorremmo fare molte più ricerche e pensare sia alla lingua che alla storia. Ad esempio, nell'esempio sopra, il fatto che gli autori francesi sembrino usare "crime" più spesso di quelli in lingua inglese è dovuto a una differenza di lingua e di uso? Forse gli autori inglesi usano spesso un sinonimo di _crime_, mentre quelli francesi no? O riflette il fatto che gli autori francesi erano più interessati al crimine rispetto a quelli inglesi?

Oppure, diciamo che ci interessa la storia del razzismo scientifico nel pensiero europeo e americano. In tal caso, potremmo voler conoscere la traiettoria della parola "race"  (trad. razza) nel tempo.

![](../assets/issues/race.jpg)

Questo N-Gram mostra un uso crescente di questo termine nel corso del diciottesimo e diciannovesimo secolo, raggiungendo un picco intorno al 1890 e poi gradualmente diminuendo nel ventesimo secolo, anche se con alcune riprese. Da un lato, il razzismo scientifico ha avuto uno dei suoi tempi d'oro alla fine del diciannovesimo secolo, quindi forse questo N-Gram mostra questa tendenza storica. Ma non appena pensi di più a questo argomento, ti rendi conto che la questione è molto più complicata di questo. Per prima cosa, potrebbe sembrare un po' strano che la linea si abbassi alla fine degli anni '50 e all'inizio degli anni '60, un'era in cui stava emergendo il movimento per i diritti civili. Le persone scrivevano davvero meno sulla razza allora rispetto a prima? In alternativa, il termine "race" può significare molte cose diverse; in questo caso, i risultati che ci interessano (la categorizzazione delle persone in base ai loro fenotipi) sono senza dubbio confusi con riferimenti a eventi sportivi ed elezioni. E non appena abbiamo iniziato a fare ricerche sulla storia del razzismo scientifico, abbiamo appreso che gli scrittori usavano il termine "race" per riferirsi a gruppi di persone in modi diversi nel diciottesimo secolo rispetto alla fine del diciannovesimo secolo. Vorremmo anche pensare a termini associati o usati come sinonimi di razza. Forse gli autori del ventesimo secolo usavano altre parole per parlare di razza? Se sì, quali potrebbero essere?

Quindi, la lingua cambia nel tempo. Una singola parola potrebbe cambiare radicalmente nell'uso nel corso dei secoli in modi che distorcono i nostri risultati. Usiamo anche termini diversi nel tempo per descrivere gli stessi fenomeni. Queste sono tutte cose che vorremmo far emergere molto di più in qualsiasi interpretazione che utilizzi N-Grams. Dovremmo anche considerare ciò che N-Grams possono (e non possono) dirci e pensare a potenziali problemi nella nostra lettura. Ma per fortuna queste implicazioni della tecnologia non scoraggino e sono comunque interessanti.

* Infatti i metodi digitali possono permetterci di fare osservazioni su un gran numero di testi. Molto più di quante se ne potrebbero fare leggendo i testi con le modalità tradizionali.

Quest'ultima frase dovrebbe destare qualche allarme: in realtà non abbiamo letto nessuno di questi testi, ma ci stiamo comunque facendo delle osservazioni al riguardo. Bisogna avere piena consapevolezza delle implicazioni di un atto del genere.

* Cosa perde questa forma di lettura?&#x20;
* Cosa guadagna?&#x20;
* Come può essere affrontata in modi che minimizzino il primo e massimizzino il secondo?

Abbiamo toccato con mano, credo, cosa McLuhan intendesse

## Interpretazione

Naturalmente, questi grafici non significano nulla di per sé. È nostro compito guardare i risultati e descriverli in modo significativo. Ma sii critico nei confronti di ciò che vedi. Potresti trovare qualcosa di interessante, ma potresti inferire sciocchezze. Il tuo compito è validare. Fai attenzione all'[apofenia](https://it.wikipedia.org/wiki/Apofenia), l'urgenza umana di guardare dati casuali e trovare schemi significativi in essi. Puoi trovare [modelli selvaggi in qualsiasi cosa](http://tylervigen.com/spurious-correlations) (correlazioni spurie) se guardi non abbastanza attentamente. Dopotutto, le visualizzazioni possono confondere tanto quanto chiarire. Numeri e grafici non hanno un significato oggettivo. [Miriam Posner ](https://twitter.com/miriamkp/status/725764655352684545?ref\_src=twsrc%5Etfw)lo ha riassunto concisamente su Twitter una volta:

![apophenia illustrated - noise illustration](../assets/issues/visual-clarity.jpg)

Pensa sempre. Non lasciare mai che un grafico pensi per te.

## Ulteriori risorse &#x20;

* Big data, digital humanities and Google’s Ngram Viewer: [Discovering hidden patterns of “Truth”](https://firstmonday.org/ojs/index.php/fm/article/view/5567/5535) (trad. : scoprire gli schemi nascosti della "verità").
* Ted Underwood su "[How not to do things with words](https://tedunderwood.com/2012/08/25/how-not-to-do-things-with-words/)" (trad. : cosa non fare con le parole) per utili critiche agli studi che utilizzano Ngram Viewer.
* Danny Sulivan su "[When OCR Goes Bad: Google's Ngram Viewer & The F-Word](https://searchengineland.com/when-ocr-goes-bad-googles-ngram-viewer-the-f-word-59181)" per un approfondimento su Google NGram e l' [OCR](https://it.wikipedia.org/wiki/Riconoscimento\_ottico\_dei\_caratteri).
* Sul concetto di [Linked Data](https://it.wikipedia.org/wiki/Linked\_data) e  [Linked Open Data](http://www.culturaitalia.it/opencms/linked\_open\_data\_it.jsp) e la loro connessione con il [web semantico](https://it.wikipedia.org/wiki/Web\_semantico).
