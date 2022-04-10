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

Just like we did with [Voyant](../reading-at-scale/voyant-part-two/), Jockers breaks the novel into a number of segments and aggregates the sentiment for each section to get a sense of how the emotion changes over time. At its core, measuring sentiment computationally in this way relies on solid training data. The computer needs to learn how to map emotion-laden words and phrases onto some sort of numerical system. The robustness of your training set can strengthen or complicate your results. Getting a good training set can be difficult, however, since assembling one takes a great deal of time and labor. Notably, it is a lot of work to manually label single words with positive or negative valence. With a series of values like these for each text, Jockers then has a basis for comparison among his whole corpus. He can start to look for patterns in plot trajectories, which eventually leads to his claim that there are only a set number of plot arcs for novels.

Proprio come abbiamo fatto con [Voyant](https://voyant-tools.org), Jockers suddivide il romanzo in una serie di segmenti e aggrega il sentiment per ciascuna sezione per avere un'idea di come l'emozione cambia nel tempo. Fondamentalmente, misurare il sentiment in modo computazionale si basa su solidi dati di allenamento. Il computer deve imparare a mappare parole e frasi cariche di emozioni su una sorta di sistema numerico. La robustezza del tuo set di allenamento può rafforzare o complicare i tuoi risultati. Tuttavia, ottenere un buon set di allenamento può essere difficile, poiché assemblarne uno richiede molto tempo e lavoro. In particolare, è molto impegnativo etichettare manualmente singole parole con valenza positiva o negativa. Comunque, con una serie di valori come questi per ogni testo, Jockers ha costruito quindi una base di confronto di tutto il suo corpus. Ha cercato schemi nelle traiettorie della trama, il che alla fine  lo ha portato ad affermare che  i romanzi presentano un numero di archi narrativi determinato.

## EmojiSentiment

Another interesting use of sentiment analysis is [EmojiSentiment](http://www.emojisentiment.com/#About). The project approaches the problem from a different angle: rather than trying to analyze textual content for sentiment, the site postulates that emojis embedded in tweets might be a good predictor of their sentiment. There are only around 2000 emoji and only a small subset have emotional valences to them; tagging these emojis is a lot easier than tagging all the words that convey emotion. The authors of this project use emojis to determine the overall sentiment for particular hashtag, as opposed to any one tweet. The project postulates that if you gather up all the emoji associated with a particular hashtag, you will get a pretty good sense of the emotional valence for that stream of conversation. For example, EmojiSentiment reads #friday as being relatively positive:

![friday sentiment](../assets/sentiment-analysis/emoji-sentiment-friday.jpg)

On first blush, this makes sense. Everyone gets excited for the weekend. But look more closely. The three most dominant emoji are fire, police sirens, and flowers, which might seem a bit unusual. Note that we're only getting 32 emoji in the last 1000 tweets - these might just be artifacts of whatever is going right now, and the project can't handle more volume than that (it's a student project. Yay students!). So our sample size is rather small and could easily be skewed by a handful of active users. We would want far more emoji to really get a good measurement of sentiment. If #friday got a relatively happy average sentiment, #angry is much more negative:

![angry sentiment](../assets/sentiment-analysis/emoji-sentiment-angry.jpg)

Note how even #angry just barely dips below 50 to be predominantly negative. We actually had to search around for a while to find a hashtag that read as predominantly negative. Could this be a function of language - are people just happier than they are sad? Certainly not. This might have to do with how we represent our emotions on social media; maybe we don't use emojis to represent negative emotions that often. Or maybe sentiment analysis by way of computation is imprecise at best. To improve on this project, we would want to scale it up to read vastly more data. We might then use the emoji a tad differently. Instead of using them to measure sentiment, you could use them to train the sentiment classifer further so that it refines itself over time! All of this would require far more funding than the EmojiSentiment team has, however, and the tool is a great provocation as it stands.

* What might you imagine using sentiment analysis for?
* What kinds of texts lend themselves especially well to reading for emotion?

## Ulteriori Risorse

* Scopri come acquisire i dati di Twitter ed elaborarli per renderli utilizzabili per ulteriori analisi: [Beginner's Guide to Twitter Data](https://programminghistorian.org/en/lessons/beginners-guide-to-twitter-data).
