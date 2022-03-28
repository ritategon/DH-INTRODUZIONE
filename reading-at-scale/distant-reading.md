# Distant Reading

[Brandon Walsh](https://walshbr.com) racconta che entrando alla scuola di specializzazione, uno studente più grande una volta ha riassunto uno dei problemi della vita come una sorta di equazione:

> There is an infinite of material that one could read.
>
> (trad. C'è un'infinità di materiali che si potrebbero leggere).

> There is a finite amount of time that you can spend reading.
>
> (trad. C'è un tempo limitato che puoi dedicare alla lettura.)

La lezione era che ci sono limiti alla quantità di materiale che anche il lettore più vorace può assorbire. Si può sentire il bisogno di leggere tutto, ma le possibilità sono oggettivamnete limitate. Quindi vale la pena di leggere quel che si può con attenzione.

I computer però capovolgono la questione: il loro problema non è tanto la quantità di lettura quanto la qualità. Come abbiamo discusso in precedenza, se i computer non possono leggere con nessuna particolare sfumatura o comprensione possono aiutarci a leggere su larga scala. Studiosi come [Franco Moretti](https://it.wikipedia.org/wiki/Franco\_Moretti) si riferiscono a questo tipo di analisi, quando usiamo la tecnologia per ottenere una visione a volo d'uccello di un corpus, in forma di **distant reading**. Se il **close reading**, di cui abbiamo parlato in precedenza, presta molta attenzione a ogni parola in un testo, la lettura a distanza presuppone che possiamo ottenere nuove intuizioni da un pensiero più ampio, utilizzando i computer per acquisire più testi di quanto sarebbe altrimenti possibile. Pertanto, potremmo avere un computer che ci fornisce rappresentazioni schematiche di migliaia o addirittura centinaia di migliaia di testi. Nell'ultimo capitolo abbiamo lavorato con le stopword e le analisi di frequenza. Ci interessava soprattutto il numero di volte in cui particolari parole apparivano nel corso del nostro corpus. I computer sono particolarmente bravi a leggere cose come questa. Da soli, non saremmo mai in grado di leggere tutti i romanzi britannici del 19° secolo. Ma i computer possono aiutarci almeno ad avere un'idea di questo grande corpus di opere. La lettura su una scala così grande può anche offrirci la possibilità di sgretolare ciò che Margaret Cohen ha definito il ["great unread"](http://press.princeton.edu/titles/6645.html), tutta quella scrittura che è passata inosservata perché non è mai entrata a far parte del canone letterario.

Potrebbe sembrare che la lettura a distanza sia meno critica: dopotutto, infatti, potresti teoricamente costruire un bellissimo programma per analizzare migliaia di libri per te senza che tu debba mai aprirne uno solo. E alcune persone lo fanno. Come [hanno sostenuto ](https://ryancordell.org/research/scale-as-deformance/)Matt Jockers, Ryan Cordell e altri, tuttavia, anche leggere a questo livello macro richiede attenzione ai micro dettagli. Pensa a quelle stesse abilità che stavi esercitando con la lettura ravvicinata all'inizio del libro: sono ancora profondamente rilevanti. Il lavoro inizia solo quando hai dei risultati e un grafico. Devi quindi capire quali elementi siano significativi e cosa potrebbero indicare. E l'esplorazione molto spesso ti riporta a parti specifiche del corpus che vuoi leggere in modo più dettagliato.

## Pattern

Un modo per iniziare a pensare allo sviluppo di approcci per l'utilizzo di strumenti e metodi come questi è fare un passo indietro. Quando guardi i risultati della lettura a distanza, sei, più di ogni altra cosa, alla ricerca di schemi e valori anomali. Potresti farti una serie di domande quando guardi i risultati di strumenti come Voyant.

* C'è qualcosa di chiaramente non pertinente o che non ha senso?
* Cosa ti sorprende?

Se sai che il tuo testo riguarda il Sud America e scopri che il quarto token più comune è "Francia", probabilmente sei di fronte a qualcosa di interessante. Potrebbe essere necessario rivedere le tue aspettative e le tue domande di ricerca e questo va benissimo. Questo fa effettivamente parte del processo di ricerca; se non rivedi la tua analisi, significa che non stai rispondendo a ciò che stai riscontrando nelle tue fonti. La cosa più interessante di un progetto è raramente la prima cosa che pensiamo che sarà.

* In che modo i numeri che lo strumento ti _butta fuori_ si collegano ai concetti sottostanti nel testo?

La nostra esperienza di lettura, le nostre interpretazioni di un testo, il modo in cui ci fa sentire sono il risultato di molte cose, ma il linguaggio gioca un ruolo nel costruirle tutte. Le parole costituiscono la base di tutto ciò che otteniamo dalla lettura, quindi possiamo lavorare a ritroso dalla parola al concetto. Pensa a quali concetti sottostanti potrebbero prendere forma a seguito di parole particolari. Ad esempio, se quattro delle prime cinque parole in un testo sono nomi maschili o pronomi maschili, ciò potrebbe dire qualcosa sulla rappresentazione di genere nel testo. I pronomi personali potrebbero dire qualcosa su cosa significa essere un sé nel tuo testo. Quattro volte più punti esclamativi dei punti? Questo potrebbe dire qualcosa sull'impressione retorica che l'autore vuole trasmettere.

* Quali tendenze vedo nei dati?&#x20;
* Qualcosa sta chiaramente diminuendo o aumentando nel tempo?&#x20;
* Le cose sono sostanzialmente le stesse nel tempo?

Se disponi di un corpus in cui sono note le date di ciascun testo, puoi iniziare a trarre inferenze basate sull'uso della lingua nel tempo. Lo strumento Google NGram si basa su tali presupposti, anche se dovresti prestare attenzione a come i cambiamenti nella lingua stessa potrebbero influenzare i tuoi risultati (il classico esempio di questo è la [s lunga](https://it.wikipedia.org/wiki/S\_lunga), che i computer leggono spesso come una "f" nei testi più antichi ). Le tendenze che vedi possono offrire buone opportunità per riflettere sulla tua comprensione di ciò che accade storicamente nello stesso periodo di tempo. In alternativa, poiché sperimentiamo i singoli testi nel tempo, possiamo esaminare come l'uso di un concetto o di una parola cambi dall'inizio alla fine di un testo. Tutto ciò potrebbe offrire un modo per pensare al testo nel suo insieme.

* Qualcosa sembra semplicemente sbagliato?

È facile pensare che i risultati che il computer  dà siano corretti e crederci senza discurtere. Dopotutto, come potrebbero mentire i numeri? La verità è, tuttavia, che qualsiasi dato è il risultato dei pregiudizi delle persone che lo ha prodotto. Statistiche apparentemente buone possono far sembrare qualsiasi cosa una verità oggettiva quando potrebbe non esserci altro che una bella immagine. Vedi l'esempio di [Robert Grant](http://www.thefunctionalart.com/2016/08/download-datasaurus-never-trust-summary.html):

![Un esempio di cattiva statistica](../assets/reading-at-scale/distant-reading-dinosaur.jpg)

E una visualizzazione appariscente può altrettanto facilmente non dimostrare nulla.

![Esempio di pessima visualizzazione. Fonte: https://twitter.com/ejmaroun/status/765029160087465985](../assets/reading-at-scale/distant-reading-graphs.jpg)

I tuoi risultati potrebbero essere frutto si  impostazioni configurate in modo errato. O forse hai caricato il testo sbagliato. O forse, a monte  stai fraintendendo come funzioni lo strumento. In questi casi va fatto un passo indietro.

> Ma aspetta, dici tu, non ne so ancora abbastanza per poter fare questo tipo di lavoro

Per la verità, non è necessario sapere nulla di statistica o informatica per poter dire qualcosa di significativo sui testi attraverso la lettura a distanza. Resta fermo che la conoscenza di entrambi questi campi può fare molto e darti cose più significative e interessanti da dire, ma questi strumenti, metodi e idee non dovrebbero essere al di là di nessuno. Per ora prendi uno strumento per una prova e guarda cosa succede. Puoi sempre approfondire nel tempo e dare alla tua analisi una base più solida. Non vale la pena tirarsi indietro e mettersi ansia. Ora prendiamolo come un gioco. Poi si potrà decidere di lavorare duro per andare a fondo.

Non si può leggere tutto, abbiamo detto. Invece, concentriamoci su ciò in cui gli esseri umani sono bravi: leggere con cura e offrire interpretazioni. Il computer può lavorare con grandi numeri molto più velocemente di noi. Il  nostro compito è aiutarlo a farlo in modo significativo.

## Further Reading

* Ryan Cordell fornisce un utile esame dell'interconnessione tra lettura ravvicinata e distante in "[Scale as Deformance](http://ryancordell.org/research/scale-as-deformance/)"

Inoltre, le seguenti risorse offrono ottime introduzioni al distant reading:

* Franco Moretti, [_Graphs, Maps, Trees: Abstract Models for Literary History_](https://www.amazon.com/Graphs-Maps-Trees-Abstract-Literary/dp/1844671852).
* Margaret Cohen, [_The Sentimental Education of the Novel_](http://press.princeton.edu/titles/6645.html).
* Matt Jockers, [_Macroanalysis_](http://www.press.uillinois.edu/books/catalog/88wba3wn9780252037528.html).
