# Micro e Macro Tasking

Pensa a uno scenario comune: stai acquistando qualcosa online e, prima che il sistema ti permetta di effettuare il check-out, devi inserire del testo, trascrivere dell'audio o comunque dimostrare di non essere un robot. Farlo richiede solo pochi secondi del tuo tempo, ma tali transazioni avvengono milioni di volte ogni giorno su Internet. L'energia combinata sprecata in interazioni così semplici è sbalorditiva.

Ora immagina di poter prendere tutte quelle ore di lavoro umano e dedicarle a qualcosa di utile. [reCAPTCHA](https://www.google.com/recaptcha/about/) mira a fare proprio questo e probabilmente l'hai usato inconsapevolmente. Pensa ai compiti di convalida umana descritti sopra: le probabilità sono piuttosto alte che, quando ne hai eseguito uno, potresti aver inconsapevolmente corretto la trascrizione di un'immagine, contribuito a fornire un set di test per l'intelligenza artificiale o contribuito a rendere Google Maps più preciso. La prossima volta che riempi una casella di testo per dimostrare che sei un essere umano, potresti chiederti a chi e a cosa serva il tuo lavoro.

Il **Crowdsourcing**, in senso lato, può essere considerato come l'applicazione di molte persone diverse a un singolo problema, facendo in modo che ciascuna lavori su un pezzo del progetto. Il tipo più comune di crowdsourcing viene utilizzato per correggere le trascrizioni di testo. Quando si scansiona un'immagine con del testo, sofisticati programmi per computer scorrono sull'immagine per fare la loro ipotesi migliore basandosi su grandi quantità di informazioni. Questo processo, noto come **riconoscimento ottico dei caratteri** (**OCR**) , spesso formula ipotesi errate: date molte variazioni di carattere, tipo di inchiostro, contrasto e altro, il compito è in realtà molto complicato e difficile. Questi errori sono spesso chiamati Dirty OCR e un esempio potrebbe assomigliare a questo:

"Qi-jtb"

Ciò potrebbe non significare molto fuori contesto, ma accanto a un'immagine potresti probabilmente mettere insieme la parola che doveva rappresentare dall'artefatto di stampa originale. Ryan Cordell risolve questa particolare scansione scadente della prima parola nella famosa frase "Quoth the Raven" di "The Raven" di Edgar Allen Poe come esempio dei problemi che la scansione può presentare per lo studio di documenti storici. Tali errori complicano gran parte dell'analisi del testo digitale: una ricerca nel documento per "Quoth" non restituirebbe questa istanza a meno che qualcuno (o qualcosa) non la pulisse.

Imparerai di più su questo e altri problemi con i dati digitali nel nostro capitolo "[Data Cleaning](../data-cleaning.md)". Per ora, basti dire che correggere tali errori è un lavoro lungo e noioso. Farlo non richiede molta energia intellettuale per un essere umano, ma richiede molto tempo. D'altra parte, queste attività di correzione sarebbero molto difficili da eseguire con precisione per un computer, ma i computer possono gestire l'ampia scala del lavoro con pochi problemi. Progetti come questi utilizzano una tecnica chiamata **microtasking**, il che significa che indirizzano l'energia umana di molte persone verso compiti finiti. I progetti di microtasking trovano soluzioni a grandi problemi trasformandoli in piccoli compiti che gli individui possono risolvere. La correzione OCR è uno scenario comune per tali progetti: [Transcribe Bentham](http://blogs.ucl.ac.uk/transcribe-bentham/) chiede agli utenti di preparare versioni corrette delle carte dei manoscritti inediti di Jeremy Bentham e [18thConnect](http://www.18thconnect.org) ha sviluppato [Typewright](http://www.18thconnect.org/typewright/documents)  per correggere un vasto numero di materiali della prima età moderna. Ciascuno di questi progetti si basa su singole persone che correggono i testi un pezzo alla volta. Di un occhio anche alla [Amazon Mechanical Turk](https://www.mturk.com).

![](../.gitbook/assets/screenshot-www.mturk.com-2022.03.16-16\_14\_04.png)

Mentre i progetti di microtasking chiedono agli utenti di lavorare su un problema già predisposto per loro, i progetti di **macrotasking** sono guidati dagli interessi e dagli obiettivi del gruppo stesso. Wikipedia è probabilmente l'esempio più famoso di crowdsourcing e rientra in questa categoria. I suoi numerosi utenti applicano la loro energia a problemi comuni: la produzione di conoscenza su argomenti particolari. Ma Wikipedia è diversa da altre forme di crowdsourcing in quanto non ha un obiettivo chiaro in vista. Non possiamo mai annotare tutta la conoscenza umana: invece, gli utenti devoti di Wikipedia lavoreranno continuamente per sviluppare una migliore comprensione fino a quando il sito Web non sarà offline. La comunità degli utenti crea i propri obiettivi, priorità e compiti, che possono portare a problemi sistemici: gli articoli online non riflettono necessariamente l'interesse intrinseco del materiale ma, invece, gli interessi della comunità di editori. (Nel caso di Wikipedia, ciò significa che ha un [gender problem](https://www.insidehighered.com/blogs/library-babel-fish/woes-wikipedia) significativo.) Mentre i progetti di microtasking riguardano problemi davvero piccoli e ripetibili, i problemi di macrotasking sono fondamentalmente diversi in natura.&#x20;

Vale la pena soffermarsi su tutti questi esempi per considerare il lavoro in essi contenuto. Stiamo parlando di una quantità incredibile di energia e di lavoro che è essenzialmente volontariato. Se andiamo su Typewright e aiutiamo a trascrivere un testo del diciottesimo secolo, quello è tempo che avremmo potuto dedicare a fare qualcos'altro, compreso il lavoro per il quale avremmo potuto essere ricompensati in modi più espliciti.

* È sufficiente che gli utenti contribuiscano al bene pubblico per questi progetti?
* &#x20;A che punto il lavoro volontario diventa sfruttamento?&#x20;

In molti casi, questi progetti digitali costano ingenti somme di denaro e, secondo la critica, questi fondi avrebbero potuto fornire dipendenti pagati effettivi anziché volontari. Alcuni di questi partecipanti al crowdsourcing potrebbero non essersi nemmeno resi conto che stavano lavorando. Nel caso di Recaptcha, probabilmente hai involontariamente offerto il tuo tempo per un progetto di crowdsourcing senza nemmeno rendertene conto. Quali sono le pratiche etiche per condurre progetti di volontariato su tale scala? Cosa ti occorrerebbe per sentirti adeguatamente ricompensato per il tuo tempo? Queste sono domande aperte senza risposte chiare, ma vale la pena tenerle a mente. Pensiamo che questa consapevolezza e autoriflessione debbano essere alla base di modi etici di impegnarsi in progetti come questi. Dopotutto, Typewright, Recaptcha e Transcribe Bentham producono grandi risultati, ma lo fanno impiegando l'energia umana per compiti abbastanza umili. Wikipedia solleva altre importanti domande sul crowdsourcing: la folla può fare di più? Cosa succede quando diamo il controllo del progetto alla folla?

{% hint style="info" %}
**Esempi di ambienti di microtasking**&#x20;

Notizia del 2014 aggiornata nel 2018 nel contesto italiano:&#x20;

[https://poloarchivistico.regione.emilia-romagna.it/notizie/volontari-a-raccolta-per-digitalizzare-gli-smithsonians](https://poloarchivistico.regione.emilia-romagna.it/notizie/volontari-a-raccolta-per-digitalizzare-gli-smithsonians)

[https://www.zooniverse.org/lab](https://www.zooniverse.org/lab)

Image and Full Transcription: (successful transcription of handwritten text): [https://transcription.si.edu/transcribe/15654/NMAAHC-007675740\_00588](https://transcription.si.edu/transcribe/15654/NMAAHC-007675740\_00588)

Organization: Smithsonian Transcription Center ([https://transcription.si.edu](https://transcription.si.edu))

Title of Specific Project in Exampl**e**: District of Columbia Education, Records Relating to School Buildings, Grounds, and Supplies, Quartermaster’s Monthly Reports ([https://transcription.si.edu/project/15654](https://transcription.si.edu/project/15654))

Link to Catalog of All Projects Undergoing Crowdsourced Transcription by Smithsonian Transcription Center: [https://transcription.si.edu/browse?filter=\&sort=](https://transcription.si.edu/browse?filter=\&sort=)
{% endhint %}
