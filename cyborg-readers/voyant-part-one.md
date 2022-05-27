# Voyant Parte 1

Useremo uno strumento chiamato [Voyant](http://voyant-tools.org/) per introdurre alcuni argomenti di base nell'analisi del testo legati alla lettura cyborg.&#x20;

Entrando in Voyant incontrerai uno spazio in cui puoi caricare testi. Per i grafici seguenti, è stato caricato il testo completo di [_The String of Pearls_](https://github.com/ritategon/DH-INTRODUZIONE/blob/0624204a28317bc3c07d9189140ac5f4bec40c7f/assets/the-string-of-pearls-full.txt) __ (puoi prenderlo e fare tu stesso le prove), testo del 1846-1847, il cui protagonista è l'inquietante Todd.

![Voyant splash page and text uploader](../assets/cyborg-readers/voyant-splash-page.jpg)&#x20;

Dopo che Voyant ha elaborato il tuo testo, otterrai una serie di riquadri con molte informazioni. Voyant racchiude diverse funzionalità in un unico pacchetto digitale compatto: ogni riquadro offre diversi modi di interagire con il testo.

![Visualizzazione di default di String of pearls in Voyant](../assets/cyborg-readers/voyant-overview.jpg)

Voyant ti offre molte opzioni, quindi non lasciarti sopraffare. Qui ci concentreremo solo su alcune funzionalità. Il riquadro in alto a sinistra potrebbe essere il più familiare per te:

![Voyant: nuvola di parole predefinita  String of pearls](../assets/cyborg-readers/voyant-word-cloud-default.jpg)

Le nuvole di parole come queste sono state rese popolari negli ultimi anni da Wordle. Non fanno altro che contare le diverse parole di un testo: più frequentemente una determinata parola appare, maggiore è la sua presenza nella nuvola. In effetti, Voyant ti consente di vedere le frequenze sottostanti che sta utilizzando per generare il cloud se fai clic sul pulsante "Termini del corpus" sopra il cloud di parole.

![Frequenza dei termini mel corpus](../assets/cyborg-readers/voyant-term-frequencies.jpg)

Concordanze come queste sono alcune delle più antiche forme di analisi del testo che abbiamo e i computer sono particolarmente bravi a produrle. In effetti, un progetto di questo tipo è spesso citato come una delle storie di origine delle digital humanities: la massiccia analisi delle concordanze nelle opere di [San Tommaso d'Aquino di padre Roberto Busa](https://www.historyofinformation.com/detail.php?entryid=2321), iniziata su schede perforate negli anni Quaranta e Cinquanta. È stato uno dei primi lavori nel suo genere ed è stato determinante per gli sviluppi successivi delle DH.

Il lavoro di Busa ha richiesto anni. Ora possiamo eseguire ricerche simili in pochi secondi e possiamo imparare molto semplicemente contando le parole. Le parole di gran lunga più frequenti sono "detto" e "Todd", il che può parere ovvio. Molti personaggi potrebbero parlare e, quando lo fanno, probabilmente stanno parlando riguardo al o al protagonista, se non sono il protagonista stesso, Todd.

Nota le parole che non vedi in questo elenco: parole come 'a' o 'the.' Parole come queste, quelle che chiamiamo **stopwords**, sono così comuni che spesso sono completamente escluse dalle analisi, il ragionamento è che diventano qualcosa di simile al rumore linguistico, mettendo in ombra le parole che potrebbero essere più significative per il documento. Ora, per vedere le parole che Voyant esclude per impostazione predefinita, passa con il mouse accanto al punto interrogativo nella parte superiore del riquadro e fai clic sulla seconda opzione da destra.&#x20;

![voyant settings](../assets/cyborg-readers/voyant-settings.jpg)

Utilizza l'elenco a discesa per passare da  'auto-detect' a 'none' (da 'rilevamento automatico' a 'nessuno'. Ora la concordanza ti mostrerà le effettive frequenze delle parole nel testo. Si noti che la frequenza di 'said' , cioè il risultato numero uno nel grafico originale, non si avvicina nemmeno all'uso di articoli, preposizioni e pronomi.

![Concordanze senza stopwords](../assets/cyborg-readers/stopword-free-concordance.jpg)

Parole come queste ricorrono con tale frequenza che spesso è necessario rimuoverle del tutto per ottenere risultati significativi. Ma l'elenco delle parole che potremmo voler rimuovere cambia a seconda del contesto. Ad esempio, la lingua non rimane stabile nel tempo. Decadi e secoli diversi hanno modelli linguistici diversi di cui potresti dover rendere conto. Gli studiosi shakespeariani potrebbero voler utilizzare un [elenco di stopwords dei primi tempi moderni ](https://github.com/ritategon/DH-INTRODUZIONE/blob/master/assets/early-modern-stopwords.txt)fornito da Stephen Wittek. Puoi usare questa stessa area di Voyant per modificare la stoplist per questa sessione di Voyant. In questo modo avrai un maggiore controllo sullo strumento e ti consentirà di adattarlo alle tue particolari domande di ricerca.&#x20;

Ci sono però alcuni casi in cui potremmo preoccuparci molto solo di queste _parole rumorose_. Possono dirci molto su come scrive un autore, cioè sul suo stile: infatti, quelle stesse parole che potrebbero sembrare non trasmettere molto sul contenuto sono gli elementi costitutivi dello stile di un autore. Manometti l'uso di preposizioni o pronomi da parte di qualcuno e cambierai rapidamente la natura della sua voce.&#x20;

Torniamo alla nuvola di parole. Utilizzando il dispositivo di scorrimento sotto la nuvola di parole, puoi ridurre o espandere il numero di termini visibili nella visualizzazione. Scorrilo completamente a destra per includere il numero massimo di parole.

![Nuvola di parole in Voyant in forma densa ](../assets/cyborg-readers/voyant-word-cloud-dense.jpg)

Proprio come l'elenco delle parole non significative può essere utilizzato per regolare i filtri per darti risultati significativi, questo dispositivo di scorrimento regola la visualizzazione che ottieni. Quando giochi con entrambe le opzioni, dovrebbe diventare chiaro che filtri e visualizzazioni diverse possono darti letture radicalmente diverse. I risultati sono tutt'altro che obiettivi: la tua lettura, lo strumento stesso e il modo in cui lo usi modellano i dati man mano che vengono conosciuti.&#x20;

Questo è un buon promemoria per ricordare che non dovresti pensare agli strumenti digitali come porte a verità fisse e chiare, né su periodi storici né su singoli testi. Voyant può sembrare in qualche modo obiettivo in quanto produce calcoli matematici e visualizzazioni di dati, ma ora hai visto che puoi facilmente modificare e manipolare i risultati. Queste tecniche di [Distant Reading ](../close-reading-2/close-reading.md)sono le stesse dei modelli di Close Reading di cui abbiamo parlato in precedenza, in quanto entrambe portano solo a porre più domande e a formulare più interpretazioni.&#x20;

Questa è una cosa buona.

### Interpreting Word Clouds

Dato che l'importante delle nuvole di parole non è tanto la produzione di visualizzazioni quanto l'interpretazione dei risultati, potresti chiederti in cosa la nuvola aiuti a imparare su _The String of Pearls._

Da un lato, si osserva che una delle parole più importanti è 'said', ma vedi anche 'dì' e "parla" e parole come "sì", "lo farò" e "oh" che probabilmente, anche se non necessariamente, provengono dai dialoghi scritti.&#x20;

Inoltre, la maggior parte delle parole sono brevi, lunghe una o due sillabe. Questo prodotto letterario, apparetenente al genere [_Penny dreadfuls_](https://it.wikipedia.org/wiki/Penny\_dreadful)  ('spaventi da un penny') era rivolto al pubblico della classe operaia: la prevalenza di queste parole relativamente 'semplici' potrebbe riflettere il pubblico del testo? Per corroborare una tale affermazione, probabilmente vorremmo guardare altre pubblicazioni del periodo per vedere se questo vocabolario fosse tipico o meno.

Se carichiamo "[A Scandal in Bohemia](https://www.gutenberg.org/files/1661/1661-h/1661-h.htm#1)" di Arthur Conan Doyle in Voyant, puoi vedere che otteniamo risultati abbastanza diversi. (Ancora una volta, sentiti libero di seguire.)

![Nuvola di parole di Scandal in Bohemia ](../assets/cyborg-readers/scandal-in-bohemia-word-cloud.jpg)

Una rapida occhiata mostra che le parole più comuni tendono ad essere più lunghe di quelle in _A String of Pearls_. In effetti, le tre sillabe 'fotografia' è uno dei termini più usati in questo racconto, scritto per un pubblico della classe media piuttosto che della classe operaia. Quindi forse il semplice vocabolario del _penny dreadful_ è legato alla natura dei suoi lettori.&#x20;

Ma non fermiamoci qui! Potresti anche notare che la nuvola di parole per _A Scandal in Bohemia_ ha molte parole legate allo status elevato: 'king', 'magesty', 'gentleman',' and 'lady' ('re', 'maestoso', 'gentiluomo' e 'ignora'), per esempio. Al contrario, con la possibile eccezione delle parole "colonel" and "sir"  ('colonnello' e 'signore') in _A String of Pearls_, in questo romanzo non ci sono quasi parole che si riferiscano al grado. Questo ti dà qualche indicazione che queste due opere sono ambientate in ambienti sociali diversi a Londra.

In alternativa, i tipi di parole in queste due opere non sono affatto uguali. La nuvola di parole per _A String of Pearls_ contiene molti verbi ('shall', 'said', 'come', 'know', 'suppose', 'thought' . tradotti, 'deve', 'ha detto', 'vieni', 'sapere', 'suppone', 'pensato'), mentre quella per _A Scandal in Bohemia_ è composta composto da molti nomi, in particolare quelli che si riferiscono a luoghi ('room', 'house', 'street', 'lodge', 'window', and 'adress', tradotti, 'stanza', 'casa', 'strada', 'lodge', 'finestra' e 'indirizzo'). Questa è una cosa interessante da notare, ma puoi comunque procedere e indagare cosa significhi nei due diversi testi. Forse _A String of Pearls_ è più interessato all'azione e all'eccitazione delle persone che fanno le cose rispetto a  _A Scandal in Bohemia_, dove l'enfasi è sul movimento e l'esplorazione di spazi diversi. O forse tutte queste osservazioni sono artefatti delle visualizzazioni, cose che suggeriscono le nuvole di parole, ma che potrebbero in realtà non reggere se poste al vaglio del controllo dei dati. Tutto questo non è ancora sufficiente: serve ulteriore riflessione.

Alcune di queste conclusioni probabilmente ti sono sembrate piuttosto ovvie. Probabilmente hai capito che _A String of Pearls_ è ambientato nella Londra della classe operaia, mentre _A Scandal in Bohemia_ si svolge in un ambiente più elevato. Potresti anche aver notato una differenza nel vocabolario, anche se l'uso di Voyant ha reso queste distinzioni più evidenti e ti ha fornito ulteriori dati a sostegno di qualsiasi affermazione che stavi facendo su di esse. Ma, probabilmente, non hai notato l'enfasi sull'azione rispetto all'importanza del luogo in queste due opere. Quindi questo è un buon esempio di come leggere con un occhio al computer possa portarti a nuove interpretazioni.

### Ulteriori Risorse <a href="#furtherresourcsupervisedclassifiers" id="furtherresourcsupervisedclassifiers"></a>

* Padre Busa: [1](https://it.wikipedia.org/wiki/Roberto\_Busa) e [2](https://www.ibm.com/easytools/runtime/hspx/prod/public/X0027/PortalX/page/pageTemplate?s=78c374df5c884363b46454a5ffefb5d9\&c=6623351d59604a11b2c845760f87280f).&#x20;
* Il testo prodotto da Geoffrey Rockwell and Stéfan Sinclair, i creatori di Voyant: [_Hermeneutica_](https://mitpress.mit.edu/books/hermeneutica).
* Introduzione alla ricerca umanistica con l'uso dei big data di Shawn Graham, Ian Milligan, and Scott Weingart [_Exploring Big Historical Data: The Historian's Macroscope_](http://www.themacroscope.org/2.0/).
