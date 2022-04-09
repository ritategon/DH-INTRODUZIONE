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

sostituisci con questo [https://towardsdatascience.com/no-fear-stylometry-with-expert-ai-163892fd234](https://towardsdatascience.com/no-fear-stylometry-with-expert-ai-163892fd234)  o questo [https://computationalstylistics.github.io/stylo\_nutshell/](https://computationalstylistics.github.io/stylo\_nutshell/) con qiuesto [https://journal.r-project.org/archive/2016/RJ-2016-007/RJ-2016-007.pdf](https://journal.r-project.org/archive/2016/RJ-2016-007/RJ-2016-007.pdf) e [http://dh2013.unl.edu/abstracts/ab-136.html](http://dh2013.unl.edu/abstracts/ab-136.html)

To illustrate this experiment, we took two authors from our syllabus: Danielle Bowler and Pia Glenn. Using their author pages on [Eyewitness News](http://ewn.co.za/Contributors/Danielle-Bowler) and [xoJane](http://www.xojane.com/author/pia-glenn), we gathered articles that belonged to each. Bowler tends to write shorter pieces than Glenn, so our training set included about double the number of pieces by Bowler (10) as by Glenn (5). With this body of training data for each author, we uploaded the texts to a great online [authorship attribution tool](http://aicbt.com/authorship-attribution/online-software/) by AICBT. The tool allows you to upload sample data for two authors. With this set, you can then upload a text by an unknown author, and the software will try to guess who wrote it based on a variety of text analysis protocols. In this case, the mystery text was "[Freedom, Justice, and John Legend](http://ewn.co.za/2015/02/23/OPINION-Danielle-Bowler-Freedom-justice-and-John-Legend)" by Bowler. Author 1 is Glenn, and Author 2 is Bowler. The tool attempted to identify the author of the mystery text as follows. The images also include AICBT's helpful explanation of the different metrics that they are using to analyze the unknown text.

Per illustrare questo esperimento, abbiamo preso due autori dal nostro programma: Danielle Bowler e Pia Glenn. Usando le loro pagine degli autori su [Eyewitness News](https://ewn.co.za/Contributors/Danielle-Bowler) e xoJane, abbiamo raccolto articoli che appartenevano a ciascuno. Bowler tende a scrivere pezzi più brevi di Glenn, quindi il nostro set di allenamento includeva circa il doppio del numero di pezzi di Bowler (10) e di Glenn (5). Con questo corpo di dati di formazione per ciascun autore, abbiamo caricato i testi su un ottimo strumento di attribuzione della paternità online di AICBT. Lo strumento consente di caricare dati campione per due autori. Con questo set, puoi quindi caricare un testo di un autore sconosciuto e il software proverà a indovinare chi lo ha scritto in base a una varietà di protocolli di analisi del testo. In questo caso, il testo del mistero era "Libertà, giustizia e John Legend" di Bowler. L'autore 1 è Glenn e l'autore 2 è Bowler. Lo strumento ha tentato di identificare l'autore del testo del mistero come segue. Le immagini includono anche l'utile spiegazione di AICBT delle diverse metriche che stanno utilizzando per analizzare il testo sconosciuto.

![authorship function](../assets/classifiers/authorship-function.jpg) ![authorship lexical](../assets/classifiers/authorship-lexical.jpg) ![authorship diversity](../assets/classifiers/authorship-punctuation.jpg)

This text is actually by author 2, so for the classifier to be accurate according to these measures, the arrow should point towards the right. You'll immediately see that we have some success, but also one failure! Function word analysis is a slight indicator of the correct author, lexical analysis is virtually useless, and punctuation analysis is way _wrong_. In a real classification project, we would want to use the success or failure of our classifier to revise our sense of which features are useful for our particular project. In this case, punctuation is not a good measure at all, so we would throw that out. Instead, we might focus on function words as an indicator of authorship. We can tweak our approach accordingly. But measures like these are only ever working probabilistically. We can say that the mystery text _might_ be written by our second author, but only in rare cases could we ever know for certain.

Note also how these measures of authorship overlap with other things we have studied in this book. Remember stopwords, those words that are so common in a text that they are frequently removed before text analysis? In cases like this one, we actually care a lot about these simple terms. Two of the three measures for authorship here deal with just those words that we might otherwise throw away: punctuation, articles, etc. These words might not tell you much about the subject of a text, but they can tell you an awful lot about _how_ a text discusses them.

Take a text that we've talked a lot about in this course: _The String of Pearls_. This penny dreadful was published in weekly installments and was written (we think) by James Malcolm Rymer and Thomas Peckett Prest. But the work was published anonymously, so we don't know which author wrote which chapter (or even if Rymer and Prest wrote the novel).

For the purposes of this demonstration, let's assume that we know that Rymer wrote Chapter One and Prest wrote Chapter Two. So who wrote Chapter Thirty-Three? If we go back to our author attribution tool and copy Chapter One into the box for Author 1 and Chapter Two into the box for Author 2, here's what we get for Chapter Thirty-Three:

!\[]\(/assets/Screen Shot 2016-08-25 at 10.33.39 AM.jpg)

!\[]\(/assets/Screen Shot 2016-08-25 at 10.33.54 AM.jpg)

!\[]\(/assets/Screen Shot 2016-08-25 at 10.34.08 AM.jpg)

Here, it looks like the tool is trending towards Rymer as the author of the chapter, but we're mainly dealing with uncertainty. But that uncertainty itself is pretty interesting! Maybe what this is showing us is that the authors had a pretty similar style. Or maybe both authors had a hand in each chapter, and our training set is not particularly useful. If we had large bodies of text by each author we might have better luck. We might want to drill down further and investigate the uses of puncutation in different chapters or the lexical diversity, word length, and sentence length in much more detail.

* Are other penny dreadfuls similar to _The String of Pearls_ in these respects?
* If so, what differentiates the style of these works from other types of serial novels?

Similar processes have been used for a variety of authorship attribution cases. The most famous one in recent times is probably that of Robert Galbraith, who came out with _The Cuckoo's Calling_ in 2013. Using a similar process of measuring linguistic similarity, Patrick Juola was able to test a hypothesis that J.K. Rowling had released the detective novel under a pseudonym. You can read more about the process [here](http://www.scientificamerican.com/article/how-a-computer-program-helped-show-jk-rowling-write-a-cuckoos-calling/).

If we can measure it, we can test it. And you would be surprised at just how many humanities-based research questions we can measure. Taking complicated human concepts like authorship and breaking them down into quantifiable pieces is part of the fun. It is also what makes the process intellectually interesting. If it were easy, it would be boring.

We have just barely scratched the surface of the field of **stylometry**, or the study of linguistic style using a variety of statistical metrics. You can carry this research process using a variety of programming languages, so you might take a look at our concluding chapter on [Where to Go Next](../conclusion/where-to-go.md) if you are interested in learning how to implement these sorts of experiments yourself.



### Text Classification con Deep Learning

prendi da qua ess [https://monkeylearn.com/text-classification-examples/](https://monkeylearn.com/text-classification-examples/) [https://monkeylearn.com/text-classification/#:\~:text=Deep%20learning%20architectures%20offer%20huge,Recurrent%20Neural%20Networks%20(RNN).](https://monkeylearn.com/text-classification/#:\~:text=Deep%20learning%20architectures%20offer%20huge,Recurrent%20Neural%20Networks%20\(RNN\).)

poi metti come ess guidato per il greco ithaca [https://ithaca.deepmind.com/](https://ithaca.deepmind.com) prima con questo e poi con drive [https://colab.research.google.com/drive/1Pef1Q-lteXLYxBFT2Zd6t9kfu-7rekyY#scrollTo=hnK8uNKnDZlD](https://colab.research.google.com/drive/1Pef1Q-lteXLYxBFT2Zd6t9kfu-7rekyY#scrollTo=hnK8uNKnDZlD)  fonti usabili [https://epigraphy.packhum.org/](https://epigraphy.packhum.org)
