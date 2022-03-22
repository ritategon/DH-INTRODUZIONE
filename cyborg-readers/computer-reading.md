# Come un Computer Legge un Testo

Se hai seguito in modo costante fino a qui, dovrebbe essere chiaro che i computer e gli esseri umani non la pensano allo stesso modo. Rispetto all'analisi del testo, possiamo dire che computer e umani hanno competenze complementari. I computer sono bravi a fare cose che richiederebbero molto tempo o che sarebbero incredibilmente noiose. I computer possono facilmente contare e confrontare e lo faranno per tutto il tempo che dici loro di farlo. Al contrario, gli esseri umani sono molto bravi a comprendere le sfumature e il contesto. Pertanto, non chiedo a un computer di eseguire un close reading  o di decomprimere le affermazioni di un testo primario o secondario; questo è qualcosa in cui sei molto più bravo tu. Allo stesso modo, è più facile che un computer elenchi tutti i numeri compresi tra 1 e 45678987 piuttosto che farlo da soli.

Se esiste una tale disparità di competenze tra te e un computer, continuerai forse a chiederti perché stiamo tenendo un corso sull'analisi del documento digitale. La risposta è che ci sono molti casi in cui vale la pena combinare le sfumature del pensiero umano con il potere quantitativo dei computer per guardare i documenti in modi nuovi e creativi. In particolare, puoi fare in modo che il computer svolga molto del lavoro ripetitivo che potresti trovare noioso.&#x20;

Per farlo, però, è necessario conoscere ancora un po' di più come i computer elaborano i testi. Abbiamo detto che hanno difficoltà a comprendere i dati, che possono interagire e utilizzare le informazioni, ma fanno pochissime ipotesi e ancor meno interpretazioni su ciò con cui stanno lavorando. Qualsiasi capacità interpretativa abbiano, ebbene essa è stata specificamente programmata. Quindi quello che segue è un approfondimento  che deve portare ad assumene che nulla va dato per scontato.

Nel contesto dell'analisi testuale, tutto ciò significa che i computer non leggono con la stessa facilità con cui lo facciamo noi. Considera la seguente frase:

"Abbiamo visto _8½_."

Presa da sola, la frase non ci dice molto. Il suo significato dipende molto dalla domanda a cui  rispondere e possiamo pensare a due possibili domande con contesti molto diversi:

> "Quanti film hai visto?"
>
> "Che film hai visto?"

Nel primo caso, potremmo rispondere con il numero di film che abbiamo visto. È stato un fine settimana lento e l'abbiamo trascorso al cinema locale passando da un film all'altro. È stato un grande momento! Nella seconda situazione, potremmo rispondere con il titolo di un film specifico, [_8½_ di Frederico Fellini](https://en.wikipedia.org/wiki/8%C2%BD). Quindi una risposta è un numero e una risposta è un nome. Dal momento che gli esseri umani sono bravi a cogliere il contesto, saremmo facilmente in grado di distinguere tra i due. Nella maggior parte delle situazioni, regoleremmo semplicemente la nostra comprensione internamente prima di andare avanti con la conversazione.

I computer non possono fare inferenze come queste e questo fatto ha gravi implicazioni: numeri e parole hanno usi significativamente diversi. Ecco due ulteriori estensioni della conversazione:

> "Se aggiungi quattro a quanti film hai visto, qual è il risultato?"

Se stessimo parlando di un certo numero di film, la mia risposta sarebbe chiaramente: "Oh, questo è 12.5. Perché mi stai facendo un quiz di matematica?" Se stessimo parlando del film di Fellini, potremmo rispondere: "Cosa? Oh, stavamo parlando di un titolo, non di un numero. Non possiamo aggiungere cose a un titolo". Ancora una volta, gli esseri umani hanno la capacità di rispondere al contesto, dedurre e adattarsi. I computer non sono altrettanto flessibili: devono sapere in anticipo, nella maggior parte dei casi, con che tipo di informazioni hanno a che fare. In questo modo possono agire come previsto.

I programmatori hanno sviluppato convenzioni per dire ai computer di distinguere tra questi diversi tipi di informazioni o **tipi di dati**. La distinzione che abbiamo delineato sopra contiene le due più importanti per i nostri scopi qui:

* **Strings**: caratteri, cose riferite alle parole
* **Integers**: numeri interi

L'equivoco sui film dipende da una confusione intorno a tipi di dati come questi. Se intendi imparare a programmare, potresti trovare nomi leggermente diversi a seconda del linguaggio di programmazione e ti verranno presentati anche altri tipi di dati. Ma la distinzione tra stringhe e numeri interi è importante per l'analisi del testo. Puoi eseguire operazioni aritmetiche su numeri interi, mentre le stringhe rispondono meno bene a queste cose. Puoi mettere in maiuscolo le parole, ma non i numeri. E i computer generalmente vogliono che tu abbia a che fare con oggetti simili: puoi combinare stringhe (le parole possono diventare frasi) o aggiungere numeri, ma provare a combinare una stringa e un numero intero bloccherà le cose.

Ma nota che il nostro scenario iniziale era imperniato sull'ambiguità tra stringhe e numeri interi. Come fa un computer a sapere se stiamo parlando di stringhe o di numeri interi nei casi in cui potrebbero riferirsi a entrambi? Come fa a sapere che vogliamo che 8 funzioni come una parola e non come un numero in questo contesto?

I programmatori nel corso degli anni hanno costruito una varietà di funzioni e strumenti in linguaggi diversi per aggirare alcune di queste difficoltà, ma rimangono comunque. Quando si elabora il testo da un computer, dobbiamo tenere conto di tali problemi. Generalmente lo facciamo seguendo linee guida molto rigorose per l'inserimento delle informazioni. Questa **sintassi** funziona più o meno allo stesso modo della grammatica per gli esseri umani, aiutando il computer a tenere traccia di ciò che intendiamo e di ciò che vogliamo che faccia.

In questo caso, possiamo dire al computer che qualcosa è una stringa o meno mettendo o meno di virgolette:

* 8 vs "8"

Il computer esamina quelle virgolette e vede la differenza nei tipi di dati:&#x20;

* un numero senza virgolette? Questo è un numero intero.
* ah, virgolette: ciò significa che sto guardando una stringa.

La programmazione e l'analisi del testo più in generale si basano su tali sottili distinzioni. Un computer ha bisogno di tenere la mano per riconoscere la differenza e la somiglianza. Per un computer, quanto segue non è completamente correlato:

* 8 ≠ "8" ≠ "Eight" ≠ "Eighth"

Il computer non riconoscerebbe le relazioni tra quelle quattro parole chiaramente correlate. Va anche oltre: i computer considerano le lettere minuscole e maiuscole come caratteri completamente diversi.

"H" ≠ "h"

Queste differenze possono essere estremamente frustranti quando inizi a esercitarti nell'analisi del testo, ma non preoccuparti: da anni i programmatori sviluppano modi per rendere conto di queste cose. In qualsiasi contesto di programmazione, vi è accesso a una gamma di utilità per maiuscole, minuscole, convertire interi in stringhe, convertire data e ora in parole, ecc.&#x20;

Ma ci sono vantaggi in queste rigide restrizioni. Seguendoli, possiamo ottenere informazioni molto dettagliate su testi, informazioni che altrimenti non potremmo ottenere. La prima parte di qualsiasi progetto di analisi del testo prevede la conversione di un linguaggio complesso in dati organizzati che il computer può comprendere. Questo primo passaggio consiste nell'appianare i punti problematici e nel colmare eventuali lacune, il tutto con un occhio alle questioni delineate sopra e nel capitolo su "[Data Cleaning](../data-cleaning.md)."

"This is a sentence" ≠ "This" "is" "a" "sentence"

Un computer non riconoscerebbe i due lati del segno di uguale come equivalenti. Il lato sinistro, dopo tutto, contiene spazi e il lato destro contiene una serie di stringhe più piccole, poiché ogni parola è tra virgolette. Fastidioso? Forse. Ma anche utile! Dopotutto, raramente siamo interessati a frasi intere. Ci riferiamo comunemente alle singole parole come **token** e il processo di spezzare le frasi in parole diventa quindi chiamato **tokenizzazione**. Questo ci permette di strutturare il nostro testo in una raccolta di pezzi che possiamo manipolare più facilmente. La tokenizzazione quasi sempre separa la punteggiatura dalle parole nei propri token. Quindi "L'ho sentito!" diventerebbe "io", "sentito", "lui", "!". I diacritici possono essere o meno gettati via, a seconda che ti interessino o meno.

Possiamo scomporre ulteriormente le cose dopo aver diviso un testo in singole parole. Mentre spesso ci preoccupiamo del numero di volte in cui si verifica ogni particolare segno o parola, potremmo anche preoccuparci dei diversi tipi di parole. Potremmo voler tenere traccia, da un lato, di tutte le diverse parole in un testo indipendentemente dalla frequenza con cui si verificano. Ma potremmo anche volere un diverso tipo di elenco di vocaboli. Invece di contare tutte le parole, potremmo semplicemente voler prendere un singolo esempio di ogni **tipo** di token. Se abbiamo il seguente documento:

> Test test test sentence sentence

Abbiamo cinque tokens and due tipi ('test' and 'sentence'). Un elenco di tipi potrebbe essere utile per avere un'idea del tipo di linguaggio utilizzato in un testo, mentre un elenco grezzo di token potrebbe essere utile per capire quali tipi di parole si trovano in quali proporzioni. A seconda delle nostre domande e interessi di ricerca, statistiche come queste possono aiutarci a capire di cosa discute il documento e come viene discusso.

Se le frasi sono suddivise in parole, potremmo anche preoccuparci di suddividere prima i documenti in frasi. Abbiamo un nome anche per questo: **segmentazione**.

> "Ma aspetta", dici, "i computer tengono alle maiuscole. Quindi se tokenizziamo un testo e proviamo a confrontare 'parola' e 'Parola' penseranno che sono cose completamente diverse!&#x20;

Vero! Hai ragione, quelle differenze nelle maiuscole spesso non sono significative. È una pratica abbastanza comune mettere in minuscolo tutte le parole dopo averle tokenizzate. Questo processo è spesso chiamato **normalizzazione** dei dati, poiché stiamo appianando le incongruenze che potrebbero intralciare le nostre domande di ricerca. L'intera raccolta di processi di segmentazione, tokenizzazione e normalizzazione ha anche un nome a parte: **preprocessing** (preelaborazione), cioè tutte quelle cose che fai ai dati prima di lavorarci. A seconda dei tuoi interessi, potresti includere altri passaggi, come taggare i token per parti del discorso o filtrare particolari tipi di parole. Tieni presente che la preelaborazione può modificare l'elenco dei tipi. Un computer non riconoscerebbe "Said" e "said" come dello stesso tipo, ma, se normalizzi le maiuscole in modo che ogni token sia minuscolo, un computer li vedrebbe come la stessa parola. Quindi spesso devi decidere quali pezzi ti interessano all'inizio del processo.

I dati testuali sono disordinati e richiede molto lavoro per convertirli in materiale utilizzabile. Molto spesso, il processo prevede anche più passaggi di quelli che illustriamo qui. Ma una volta che si ottiene un controllo su un insieme definito di metodi per farlo, si apre un intero mondo di possibilità. Dopotutto, Internet è pieno di dati testuali non strutturati e potremmo imparare molto sul nostro mondo analizzandolo. Questo campo di studio è indicato come **natural language processing/**elaborazione del linguaggio naturale ("linguaggio naturale" si riferisce alle lingue umane come italiano, inglese, francese, arabo o cinese, al contrario delle lingue dei computer, che sono state inventate). Una vasta gamma di interessanti professioni. Il mondo ha bisogno di persone che sappiano dare un senso al nostro mondo di documenti.&#x20;
