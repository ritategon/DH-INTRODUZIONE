# La forma dei dati

Potrebbe essere la prima volta che pensi alla "forma dei dati": significa che la struttura attorno a parole e numeri può consentire diversi tipi di analisi da parte di un essere umano o di un computer che legge il testo. Continua a leggere per conoscere le tre categorie principali: dati non strutturati, strutturati e semistrutturati.

### Dati non strutturati

I dati non strutturati sono dati che non sono organizzati in unità semantiche distinte e predefinite. Tipicamente, questo significa dati testuali, che potrebbero essere un resoconto scritto, un'opera letteraria, un articolo di giornale o qualsiasi altra cosa rappresentata come testo. Gli esseri umani possono elaborare dati non strutturati leggendoli, comprendendone il contenuto e facendo inferenze utilizzando il contesto e il buon senso, tutte attività estremamente difficili per i computer. I dati non strutturati sono difficili da elaborare in modo significativo per i computer.&#x20;

Esempio: _George Washington fu il primo presidente degli Stati Uniti, in carica dal 30 aprile 1789 al 4 marzo 1797. Gli successe John Adams, che rimase presidente fino al 1801, dimettendosi il 4 marzo._

### Dati strutturati

I dati strutturati sono dati organizzati secondo un particolare modello, che ne definisce esplicitamente la struttura. Ad esempio, i dati chiave sui presidenti degli Stati Uniti potrebbero essere strutturati secondo un modello che richiede che, per ogni presidente, registriamo:

![](../.gitbook/assets/screenshot-learning.edx.org-2022.03.20-20\_58\_14.png)

Poiché questi dati sono strutturati, qualsiasi elaborazione software può, e deve, presumere che ogni riga della tabella rappresenti un singolo presidente. Inoltre, il software può presumere che i dati nella colonna "took office" siano sempre una singola data (invece di dire un numero, un nome, una descrizione o un'ora del giorno) che rappresenta la data in cui il presidente è entrato in carica. Ciò semplifica l'elaborazione dei dati strutturati. Ad esempio, potremmo calcolare immediatamente la durata della permanenza in carica di ciascun presidente sottraendo la data "Entrò in carica" da "Left office" in ogni riga. Questa semplice operazione sarebbe molto più difficile da eseguire computazionalmente su dati non strutturati, anche se contenessero tutte le stesse informazioni.

### Dati semi - strutturati

I dati semistrutturati sono dati che non sono conformi a un modello di dati formale, ma utilizzano costrutti formali per indicare elementi semantici separati all'interno dei dati. Un metodo per indicare gli elementi semantici consiste nell'aggiungere codici speciali, o "markup", a ciò che altrimenti sarebbe un testo non strutturato. Ad esempio, potremmo aggiungere coppie di codici come "\<name>" e " \</name>" attorno a ogni occorrenza di un nome proprio per rendere alcuni aspetti di un documento altrimenti non strutturato più facilmente elaborabili computazionalmente. Questo approccio può essere utilizzato per evitare ambiguità durante l'elaborazione di contenuti scritti in lingue naturali. Vedi di seguto un esempio:

![](../.gitbook/assets/screenshot-learning.edx.org-2022.03.20-21\_04\_20.png)

Sebbene non siano semplici da elaborare come i dati strutturati, i dati semistrutturati possono essere utilizzati per aggiungere informazioni a dati non strutturati così da consentire un'elaborazione efficace in molte applicazioni.

### Sintesi della forma dei dati

Dunque, esistono tre grandi categorie di dati: strutturati, non strutturati e semistrutturati. I dati organizzati secondo un modello di dati esplicito e ben definito sono chiamati dati strutturati. I dati non strutturati non hanno unità distinte e predefinite. I dati che non sono conformi a un modello di dati, ma utilizzano costrutti formali, come codici di markup per indicare elementi semantici interni, sono chiamati dati semi-strutturati.

![](https://lh3.googleusercontent.com/7zzPFf\_pMWPIf000mK0iy-HzrbIgT4o-ndEkyV9aj\_Zg7YJUE4K6snlgw5sF1IfzP-tvx2Jl4S2s5Ze\_1UmWX8OrP-zT0v4Keh3NK1KQjwTw2Gf3au6PSyLNfkGERzEO23\_VVMqd)









