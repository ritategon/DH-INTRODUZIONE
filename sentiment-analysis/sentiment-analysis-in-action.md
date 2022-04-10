# Sentiment Analysis in azione

Per illustrare come funzioni la sentiment analysis, esaminiamo un paio di progetti diversi. Ci sarà  una buona dose di riferimenti ai dettagli tecnici, ma lo scopo è che tu ti faccia   un'idea del tipo di lavoro che ci sta sotto.

## Jockers and Syuzhet

{% hint style="info" %}
[Jockers](https://www.matthewjockers.net) è un accademico che si è focalizzato sull'approccio computazionale e ai testi.&#x20;

[Syuzhet](https://cran.r-project.org/web/packages/syuzhet/vignettes/syuzhet-vignette.html) è un pacchetto di NLP (Natural language Processing) per il linguaggio [R](https://www.r-project.org/about.html).
{% endhint %}

[Matt Jockers](https://www.matthewjockers.net/2015/02/02/syuzhet/) ha lavorato sull'utilizzo della sentiment analysis per scoprire le traiettorie della trama nella fiction proprio negli stessi termini del video della lezione precedente. Prendendo migliaia di testi e classificando le loro frasi in base al sentiment, ha sviluppato una procedura software per tracciare le traiettorie della trama e ha suggerito che ci sono solo sei o sette forme di trama diverse basate su questo tipo di analisi. L'audace affermazione di Jockers è stata da allora oggetto di seria critica da parte di [Joanna Swafford](https://annieswafford.wordpress.com/2015/03/02/syuzhet/), che sostiene che le forme sono il risultato di configurazioni nel software di Jockers piuttosto che di qualsiasi qualità intrinseca nel testo. Questo è un tema ricorrente anche in questo libro ed viene riportato per ribadire che metodi e strumenti sono in progress e comportano dei limiti.

Diamo un'occhiata più da vicino a come Jockers è in grado di fare una tale affermazione. Usa un sofisticato pacchetto software che ha costruito nel linguaggio di programmazione R. Non entreremo nei dettagli del codice stesso, ma possiamo coprire l'approccio generale.&#x20;

Il progetto di Jockers combina classificatori supervisionati e classificatori non supervisionati. Ricorda: i classificatori supervisionati si basano sui dati di addestramento che indicano al software come interpretare e classificare i dati. I classificatori non supervisionati non si basano su alcun dato di addestramento precedente. Al contrario, si basano su presupposti e algoritmi sottostanti per classificare i testi (nel caso della modellazione di argomenti, ciò significa che i classificatori non supervisionati fanno ipotesi sulla relazione tra testi e statistiche). Di seguito ci concentreremo sulla parte supervisionata del suo lavoro.

Quindi, in primo luogo, Jockers aveva bisogno di dati di addestramento. Affinché il suo software leggesse i sentiment nelle frasi, aveva bisogno di frasi di esempio che erano già state contrassegnate per le emozioni. Fornendo al software frasi di esempio, il software riesce poi a classificare le  frasi che si presentano.Quindi immagina di addestrare il nostro computer con queste frasi:

1. "I am happy!" (Sono felice), positivo
2. "I am sad!" (Sono triste), negativo

Successivamente, accendiamo il nostro classificatore e gli chiediamo di contrassegnare un determinato testo in base al sentiment. Immagina che il computer incontri di nuovo la frase 1 più avanti nel testo. Il computer potrebbe guardare nella sua banca di conoscenze e ricordare che dovrebbe essere contrassegnato come positivo. Ma questo classificatore non funzionerebbe molto bene: conosce solo il sentimento per due frasi specifiche. Quando incontra nuove frasi che non abbiamo premarcato, non saprebbe cosa fare. In pratica, vogliamo addestrare un classificatore su quanti più dati possibile per massimizzare la sua capacità di gestire nuove informazioni. E probabilmente non lo addestreremo su frasi intere. Dopotutto, i computer distinguono tra frasi e singole parole in modi abbastanza profondi (ne abbiamo parlato in [Come un computer legge un testo computer](../cyborg-readers/computer-reading.md)). A seconda di quanto vogliamo essere approfonditi, potremmo invece fornire al computer il vocabolario e le frasi contrassegnate per sentiment. Poiché lavorare con i numeri ci offre più opzioni per rappresentare graficamente le cose, potremmo usare "1" e "-1" per rappresentare frasi con valori positivi e negativi. E piuttosto che con un binario positivo/negativo, potremmo tracciare un continuum: numeri compresi tra -5 e 5, diciamo. Dopotutto, "buono" è meno positivo di "esuberante". Quindi ogni parola o frase viene convertita in una serie di numeri positivi e negativi.

Puoi trovare informazioni sui set di allenamento utilizzati da Jockers [qui](https://github.com/mjockers/syuzhet#references). Usa un lessico di formazione tutto suo, ma offre la possibilità di classificare il sentiment usando altri _training set_. Fondamentalmente il software legge un testo, esamina la memoria del corpus di addestramento per determinare quanto sia positiva o negativa una frase o una parola, quindi converte il testo in una serie di valori come questo:

```
2.50 0.60 0.00 -0.25 0.00 0.00
```

Ora il testo viene convertito in una serie di valori che rappresentano il sentiment del testo. Quando i numeri del testo diventano negativi o positivi, abbiamo un'idea di come il classificatore legga le emozioni del testo. Da lì, si tratta solo di tracciare i numeri per ottenere una migliore rappresentazione delle tendenze del sentiment nel tempo. Alla fine, possiamo ottenere qualcosa di simile a questo grafico per _A Portrait of the Artist as a Young Man_ di James Joyce, tratto dalla spiegazione del software di Jockers:

![Traiettoria della trama inel Portrait](../assets/sentiment-analysis/jockers-portrait.jpg)

Proprio come abbiamo fatto con [Voyant](https://voyant-tools.org), Jockers suddivide il romanzo in una serie di segmenti e aggrega il sentiment per ciascuna sezione per avere un'idea di come l'emozione cambia nel tempo. Fondamentalmente, misurare il sentiment in modo computazionale si basa su solidi dati di allenamento. Il computer deve imparare a mappare parole e frasi cariche di emozioni su una sorta di sistema numerico. La robustezza del tuo set di allenamento può rafforzare o complicare i tuoi risultati. Tuttavia, ottenere un buon set di allenamento può essere difficile, poiché assemblarne uno richiede molto tempo e lavoro. In particolare, è molto impegnativo etichettare manualmente singole parole con valenza positiva o negativa. Comunque, con una serie di valori come questi per ogni testo, Jockers ha costruito quindi una base di confronto di tutto il suo corpus. Ha cercato schemi nelle traiettorie della trama, il che alla fine  lo ha portato ad affermare che  i romanzi presentano un numero di archi narrativi determinato.

## EmojiSentiment

Un altro uso interessante dell'analisi del sentimento è [EmojiSentiment](http://kt.ijs.si/data/Emoji\_sentiment\_ranking/emojimap.html). Il progetto ([qui](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0144296) puoi vedere la ricerca di riferimento)affronta il problema da un'angolazione diversa: piuttosto che cercare di analizzare il contenuto testuale per il sentimento, il sito postula che gli emoji incorporati nei tweet potrebbero essere un buon predittore del loro sentimento. Ci sono solo oltre 2000 emoji e solo un piccolo sottoinsieme ha valenze emotive; taggare questi emoji è molto più facile che taggare tutte le parole che trasmettono emozioni. Gli autori di questo progetto utilizzano gli emoji per determinare il sentiment generale per un particolare hashtag, rispetto un qualsiasi tweet. Il progetto postula che se si raccolgono tutte le emoji associate a un particolare hashtag, si ottiene un senso adeguato della valenza emotiva per quel flusso di conversazione. Ad esempio, EmojiSentiment in questo caso legge #friday come relativamente positivo:

![friday sentiment](../assets/sentiment-analysis/emoji-sentiment-friday.jpg)

{% hint style="info" %}
[Qui](https://home.unicode.org/emoji/emoji-frequency/) puoi esplorare autonomamente la frequenza.

[Qui](http://kt.ijs.si/data/Emoji\_sentiment\_ranking/index.html) il ranking ed altro.

[Qui](http://emojitracker.com) un tracker in tempo reale.
{% endhint %}

A prima vista, questo ha senso. Tutti si emozionano per il fine settimana. Ma guarda più da vicino. Le tre emoji dominanti sono fuoco, sirene della polizia e fiori, che potrebbero sembrare un po' insoliti. Nota che stiamo ricevendo solo 32 emoji negli ultimi 1000 tweet: questi potrebbero essere solo artefatti di qualsiasi cosa stia succedendo in questo momento e il progetto non può gestire un volume maggiore di quello. Quindi la nostra dimensione del campione è piuttosto piccola e potrebbe essere facilmente distorta da una manciata di utenti attivi. Vorremmo molte più emoji per ottenere davvero una buona misurazione del sentimento. Se il #venerdì ha un sentimento medio relativamente felice, #arrabbiato è molto più negativo:

![angry sentiment](../assets/sentiment-analysis/emoji-sentiment-angry.jpg)

Nota come anche #arrabbiato scenda a malapena sotto 50 per essere prevalentemente negativo. In realtà abbiamo dovuto cercare un po' per trovare un hashtag che fosse letto come prevalentemente negativo. Potrebbe essere una funzione del linguaggio: le persone sono semplicemente più felici di quanto siano tristi? Certamente no. Questo potrebbe avere a che fare con il modo in cui rappresentiamo le nostre emozioni sui social media; forse non usiamo gli emoji per rappresentare le emozioni negative così spesso. O forse l'analisi del sentiment attraverso il calcolo è nella migliore delle ipotesi imprecisa. Per migliorare questo progetto, potremmo potenziarlo per leggere molti più dati. Potremmo quindi usare l'emoji in modo leggermente diverso. Invece di usarli per misurare il sentiment, si potrebbero usare per addestrare ulteriormente il classificatore del sentiment in modo che si perfezioni nel tempo! Tutto ciò richiederebbe tuttavia molti più finanziamenti rispetto al team di EmojiSentiment e lo strumento è già una grande provocazione così com'è.

* Per cosa potresti immaginare di usare la sentiment analysis?&#x20;
* Quali tipi di testi si prestano particolarmente bene alla lettura delle emozioni?

## Ulteriori Risorse

* Scopri come acquisire i dati di Twitter ed elaborarli per renderli utilizzabili per ulteriori analisi: [Beginner's Guide to Twitter Data](https://programminghistorian.org/en/lessons/beginners-guide-to-twitter-data).
