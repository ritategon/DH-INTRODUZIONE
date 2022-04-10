# Bags of Words

{% hint style="info" %}
(Non è necessario, ma  prima di cominciare potresti voler capire meglio il significato della locuzione **Bags of Words** e che direzione stiamo prendendo. Nel caso vedi [qui](https://it.wikipedia.org/wiki/Modello\_della\_borsa\_di\_parole)).
{% endhint %}

{% hint style="info" %}
La parola **topic** che significa argomento, ad un certo punto non verrà più tradotta, ma lasciata per il suo riferimento specifico ad una serie di tecniche di analisi testuale.
{% endhint %}

Quando leggiamo, i nostri occhi si muovono in sequenza sulla pagina e prendono le frasi  una dopo l'altra nell'ordine in cui sono state concepite. Ciò ci consente di fare cose interessanti rappresentando graficamente le parole nel tempo usando [Voyant](https://voyant-tools.org). Questo senso della cronologia è parte integrante del modo in cui noi, come lettori umani, comprendiamo i testi. Ma è possibile immaginare altri modi di leggere. Hai mai sfogliato una pagina guardando le parole all'indietro? Probabilmente hai ugualmente colto l'essenza del testo anche se non l'hai letto in ordine e anche se hai perso molte parole.

Prendi questo passaggio:

> I will, for the sake of argument, assume that the information given to the coroner by the officer of one of the medical schools is correct, and that Dr. Phillips is right in considering that the character of the mutilation in question justifies the assumption that the perpetrator was probably one who possessed some knowledge of anatomy. But that the inference which has been deduced is warranted, any one who is the least acquainted with medical science and practice will unhesitatingly deny and indignantly repudiate. That a lunatic may have desired to obtain possession of certain organs for some insane purpose is very possible, and the theory of the murdering fiend being a madman only derives confirmation from the information obtained by the coroner. But that the parts of the body carried off were wanted for any quasi scientific publication, or any other more or less legitimate purpose, no one having any knowledge of medical science will for a moment believe.
>
> (Traduzione: Per amor di discussione, presumerò che le informazioni fornite al medico legale dall'ufficiale di una delle scuole di medicina siano corrette e che il dottor Phillips abbia ragione nel ritenere che il carattere della mutilazione in questione giustifichi l'assunto che l'autore sia stato probabilmente uno che possedeva una certa conoscenza dell'anatomia. Ma che l'inferenza che è stata dedotta sia giustificata, chiunque abbia meno familiarità con la scienza e la pratica medica negherà senza esitazione e ripudierà con indignazione. Che un pazzo possa aver desiderato ottenere il possesso di determinati organi per qualche folle scopo è molto probabile, e la teoria secondo cui il demone assassino è un pazzo deriva solo dalla conferma delle informazioni ottenute dal medico legale. Ma che le parti del corpo portate via fossero ricercate per qualsiasi pubblicazione quasi scientifica, o per qualsiasi altro scopo più o meno legittimo, nessuno che abbia alcuna conoscenza della scienza medica lo crederà per un momento.)

Il testo è tratto da una  [lettera](https://www.casebook.org/press\_reports/pall\_mall\_gazette/18880928.html) connessa con gli omicidi di Jack lo Squartatore pubblicata dalla _Pall Mall Gazette_ il 28 settembre 1888. Anche senza sapere nulla del contesto, probabilmente si può dedurre un senso approssimativo del **topic/argomento** del testo: l'omicidio. Potremmo inoltre dire che ci sono una serie di argomenti sovrapposti nel testo: prove, medicina, omicidio e molti altri. Ma come hai riconosciuto questi temi nel paragrafo? Se avessi sfogliato il testo, alcune parole potrebbero essere saltate fuori per indicare questi argomenti. Vedi le parole "coroner" e "body" e queste parole suggeriscono cose particolari e non altre. Ti fanno pensare: "Questo articolo riguarda il crimine o la medicina". Non ti fanno pensare "Oh, sto leggendo una ricetta per un buon guacamole". Il vocabolario sono gli elementi costitutivi dei temi in un passaggio e possiamo, in teoria, determinare gli argomenti al lavoro in un testo prestando molta attenzione al tipo di parole che vi compaiono. Ecco lo stesso passaggio con una rappresentazione di come il processo di lettura di questo articolo potrebbe aver avuto luogo usando [_Prism_](https://prism.scholarslab.org). Abbiamo evidenziato varie parole associate a categorie particolari:

```
Highlight Color: Topic
---
red: evidence
green: medicine
blue: murder
black: words where two or more topics were marked the same amount.
grey: no topic marked
```

![Elementi di evidenza di topic modeling ](../assets/topic-modeling/topic-modeling-highlights.jpg)

Questo è un modello visivo di come potremmo leggere il testo. In questo esempio, ciascuno di questi colori rappresenta un tipo diverso di **topic/argomento** che il testo tratta. Ogni topic è composto da discorsi particolari: un linguaggio legato alla dimostrazione delle cose, un vocabolario legato alla medicina e una serie di parole sul crimine. Altri articoli di giornale su Jack lo Squartatore potrebbero presentare una serie diversa di temi. L'argomento degli articoli potrebbe cambiare, il vocabolario rifletterebbe questo e la nostra percezione degli argomenti sottostanti cambierebbe di conseguenza. Probabilmente la maggior parte di questi testi tratta del crimine, ma potresti avere alcuni articoli di Jack lo Squartatore incentrati sulle vittime o sulle indagini della polizia sugli omicidi.

Dai un'occhiata più da vicino ai tipi di parole che abbiamo evidenziato nell'articolo sopra. Alcune parole potrebbero essere davvero buoni indicatori di un particolare argomento, mentre altre potrebbero essere indicatori più sfocati di ciò di cui stiamo parlando. Ad esempio, sebbene la parola "practice" possa apparire nelle conversazioni sia sulla medicina che sullo sport, una parola come "anatomy" è più strettamente e chiaramente indicativa di un topic scientifico.&#x20;

Non sarebbe interessante se potessimo in qualche modo vedere l'intera rete di topic che si verificano in un testo? E se potessimo scoprire come appaiono topic diversi in testi diversi e il grado in cui li discutono, potremmo trovare modi per operare delle distinzioni tra testi.

Un problema con l'utilizzo di _Prism_ per fare questo lavoro è che dipende da qualcuno che imposta in anticipo questi topic e quindi, in sostanza, conosce o indovina qualcosa sul testo prima che inizi il processo di analisi del testo. Ma forse ci sono dei topic nascosti nel testo che non sappiamo nemmeno cercare o non ci viene in mente. E se potessimo usare i computer non solo per distinguere i testi in base ai topicche trattano, ma anche per trovare i topic stessi?&#x20;

Stiamo iniziando a fluttuare in un diverso tipo di lettura. Facciamo, però, un altro passo indietro.

Se prendiamo le parole in un testo come indicative dei suoi topic sottostanti, in realtà non dobbiamo preoccuparci così tanto dell'ordine delle parole. La sequenza delle parole, a volte chiamata asse sintagmatico, conta solo per certi tipi di lettura. Nei capitoli precedenti, abbiamo preservato il senso del tempo narrativo in un testo: quando abbiamo contato le parole con Voyant, le abbiamo poi rappresentate graficamente nel tempo. Ci interessava sapere se e quanto una frase particolare si verificasse all'inizio del testo rispetto alla fine. Ma possiamo scoprire cose interessanti sui testi se siamo un po' più flessibili e li pensiamo non come cose che si svolgono nel tempo, ma piuttosto come semplici conteggi simbolici, come  **bags of words** (sacchi di parole). In un modello bag word, l'ordine delle parole diventa irrilevante. Tutto ciò che ci interessa è quali parole compaiono in un testo e quanto spesso lo facciano. Abbastanza semplice, giusto?&#x20;

Prendi le seguenti due frasi:

* "Fine. How are you doing?"
* "How are you doing? Fine?"
* "Bene. Come stai?"
* "Come stai? Bene?"

If we _normalize_ a text by removing the stopwords, lowercasing the words, and getting rid of the punctuation, we get a bag of words. In this case, the bag of words for these two sentences is the same:

Se _normalizziamo_ un testo rimuovendo le stopword, riducendo le parole in minuscolo ed eliminando la punteggiatura, otteniamo un bag of words. In questo caso, bag of words per queste due frasi è lo stesso:

```
[
    "fine", 
    "how", 
    "are", 
    "you", 
    "doing"
]
```

Il contesto sfumato delle frasi che le rende diversi scompare, ma abbiamo la sensazione che entrambe parlino di cose simili. Ora, non vorremmo solo sapere quali parole vengano usate; vorremmo anche sapere con quale frequenza si presentino. Quindi un modello di un bag of words per le seguenti due frasi potrebbe produrre qualcosa di simile al seguente:

* Frase A: "Barbara is doing fine, thank you."
* Frase B: "Thank you, Dave. I am doing fine."

```
Words in Corpus
[
    "Barbara",
    "is",
    "doing",
    "fine",
    "thank",
    "you",
    "Dave,
    "I",
    "am"
]

Counts for Sentences
A: [1, 1, 1, 1, 1, 1, 0, 0, 0]
B: [0, 0, 1, 1, 1, 1, 1, 1, 1]
```

Qui otteniamo due liste. "Words in Corpus" fornisce tutte le parole nei nostri documenti. "Counts for Sentences A" e "Counts for Sentences B" descrivono in dettaglio il numero di volte in cui ciascuno di questi termini ricorre in ciascuna frase. Quindi il primo elemento della lista dei Counts for Sentences A è 1 perché "Barbara" ricorre 1 volta. La frase B ha 0 nella stessa posizione perché la parola "Barbara" non compare nella frase. Potremmo avere numeri grandi quanto ci occorrono per rappresentare il testo nel suo insieme. Abbastanza facile per un paio di brevi frasi, ma immagina di poter rompere interi romanzi come questo.&#x20;

Un'ultima cosa. Aggiungiamo questa frase al modello del bag of words che abbiamo costruito:

* Frase C: "I am Dave".

Il nuovo modello ora si presenta così:

```
Words in Corpus

[
 "Barbara",
 "is",
 "doing",
 "fine",
 "thank",
 "you",
 "Dave,
 "I",
 "am"
]

Counts for Sentences
A: [1, 1, 1, 1, 1, 1, 0, 0, 0]
B: [0, 0, 1, 1, 1, 1, 1, 1, 1]
C: [0, 0, 0, 0, 0, 0, 1, 1, 1]
```

Solo dando un'occhiata ai conteggi delle tre frasi, potresti sostenere che due delle frasi sono più simili tra loro. Guarda quanti 1 ottieni nelle frasi A e B rispetto a quanti 0 ottieni nella frase C. Puoi fare molta matematica per dimostrarlo e persino iniziare a rappresentare graficamente le cose per visualizzare l'argomento. Nota che le frasi 1 e 3 sono immagini speculari l'una dell'altra: non condividono alcun vocabolario in comune. Possiamo pensare ad A e C come estremità opposte di un continuum, quindi, e B come una via di mezzo. Poiché la frase B ne condivide parte con la frase A (entrambe contengono "doing," "fine," "thank," and "you"), ma di più con la frase C (entrambe contengono "I" "am" e "Dave", come anche "Barbara" o "is" non compare in nessuna delle due), possiamo dire che la frase B è un po' più lontana dall'una rispetto all'altra:

```
Sentences Graphed by Similarity
A------------------B----------C
```

Per ora, non preoccuparti della matematica dietro a tutto questo. L'obiettivo è solo darti un'idea delle possibilità che possono derivare dal considerare i testi come bag of words. Nota che, ad un certo punto, il vocabolario alla base del modello diventa irrilevante per questo tipo di pensiero. Stiamo solo lavorando con i numeri, il che è buono per il computer! Possiamo aggiungere il significato e la nuance linguistica alla fine, quando useremo le informazioni ricavate per fare interpretazioni umanistiche.

Potresti pensare che questo vada contro tutto ciò che hai finora saputo sulla lettura. Potrebbe sembrarti come se stessimo distruggendo un testo.  In questo caso non avresti  torto, perchè in effetti questo concetto è abbastanza lontano dalla forma tradizionale della lettura, cioè in sequenza attraverso la pagina. Questo approccio, invece, vuole che si pensi alla lettura in modo diverso, per sviluppare una nuova epistemologia dell'atto della lettura.  Perdiamo qualcosa nel processo,cioè il senso di un testo nel suo dispiegarsi nel tempo.

But we also gain the ability to think about a text in new ways. Sentences are just the beginning. You can use a bag of words approach to determine how different or similar whole books or authors are from each other. If we have lists of words for each text as well as for the corpus (or set of documents) as a whole, we can actually work backwards to get a sense of the underlying topics that we were talking about a moment ago. Instead of skimming a paragraph to determine its basic topic, we could scan full texts -- and scan lots of them (Brandon's record is about 1.8 million texts in a corpus). And rather than trying to get a sense of 1-3 topics, we could break our text apart into 15-20 different topics. Now we are cooking with gas, and we're talking about topic modeling.

Ma acquisiamo anche la capacità di pensare a un testo in modi nuovi. Le frasi sono solo l'inizio. Puoi utilizzare un approccio basato sul bag of wors per determinare quanto libri o autori interi siano diversi o simili l'uno dall'altro. Se abbiamo elenchi di parole per ogni testo così come per il corpus (o insieme di documenti) nel suo insieme, possiamo effettivamente lavorare a ritroso per avere un'idea degli argomenti sottostanti di cui stavamo parlando un momento fa. Invece di scorrere un paragrafo per determinarne l'argomento di base, potremmo scansionare testi completi e scansionarne molti (il record di Brandon è di circa 1,8 milioni di testi in un corpus). E invece di cercare di avere un'idea di 1-3 argomenti, potremmo suddividere il nostro testo in 15-20 argomenti diversi. Ora sto bevendo un caffè, metre sto parlando di topic modelling.

### Ulteriori Risorse <a href="#furtherresourcsupervisedclassifiers" id="furtherresourcsupervisedclassifiers"></a>

* Vedi le utili pagine [Wikipedia](https://it.wikipedia.org/wiki/Modello\_della\_borsa\_di\_parole) in italiano e quella in inglese [Wikipedia](https://en.wikipedia.org/wiki/Bag-of-words\_model).
* Per farti un'idea, vedi Il contributo dei topic models alla navigazione del [corpus delle sentenze della Cassazione](https://webstat.giustizia.it/Analisi%20e%20ricerche/Navigazione%20tematica%20del%20corpus%20della%20Cassazione.pdf).
* Daniel Chandler ha un'utile [spiegazione](http://visual-memory.co.uk/daniel/Documents/S4B/sem03.html) dell'asse sintagmatico: si tratta di semiotica per principianti.
