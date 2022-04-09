---
description: Qui si spiega il nesso tra Topic Modeling e Unsupervised Classification
---

# Un Esempio di Topic Modeling

Nella sezione precedente, è stato descritto come un singolo testo potrebbe essere suddiviso in un elenco di parole con le relative frequenze; abbiamo anche suggerito che un singolo testo potrebbe essere composto da un numero qualsiasi di topic. Possiamo immaginare uno strumento che possa inferire/dedurre questi topic per noi senza che dobbiamo prima leggere tutti i nostri documenti. L'approccio è appunto il **topic modeling**, un metodo computazionale che permette di scoprire i topic che costruiscono un testo. Esso viene realizzato esercitando una varietà di protocolli statistici più e più volte su un testo. L'esecuzione di progetti di topic modeling richiede conoscenze e abilità di programmazione superiori a quelle previste in questo corso introduttivo. Quindi, invece di esercitare le tecniche stesse o offrire uno strumento per farlo, l'obiettivo qui è cercare di descrivere e far intendere meglio cosa il topic modeling sia  e come interpretarne i risultati utilizzando un caso di studio. Se vuoi andare oltre, molto bene: nella sezione _Ulteriori Risorse_ posta sotto, potrai trovare qualche utile approfondimento.

Nella precedente lezione [Bag of Words](bags-of-words.md), abbiamo esaminato un paragrafo e suggerito che, scorrendolo, avresti potuto inferire/dedurre i topic presenti. Il topic modeling funziona in modo simile: il software cerca le parole che tendono a comparire accanto a ciascuna in modi statisticamente significativi. La somma totale di queste parole che ricorrono una accanto all'altra diventa leggibile per un lettore come topic. La lezione precedente ha esaminato un singolo paragrafo ma puoi immaginare come questo si complichi molto rapidamente quando si lavora oltre una scala così piccola. Abbiamno limiti cognitivi e possiamo mantenere solo pochi topic alla volta nel nostro cervello, pochi testi nei nostri pensieri. Un computer non ha lo stesso problema. Il software di modellazione degli argomenti può elaborare centinaia di migliaia di testi, più e più volte, perfezionando il senso di come tutti i pezzi si incastrano. Può darci un'idea dei topic presenti in un intero corpus.

Quindi, quando si esegue un software di topic modeling, eso cerca le parole che ricorrono l'una vicino all'altra nei testi in modi significativi attraverso il corpus caricato. Nella maggior parte dei casi, cerca le parole che ricorrono insieme nei documenti che come ricordi, non dipendono dalla loro posizione all'interno del documento: infatti, il topic modeling funziona su un modello di bag of words a cui importa solo se le parole si trovino o meno all'interno del testo, non la loro posizione al suo interno. Ma occasionalmente potresti suddividere (la parola tecnica è fare **chunk** documenti più grandi in una serie di paragrafi in modo che il software li consideri ciascuno come documenti separati per una maggiore granularità. Esistono numerosi trucchi simili per perfezionare i processi.

Dopo aver fatto l'analisi di topic modeling su un intero corpus, a seconda del software utilizzato, spesso ti verranno fornite molte informazioni che possono essere difficili da analizzare. Tutte queste si sommano ai risultati del tuo progetto. Comunque, il primo step importante, una matrice di topic/parole, conterrà delle linee che si presentano come vedi di seguito:

```
0 2.5 librivox httpupload mp orgshareupload duration mb het de heres van ik size een je en dat te bart voor

1 2.5 file volume audacity problem db files upload edit fix version check dont track click change bit open id computer

2 2.5 text word read words dont make question change made pronunciation didnt point names doesnt understand makes sense long sentence

5 2.5 recording project end librivox post files file number thread section read link completed sections title book complete seconds silence

7 2.5 english years life world language history people american school accent books german french work interesting literature live book written

8 2.5 project page catalog httplibrivox found files link archive audio complete added add cover list links readers google put site
```

Il programma restituisce una serie di topic, che in questo caso sono definiti come insiemi di parole che tendono a comparire insieme nei documenti con una certa significatività statistica. In questi esempi, è stato chiesto al programma di fornirci venti argomenti; il numero identificativo di ogni argomento è il primo numero a sinistra. Nota due cose:&#x20;

1. innanzitutto, i numeri iniziano con 0 e finiscono con 19, invece di iniziare con 1 e terminare con 20;&#x20;
2. in secondo luogo, sono stati selezionati alcuni argomenti da evidenziare rispetto al numero totale; non tutti e venti sono elencati qui.

Dopo i numeri, vedi la serie di parole che compongono quel topic. Il computer non sa nulla di questi topic; si limita a vedere che queste parole spesso coesistono nei documenti.

Il vero lavoro di topic modeling implica l'interpretazione di questi topic in modo da renderli significativi per i lettori. Alcuni sono solo rumori, artefatti di parole che tendono a comparire una accanto all'altra. Ma altri hanno più senso. Sulla base dei topic 1 e 5 potresti essere in grado di dedurre che questi testi particolari provengono da descrizioni di registrazioni sonore di qualche tipo. L'argomento 2 potrebbe suggerire che stiamo parlando di lettura di testi. Gran parte del lavoro  implica il tentativo di formulare ipotesi su quali tipi di discorsi implichinoo questi gruppi di parole. In questo caso, il corpus in questione è di circa 1,8 milioni di post sul forum di [librivox.org](https://librivox.org), un sito che produce audiolibri di pubblico dominio. Tutti gli esempi in questa lezione sono tratti dal lavoro che Brandon ha svolto esaminando appunto questi materiali. Alcuni altri argomenti:

```
11 2.5 recording librivox post test find make start wanted record forum minute thread fun check link listeners things readers give

12 2.5 noise sound recording good bit sounds hear mic voice background microphone record volume silence editing quality loud dont recordings

13 2.5 part read act line parts missing lines play great wrotei id editing role character narrator todd put dramatic edit

14 2.5 section pl mw sections ready uploaded notes fixed corrected updated maryann repeat betty wrotehi wrotesection spot reuploaded pling phil

15 2.5 de la le je les pour pas en vous ne est si ce dans du des merci il mais

17 2.5 ich die und der ist das du von es nicht den auch ein im noch zu wenn kapitel aber

19 2.5 reading read great book listening books reader listen love recordings enjoy forward wonderful listened proof job voice work enjoyed
```

Guardando questi topic, potremmo vedere che alcuni di essi trattano aspetti della registrazione del suono. In particolare, i testi tendono spesso a parlare dell'atto di produrre queste registrazioni. Questo ha senso, poiché gli utenti di LibriVox creano e caricano le registrazioni da soli. Notevoli anche gli argomenti 15 e 17, in quanto rappresentano argomenti di lingua francese e tedesca. In ogni grande corpus che è principalmente una lingua, i testi scritti in altre lingue tenderanno a raggrupparsi. E se ricordi che prima è stato posto in premessa che il linguaggio medico tenderebbe a comparire accorpato, questo ha senso. È molto più probabile che il vocabolario francese appaia accanto ad altro vocabolario francese, in un testo interamente francese, rispetto a un corpus più ampio che è principalmente in inglese.

Per ogni documento nel corpus, il topic modeling restituisce anche una matrice che mostra la percentuale del contributo del topic al testo. La matrice potrebbe contenere centinaia di migliaia di segmenti che assomigliano a questo (modificati leggermente per la leggibilità):

```
0 httpsforum.librivox.orgviewtopic.phpf23t2 
12 0.14788732394366197 
1 0.13380281690140844 
11 0.07746478873239436 
2 0.06338028169014084 
19 0.04929577464788732 
18 0.035211267605633804 
17 0.035211267605633804 
16 0.035211267605633804 
15 0.035211267605633804 
14 0.035211267605633804 
13 0.035211267605633804 
10 0.035211267605633804 
9 0.035211267605633804 
8 0.035211267605633804 
7 0.035211267605633804 
6 0.035211267605633804 
5 0.035211267605633804 
4 0.035211267605633804 
3 0.035211267605633804 
0 0.035211267605633804 
```

La prima riga qui contiene informazioni sul documento, un ID (elemento identificativo) per il documento e quindi un nome per esso. In questo caso, ogni post del forum ha il proprio URL, quindi stiamo usando l'URL come ID:

```
0 httpsforum.librivox.orgviewtopic.phpf23t2
```

Questo sopra è il post numero 0, il primo post riportato dal software di topic modeling. Brandon ha eliminato parte della punteggiatura, ma probabilmente riconosci quello che segue come una sorta di URL. Questa informazione corrisponde ad un post del forum che esiste a questo URL: [https://forum.librivox.org/viewtopic.php?f=23\&t=2](https://forum.librivox.org/viewtopic.php?f=23\&t=2). Quello che segue invece è un elenco di ogni argomento prodotto dal nostro software di modellazione degli argomenti e il peso di ciascun argomento per quel documento:

```
12 0.14788732394366197
1 0.13380281690140844
11 0.07746478873239436
17 0.035211267605633804
15 0.035211267605633804
```

So topics 12, 1, and 11, in that order, are the three most prominent topics in the document. Topic 12 has a weight of 14% in the document, and so on. Topic 12 is far more likely to appear in this document than topics 17 and 15. Using this information, if we know the dates that each text was published, we can actually determine the rise and fall in prominence of different topics over time (see the Further Resources on this page for cautions when doing so). We could see how discourse ebbs and flows over the course of our corpus. Remember topics 15 and 17, our German and French language topics? They aren't especially prominent in this first text, which makes sense because it was written in English. There is a pretty low likelihood that German or French words are going to show up in an otherwise English text, all things considered. But we can use this information to get a sense of where French and German texts are likely to occur by charting the ebb and flow of the French and German topics over time:

Quindi i topic 12, 1 e 11, in quest'ordine, sono i tre topic più importanti nel documento. Il topic 12 ha un peso del 14% nel documento e così via. È molto più probabile che il 12 appaia in questo documento rispetto al 17 e al 15. Utilizzando queste informazioni, se conosciamo le date in cui ciascun testo è stato pubblicato, possiamo effettivamente determinare l'ascesa e la diminuzione di importanza di diversi topic nel tempo (vedi Ulteriori Risorse in questa pagina per le precauzioni da usare nel farlo). Abbiamo potuto vedere come il discorso fluisce e rifluisce nel corso del nostro corpus. Ricordi gli argomenti 15 e 17, i nostri argomenti in lingua tedesca e francese? Non sono particolarmente importanti in questo primo testo, il che ha senso perché è stato scritto in inglese. C'è una probabilità piuttosto bassa che le parole tedesche o francesi vengano visualizzate in un testo altrimenti inglese, tutto sommato. Ma possiamo usare queste informazioni per avere un'idea di dove è probabile che si trovino i testi francesi e tedeschi tracciando il flusso e riflusso degli argomenti francesi e tedeschi nel tempo:

![Topic modeling di testi in francese e tedesco in diacronia](../assets/topic-modeling/topic-modeling-french-german.jpg)

Otteniamo picchi evidenti del topic in tedesco da settembre a dicembre 2014 e picchi leggermente inferiori di quello in francese alla fine del 2007 e 2008. Poiché sappiamo che questi argomenti rappresentano approssimazioni piuttosto coerenti dell'uso della lingua francese e tedesca nel corpus, possiamo usare tecniche come queste per sostenere che questi momenti particolari rappresentano periodi di intensa attività da parte delle comunità francese e tedesca tra gli utenti di LibriVox. Sulla base di queste prove, potremmo argomentare sull'interconnessione globale della comunità degli utenti di LibriVox. Potremmo quindi riportare queste informazioni nel corpus e porre nuove domande sulla base di questi dati.

* Che tipo di libri sono importanti per queste comunità?&#x20;
* Che tipo di conversazioni stanno avendo?&#x20;
* Perché queste lingue aumentano in questi momenti particolari?

Fino ad ora, abbiamo sottolineato la necessità di avere un approccio all'analisi del testo avendo chiari i nostri interessi e le domande di ricerca che li guidano. Va invece osservato che il topic modeling funziona in modo leggermente diverso: è più utile nella fase esplorativa. Tecnicamnete il topic modeling  viene definito **unsupervised classification** ovvero classificazione non supervisionata, perché chiediamo al computer di analizzare e contrassegnare un testo senza dargli indicazioni chiare. Diciamo solo "Ecco del testo. Fai le tue cose e dimmi cosa trovi". Una tecnica detta **supervised classification**, **** ovvero classificazione supervisionata, prenderebbe informazioni da noi per aiutare il computer a prendere decisioni. Potremmo dire: "Leggi questo testo. Se ha più di cinquanta usi della parola 'crimine', segnalalo come 'narrativa poliziesca.' Se ha cinquanta usi della parola "amore", contrassegnalo come 'romanticismo'" (ulteriori informazioni sui classificatori supervisionati saranno presenti nel prossimo capitolo). Classificatori non supervisionati come il topic modeling, invece, sanno molto poco dei testi sottostanti che stanno esaminando. Invece, li elaborano in base a un modello sottostante.

Nell'ultima lezione si è osservato che il modello **bag of words**  rappresenta un'epistemologia dei testi, un modo di intendere i documenti che potrebbe essere diverso da quello con cui finora hai avuto familiarità. Per la precisione il tipo di topic modeling  di cui qui abbiamo discusso, viene chiamato **Latent Dirichlet Allocation (LDA)**. Non entreremo nei dettagli sulle specifiche del LDA, ma è importante sapere che questo è il modello con cui stai lavorando e che LDA presuppone che un testo sia costruito da un numero limitato di topic.

Non allarmarti se il topic modeling ti sembra molto più astratto del materiale che abbiamo trattato fino ad ora. Per capire davvero come funzioni, dovrai avere una conoscenza di una varietà di argomenti diversi specifici del machine learning e della statistica. E qui non si pretende che tu capisca queste specifiche. E' importante,  invece, che tu comprenda l'idea alla base, che tu abbia colto cosa sia e come funzioni il topic modeling e che tu sia in grado di spiegarli ad altri seppure in termini generali.

### Sintesi

Proviamo ora a fare una sintesi.

Il **Topic Modeling** è un'azione legata al **NLP (Natural Language Processing**); prevede forme di **Unsupervised Analysis** che non hanno bisogno di dataset etichettati. Usa tecniche di Latent Semantic Analysis (LSA) e  **LDA (Latent Dirichlet Allocation)**. Noi abbiamo esplorato la seconda.

## Ulteriori risorse

* Andrew Goldstone and Ted Underwood un interessante studio di caso di [topic modeling ](https://andrewgoldstone.com/blog/2012/12/13/pmla/)[_PMLA_](https://andrewgoldstone.com/blog/2012/12/13/pmla/) che include anche una utile introduzione al topic modeling.
* [Topic Modelling for Absolute Beginners](https://thedigitalskye.com/2020/11/07/topic-modelling-for-absolute-beginners/)
* Il Programming Historian offre una  [buona introduzione](http://programminghistorian.org/lessons/topic-modeling-and-mallet) al topic modeling usando Mallet. E' tecnico ma molto utile.
* Per una spiegazione più approfondita di come funziona l'algoritmo alla base del topic modeling, potresti dare un'occhiata all'[esercizio in classe di Lisa Rhody](https://github.com/lmrhody/topicmodelgame) per insegnare LDA.
* Miriam Posner è molto utile per  [comprendere i risultati di topic modeling](http://miriamposner.com/blog/very-basic-strategies-for-interpreting-results-from-the-topic-modeling-tool/).
* Benjamin Schmidt in "[Words Alone: Dismantling Topic Modeling in the Humanities](http://journalofdigitalhumanities.org/2-1/words-alone-by-benjamin-m-schmidt/#appendix)" fornisce una valida disamina sulle precauzioni da usare  quando si lavora con il tipic modeling nel tempo.
* Fabio Ciotti, [What's in a Topic Model? Critica teorica di un metodo computazionale per l’analisi del testo. Testo & Senson.18, 2017](https://testoesenso.it/index.php/testoesenso/article/view/370/pdf\_227). L'interessante articolo si propone di affrontare criticamente, i fondamenti teorici di una nozione e di un metodo che sono oggi molto diffusi negli studi letterari computazionali, il topic modeling, appunto, inteso come l'individuazione statistico/probabilistica dei cluster lessicali che caratterizzano un insieme di testi, e l'analisi delle loro distribuzioni. Quando parla di fondamenti teorici si riferisce al ruolo che tale nozione può giocare nel contesto di una teoria del testo e di una metodologia della critica letteraria, e non ai suoi aspetti puramente matematici, che sono ovviamente saldamente basati sulla statistica e sulla teoria della probabilità bayesiana. Dopo una descrizione dei fondamenti tecnici della nozione di topic modelling procede a confrontare tale nozione con alcuni suoi possibili correlati in ambito teorico letterario, evidenziando i limiti di ogni possibile identificazione.
