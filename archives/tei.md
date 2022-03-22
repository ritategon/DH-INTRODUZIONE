# Text Encoding Initiative

{% hint style="info" %}
Guarda l'immagine e prova a pensare alle implicazioni sottese. Quali sono i limiti e potenzialità dei due contesti?
{% endhint %}

{% embed url="http://digitalscholarship.ohio5.org/wp-content/uploads/2016/01/website_blog_scholar_screen2-768x663.jpg" %}

Cominciamo da questa poesia di Oscar Wild.&#x20;

{% hint style="info" %}
(Anzi prima di cominciare, se vuoi, prenditi una pausa, ma proprio con lo scopo di una pausa, con una interpretazione di questo testo di [Jeanne Moreau ](https://drive.google.com/file/d/1s\_ACW71qnJb2YjZ7Ui-QHDESJnYtOCl\_/view?usp=sharing)ripresa anche da Fassbinder "Querelle" del 1982).
{% endhint %}

```
  Yet each man kills the thing he loves
  By each let this be heard.
  Some do it with a bitter look,
  Some with a flattering word.
  The coward does it with a kiss,
  The brave man with a sword!
  
  Oscar Wilde, The Ballad of Reading Gaol 
```

Questo corso studia i testi e le cose che i computer possono fare con essi. Ma, mentre leggi, potresti notare che non possono fare molto. Molti dei metodi che vedrai sono semplicemente metodi sofisticati per contare le parole, mentre, come già sapevi e come [abbiamo visto](../close-reading-1/),  la lettura comporta processi di interpretazione e analisi molto più complicati. Quando leggiamo, tendiamo a saltare a comprensioni molto più complicate di un testo:

* Cosa significa questo ?&#x20;
* Quali elementi del testo trasmettono questo significato? Come lo fanno?

I computer hanno difficoltà con concetti astratti e tendono a lavorare in gerarchie e strutture ben definite e, anche allora, conoscono solo quelle strutture di cui qualcuno ha parlato loro. Ad esempio, se dovessimo dire a un computer: "Ehi! Trovami la poesia in questa lezione!" Non avrebbe idea di cosa stiamo parlando: dobbiamo trovare un modo per dire al computer dove può trovare la poesia. In questo momento pensa solo che il testo di Wilde postato sopra non sia diverso dalle altre righe di testo in questa pagina. È tutto solo testo.

Un programma per computer che lo esamina non riconoscere nemmeno quei sei versi come correlati in alcun modo. Non capiresce nulla di come i componenti interni di quelle linee siano collegati tra loro. Però esistono molte vie per rappresentare queste informazioni strutturali e possiamo fare sì che funzionino per un computer operando in un modo che tu come umano, attraverso un linguaggio e un sistema, puoi ti tuo utilizzare da solo durante la lettura.&#x20;

Pensa a tutte le annotazioni che metti sulle tue pagine mentre le leggi (ripensa allo scriba/copista dell'immagine che sta in apertura di questa sezione).  Ma immagina se dovessi annotare sistematicamente alcune caratteristiche strutturali del testo. Possiamo pensare al passaggio di Wilde, dopotutto, come a una serie di concetti annidati:

* C'è una strofa.&#x20;
* Questa strofa contiene alcuni versi.&#x20;
* Ogni riga ha del testo.
* Parte di quel testo contiene una rima.

E possiamo rappresentarlo graficamente, in questo modo, dove una linea nera denota i limiti della stanza, una blu orizzontale rappresenta le linee e i colori rotanti sotto le parole finali descrivono uno schema di rime:

![annotaree/marcare una poesia a mano](../assets/archives/tei-graphic.jpg)

Possiamo fare di meglio. Le seguenti annotazioni di testo sono un po' più chiare e si avvicinano a qualcosa che potremmo capire senza alcun contesto.&#x20;

![tei with text annotations](../assets/archives/tei.jpg)

Perché un computer lo capisca, abbiamo bisogno di un modo ancora più delineato per descrivere il passaggio. Dobbiamo prestare molta attenzione alla sintassi, ai modi in cui contrassegniamo cose particolari per fornire informazioni al computer. I computer richiedono linee guida sistematiche molto specifiche per poter elaborare le informazioni, come vedrai nella sezione sui [**Cyborg Readers**](../cyborg-readers.md). Ad esempio, dovremmo usare costantemente lettere minuscole per rappresentare schemi di rime. E "riga 1" per rappresentare la prima riga di una poesia invece di "riga uno". Abbiamo bisogno di un modo chiaro e uniforme e costante per descrivere le parti della poesia. Qualsiasi variazione a queste regole causerebbe effetti indesiderati e non intenzionali. Gli studiosi hanno lavorato per anni per sviluppare un tale sistema per descrivere i testi in un modo che possa essere elaborato dal software. La **Text Encoding Initiative (TEI)**, il risultato di questo lavoro, è un tentativo di rendere leggibili alle macchine concetti umanistici astratti. Se applichiamo  il TEI al passaggio, potrebbe iniziare ad assomigliare a questo:

```
<lg>
  <l>Yet each man kills the thing he loves</l>
  <l>By each let this be heard.</l>
  <l>Some do it with a bitter look,</l>
  <l>Some with a flattering word.</l>
  <l>The coward does it with a kiss,</l>
  <l>The brave man with a sword!</l>
</lg>
```

Nota che i nostri concetti come "stanza" e "linea" sono stati qui tradotti in tag particolari:

```
La stanza viene marcata <lg> (line grouping).
La linea viene marcata <l> (line).
Ogni set di tag ha sia una apertura (<lg>) che una chiusura (</lg>). 
I tag di chiusura sono quasi identici ai tag di apertura ad eccezione di una barra-slash - /.
I tag hanno relazioni intuitive con i concetti che rappresentano: <l> corrisponde alla linea e <lg> corrisponde al gruppo di linee
```

I tag di apertura e chiusura avvolgono e determinano le posizioni di particolari elementi strutturali per il computer: esiste una linea da qui a lì, una stanza esiste da qui a lì e così via. E prendi nota di come determinati tag possono esistere all'interno di altri. Questi elementi di inquadratura aiutano il computer a comprendere i confini dei concetti che stiamo descrivendo e aiutano a strutturare il testo. Pensa al TEI come a un nuovo livello che esiste sopra il testo. Le parole offrono un livello di significato, ma aggiungiamo nuovi livelli contrassegnando il testo con queste annotazioni fisse. Questo **markup** offre al computer (o ai futuri lettori) modi più sfumati di comprendere come le parti di un testo si relazionino tra loro.

Ecco come possiamo dare ulteriori dettagli alla poesia su cui siamo concentrati. Per esempio:

```
<lg type="poem">
  <lg type="stanza">
    <l>Yet each man kills the thing he loves</l>
    <l>By each let this be heard.</l>
    <l>Some do it with a bitter look,</l>
    <l>Some with a flattering word.</l>
    <l>The coward does it with a kiss,</l>
    <l>The brave man with a sword!</l>
  </lg>
  <lg type="stanza">
    <l> A short second stanza that we've made up.</l>
  </lg>
</lg>
```

Qui abbiamo aggiunto un gruppo di stanze extra e un tag esterno per indicare che questa è, in effetti, una poesia. Diamo anche **attributi** a determinati tag per fornire maggiori informazioni su di essi: type="stanza" dice al computer che il contenuto di questo tag si riferisce a una poesia. Ricordi la gerarchia nidificata di cui abbiamo parlato prima? Nota come la rappresentiamo graficamente per **indentazione**. L'elemento poetico esterno contiene due stanze, che contengono alcuni versi, e quelle hanno del testo. Puoi scorrere il testo e vedere la struttura. Alcuni linguaggi di programmazione in realtà commettono errori se non presti attenzione a queste cose. Ma, in ogni caso, ci aiuta solo a mantenere le cose pulite e facili da leggere.

Un'ultima cosa. Ricordi il nostro schema di rime e i numeri di riga? Possiamo codificare anche quelli:

```
<lg type="stanza">
    <l n="1" rhyme="a">Yet each man kills the thing he <rhyme>loves</rhyme></l>
    <l n="2" rhyme="b">By each let this be <rhyme>heard</rhyme>.</l>
    <l n="3" rhyme="c">Some do it with a bitter <rhyme>look</rhyme>,</l>
    <l n="4" rhyme="b">Some with a flattering <rhyme>word</rhyme>.</l>
    <l n="5" rhyme="d">The coward does it with a <rhyme>kiss</rhyme>,</l>
    <l n="6" rhyme="b">The brave man with a <rhyme>sword</rhyme>!</l>
  </lg>
```

We have added attributes to denote the line numbers for each line as well as the rhyme scheme, and then a new tag for each line denotes what word the rhyme is associated with. All of the tags used here can be found in the tutorial on poetry on the [TEI by Example](http://teibyexample.org/modules/TBED04v00.htm) page.

Once a text has been **encoded** in this way, it can be represented more easily in a digital form. This work may not necessarily actually make it _look_ any different. But it does allow you to do new and exciting things to your work. TEI encoding can make it possible to provide nuanced digital editions of a text. We could actually say to a program, pull out all the rhyming words in a poem. Or make them appear differently on a webpage. Or change them all to "TEI is the best."

Let's look at an example of something that's got a lot of encoding already in it. Here is the TEI for [this entry](http://www.oldbaileyonline.org/browse.jsp?id=t18881119-50\&div=t18881119-50\&terms=ripper#highlight) on a robbery case that mentions Jack the Ripper from the [Old Bailey Online](http://www.oldbaileyonlineorg). You might not recognize a lot of the tags (there are _loads_ of TEI tags), but the general arrangement of them should look familiar (full TEI [here](https://www.oldbaileyonline.org/browse.jsp?foo=bar\&path=sessionsPapers/18881119.xml\&div=t18881119-50\&xml=yes)):

![Jack the Ripper TEI](../assets/archives/old-bailey-tei.jpg)

Focus on what you do know: the tagging syntax should ring some bells. If you want to look up any of the tags, you can always check out the [TEI guidelines](http://www.tei-c.org/index.xml). A lot of working with technology consists of not panicking when you see something unfamiliar and then looking up what you don't know. But we digress.

When you look at the [public-facing version of the entry](https://www.oldbaileyonline.org/browse.jsp?id=t18881119-50\&div=t18881119-50\&terms=ripper#highlight) on the Old Bailey Online, almost all the tags disappear:

![Same entry without TEI](../assets/archives/old-bailey-sans-tei.jpg)

In order to make the text legible for readers, we very often hide most (or all) of the markup that is helping to present the document. This ensures that you can serve the needs of different audiences: some people might want to see the TEI for your text, but others might just want to be able to read it as normal. We have already talked a bit about the functions you can get from TEI, but, if they largely remain hidden, you might find yourself thinking that they might not be enough to warrant the amount of work that goes into putting together a TEI-encoded text.

Looking at the TEI tags for this document give you a sense of why you might encode a text even if not many people are going to look at the TEI. You'll see there are tags for the witnesses' names (both first and last) and their gender. Why might this be useful? Well, maybe the people who designed this site thought that users could conceivably want to search for the participants in a crime by name and by gender. That way you can ask all sorts of questions about what other crimes individuals witnessed, or whether men or women were more likely to be involved in or witness to particular types of crime.

Encoding is meant to convey abstract humanities concepts to the machine so that we can make better use of them in our digital work. Some of these concepts, like line breaks, might be pretty clear cut. Others might require a lot of interpretation. Even given the same set of tags and texts, two people could encode things differently. You can make a whole career off working with TEI, and we have just scratched the surface here. But encoding documents in TEI is an important step in preparing them for their lives as digital artifacts. Not all texts need to be encoded in TEI in order for them to be archived, but the vast majority of documents you will find in digital humanities archives have been encoded in this way. The process helps ensure that complex humanities data makes its way comfortably, ethically, and responsibly into the digital world.

### Ulteriori risorse

* TEI web editor [https://digital-editing.fas.harvard.edu/editor/](https://digital-editing.fas.harvard.edu/editor/)
* Ambiente di sviluppo integrato e collaborativo [https://atom.io/](https://atom.io)&#x20;
* Ambiente di annotazione e analisi collabaorativa [https://portal.catma.de/catma/](https://portal.catma.de/catma/)
* Di Jacob Heil una ottima argomentazione a favore delle pratiche di markup  "[Why We TEI](http://digitalscholarship.ohio5.org/2016/02/why-we-tei-2/)."
* Ryan Cordell in "[On Ignoring Encoding](http://ryancordell.org/research/dh/on-ignoring-encoding/)" fornisce una grande difesa della codifica testuale come parte fondamentale delle discipline umanistiche digitali.
* Introduzione al TEI in italiano [https://tei-c.org/Vault/P4/Lite/teiu5\_it.html](https://tei-c.org/Vault/P4/Lite/teiu5\_it.html)
* Teorie e pratiche nell’uso dell’XML/TEI per la codifica dei testi [https://www.iliesi.cnr.it/iniziative/XML-TEI.pdf](https://www.iliesi.cnr.it/iniziative/XML-TEI.pdf)

