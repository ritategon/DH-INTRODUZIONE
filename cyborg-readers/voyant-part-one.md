# Voyant Parte 1

Useremo uno strumento chiamato [Voyant](http://voyant-tools.org) per introdurre alcuni argomenti di base nell'analisi del testo legati alla lettura cyborg.&#x20;

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

Just like the stopword list can be used to adjust the filters to give you meaningful results, this slider adjusts the visualization that you get. It should become clear as you play with both options that different filters and different visualizations can give you radically different readings. The results are far from objective: your own reading, the tool itself, and how you use it all shape the data as it comes to be known.

This is a good reminder that you should not think of digital tools as gateways to fixed and clear truths, either about historical periods or individual texts. Voyant may seem somehow objective in that it produces mathematical calculations and data visualizations, but now you've seen that you can easily alter the results. These techniques of "distant reading" are same as the models of "close reading" we talked about earlier in that both only lead to asking more questions and positing more interpretations.

That is a good thing.

Proprio come l'elenco delle parole non significative può essere utilizzato per regolare i filtri per darti risultati significativi, questo dispositivo di scorrimento regola la visualizzazione che ottieni. Quando giochi con entrambe le opzioni, dovrebbe diventare chiaro che filtri e visualizzazioni diverse possono darti letture radicalmente diverse. I risultati sono tutt'altro che obiettivi: la tua lettura, lo strumento stesso e il modo in cui lo usi modellano i dati man mano che vengono conosciuti. Questo è un buon promemoria per ricordare che non dovresti pensare agli strumenti digitali come porte a verità fisse e chiare, né su periodi storici né su singoli testi. Voyant può sembrare in qualche modo obiettivo in quanto produce calcoli matematici e visualizzazioni di dati, ma ora hai visto che puoi facilmente modificare i risultati. Queste tecniche di "lettura a distanza" sono le stesse dei modelli di "lettura ravvicinata" di cui abbiamo parlato in precedenza, in quanto entrambe portano solo a porre più domande e a formulare più interpretazioni. Questa è una buona cosa.

## Interpreting Word Clouds

Given that what's important about word clouds is not producing visualizations so much as the interpreting the results, you might ask: what does this help us learn about _The String of Pearls_?

For one, looking at these word clouds suggests that much of the vocabulary of this novel either refers to or exists in the context of speech. One of the most prominent words is "said," but you also see "say" and "speak" and words like "yes," "I'll," and "oh" which probably -- although not necessarily -- come from written dialog.

Additionally, most of the words are short, one or two syllables long. Penny dreadfuls like _The String of Pearls_ were aimed at working class audiences: could the prevalence of these relatively 'simple' words reflect the audience of the text? In order to substantiate such a claim, we would probably want to look at other publications of the period to see whether or not this vocabulary was typical.

If we load Arthur Conan Doyle's "[A Scandal in Bohemia](http://www.gutenberg.org/files/1661/1661-h/1661-h.htm#1)" into Voyant, you can see that we get quite different results. (Again, feel free to follow along.)

![scandal in bohemia word cloud](../assets/cyborg-readers/scandal-in-bohemia-word-cloud.jpg)

A quick glance shows that the most common words tend to be longer than those in _A String of Pearls_. Indeed, the three syllable "photograph" is one of the most frequently used terms in this short story, one written for a middle-class as opposed to working-class audience. So maybe the simple vocabulary of the penny dreadful _is_ related to the nature of its readership.

But let's not stop there! You may also notice that the word cloud for "A Scandal in Bohemia" has a lot of words related to high status: "king," "magesty," "gentleman," and "lady," for instance. In contrast, with the possible exception of the words "colonel" and "sir" in _A String of Pearls_, there are hardly any words in this novel that refer to rank. This gives you some indication that these two works are set in different social milieus in London.

Alternately, the types of words in these two works are not at all the same. The word cloud for _A String of Pearls_ contains a lot of verbs ("shall," "said," "come," "know," "suppose," "thought"), whereas that for "A Scandal in Bohemia" is made up of a lot of nouns, particularly those referring to places ("room," "house," "street," "lodge," "window," and "adress"). This is an interesting thing to note, but you still want to think about what this means about the two different texts. Perhaps _A String of Pearls_ is more concerned with action and on the excitement of people doing things than "A Scandal in Bohemia," where the emphasis is on moving through and exploring different spaces. Or maybe all of these observations are artifacts of the visualizations, things that the word clouds suggest but that might not actually hold up under scrutiny of the data. More thinking is needed!

Some of these conclusions were probably pretty obvious as you read these two works (or portions of them). You probably picked up the fact that _A String of Pearls_ is set in working-class London, whereas "A Scandal in Bohemia" takes place in a more elevated milieu. You might even have noticed a difference in vocabulary, even if using Voyant made these distinctions more apparent and gave you further data to back up any claims you were making about them. But you probably didn't notice the emphasis on action vs. the importance of place in these two works. So this is a good example of how reading with one eye to the computer can lead you to new interpretations.

## Further Resources

* Padre Busa: [1](https://it.wikipedia.org/wiki/Roberto\_Busa) e [2](https://www.ibm.com/easytools/runtime/hspx/prod/public/X0027/PortalX/page/pageTemplate?s=78c374df5c884363b46454a5ffefb5d9\&c=6623351d59604a11b2c845760f87280f).&#x20;
* Il testo prodotto da Geoffrey Rockwell and Stéfan Sinclair, i creatori di Voyant: [_Hermeneutica_](https://mitpress.mit.edu/books/hermeneutica).
* Introduzione alla ricerca umanistica con l'uso dei big data di Shawn Graham, Ian Milligan, and Scott Weingart [_Exploring Big Historical Data: The Historian's Macroscope_](http://www.themacroscope.org/2.0/).
