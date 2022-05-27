# Text Encoding Initiative

{% hint style="info" %}


Guarda l'immagine e pensa alle implicazioni sottese. Quali sono i limiti e potenzialità dei due contesti?
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

Abbiamo aggiunto attributi per marcare i numeri di riga per ogni riga così come lo schema delle rime, quindi un nuovo tag per ogni riga denota a quale parola è associata la rima. Tutti i tag utilizzati qui possono essere trovati nel tutorial sulla poesia nella pagina [TEI by Example.](https://teibyexample.org/tutorials/TBED04v00.htm)

Una volta che un testo è stato **codificato** in questo modo, può essere rappresentato più facilmente in forma digitale. Questo lavoro potrebbe non necessariamente farlo sembrare diverso. Ma ti permette di fare cose nuove ed interessanti. La codifica TEI può consentire di fornire edizioni digitali sfumate di un testo. Potremmo davvero dire a un programma, tirare fuori tutte le parole in rima presenti in una poesia. Oppure falli apparire in modo diverso su una pagina web.

Diamo un'occhiata a un esempio di qualcosa che contiene già molta codifica. Andiamo nella[ Cambridge Digital Library](https://cudl.lib.cam.ac.uk/collections/leopardi/3). Prendiamo una lettera di Leopardi a suo padre, Monaldo  ([MS Add.6210](https://cudl.lib.cam.ac.uk/view/MS-ADD-06210-00018/1)).&#x20;

![](../.gitbook/assets/screenshot-cudl.lib.cam.ac.uk-2022.03.22-13\_58\_58.png)

Puoi osservare che non vedi codifica TEI. Ora guarda sotto e scopri cosa c'è dietro le quinte:

```xml
<?xml-model href="../schema/tei_dj.rng" type="application/xml" schematypens="http://relaxng.org/ns/structure/1.0"?>
<TEI xmlns="http://www.tei-c.org/ns/1.0" xml:id="manuscript_1">
   <teiHeader>
      <fileDesc>
         <titleStmt>
            <title>MS/ADD/6210/18</title>
         </titleStmt>
         <publicationStmt>
            <publisher/>
            <availability xml:id="displayImageRights" status="restricted">
               <p>Public domain.</p>
            </availability>
            <availability xml:id="downloadImageRights" status="restricted">
               <licence>Images made available for download are licensed under a Creative Commons
                  Attribution-NonCommercial 3.0 Unported License (CC BY-NC 3.0)</licence>
            </availability>
            <availability xml:id="metadataRights" status="restricted">
               <licence>This metadata is licensed under a Creative Commons Attribution-NonCommercial
                  3.0 Unported License.</licence>
            </availability>
         </publicationStmt>
         <sourceDesc>
            <msDesc>
               <msIdentifier>
                  <repository>Cambridge University Library</repository>
                  <idno>MS Add.6210.18</idno>
               </msIdentifier>
               <msContents>
                  <summary> </summary>
                  <msItem xml:id="Letter_1">
                     <title>Letter from Giacomo Leopardi to Monaldo Leopardi</title>
                     <textLang mainLang="ita">Italian</textLang>
                  </msItem>
               </msContents>
               <physDesc>
                  <objectDesc form="leaf">
                     <supportDesc material="paper">
                        <support>Paper with <watermark/> watermark</support>
                        <extent>2 pages </extent>
                     </supportDesc>
                  </objectDesc>
                  <handDesc>
                     <handNote xml:id="hand-1" scope="major" medium="thin-brown-ink">Giacomo
                        Leopardi, thin-brown ink.</handNote>
                     <handNote xml:id="hand-2" scope="minor" medium="pencil">Archivist,
                        annotation.</handNote>
                  </handDesc>

               </physDesc>

               <history>
                  <origin>
                     <origDate calendar="Gregorian" when="18270623">23 Giugno 1827</origDate>
                     <origPlace key="3176958">Firenze</origPlace>
                  </origin>
               </history>
            </msDesc>

            <listPerson>

               <person xml:id="pers-1">
                  <persName key="12311353">
                     <forename>Giacomo</forename>
                     <surname>Leopardi</surname>
                  </persName>
               </person>

               <person xml:id="pers-14">
                  <persName key="9709149068390265730006">
                     <forename>Monaldo</forename>
                     <surname>Leopardi</surname>
                  </persName>
               </person>

               <person xml:id="pers-38">
                  <persName key="1569009">
                     <forename>Adelaide</forename>
                     <surname>Antici</surname>
                  </persName>
               </person>

            </listPerson>

            <listPlace>

               <place xml:id="pla-1">
                  <placeName key="6541846">Recanati</placeName>
               </place>

               <place xml:id="pla-6">
                  <placeName key="3176958">Firenze</placeName>
               </place>

               <place xml:id="pla-7">
                  <placeName key="3181927">Bologna</placeName>
               </place>

            </listPlace>

         </sourceDesc>

      </fileDesc>

      <encodingDesc>
         <classDecl>
            <taxonomy>
               <category xml:id="top-1">
                  <catDesc>Information request</catDesc>
               </category>
               <category xml:id="top-2">
                  <catDesc>Greetings</catDesc>
               </category>
               <category xml:id="top-10">
                  <catDesc>Giving information</catDesc>
               </category>
            </taxonomy>
         </classDecl>
      </encodingDesc>
      <profileDesc>

         <correspDesc>
            <correspAction type="sent">
               <persName key="12311353">Leopardi, Giacomo, 1798-1837</persName>
               <date when="18270623">23 Giugno 1827</date>
            </correspAction>
            <correspAction type="received">
               <persName key="9709149068390265730006">Leopardi, Monaldo, 1776-1847</persName>
            </correspAction>
         </correspDesc>

         <creation>
            <listChange ordered="true">
               <change xml:id="change-1">Main body of letter, Giacomo Leopardi.</change>
               <change xml:id="change-2">Address, Giacomo Leopardi.</change>
               <change xml:id="change-3">Stamp.</change>
               <change xml:id="change-4">Annotation, Archivist.</change>
            </listChange>
         </creation>

      </profileDesc>
      <revisionDesc>
         <change when="20210724"><persName>Gioele Marozzi</persName> revised header and added
            transcription</change>
      </revisionDesc>
   </teiHeader>
   <facsimile>
      <graphic decls="#document-thumbnail" rend="portrait" url="MS-ADD-06210-000-00057"/>
      <surface xml:id="i1" n="1r">
         <graphic decls="#downloadImageRights #download" height="5652px" width="3928px"
            rend="portrait" url="MS-ADD-06210-000-00057"/>
      </surface>
      <surface xml:id="i2" n="1v">
         <graphic decls="#downloadImageRights #download" height="5497px" width="3783px"
            rend="portrait" url="MS-ADD-06210-000-00058"/>
      </surface>
   </facsimile>
   <text>
      <body>
         <div n="1">

            <pb n="1r" xml:id="pb-1r" facs="#i1"/>
            <div n="2">

               <fw type="other" change="#change-3">27 GIUGNO</fw>

               <fw type="other" change="#change-3">
                  <placeName ref="#pla-6">FIRENZE</placeName>
               </fw>

               <p change="#change-2" hand="#hand-1" rend="center">Al Nobil Uomo<lb/> Il
                        <choice><abbr>Sig.</abbr><expan>Signor</expan></choice> Conte <persName
                     ref="#pers-14">Monaldo Leopardi</persName><lb/>
                  <placeName ref="#pla-1">Recanati</placeName><lb/> Stato Romano </p>

            </div>
            <pb n="1v" xml:id="pb-1v" facs="#i2"/>

            <div n="3" change="#change-1" hand="#hand-1" ana="#top-1 #top-2 #top-10">

               <opener>
                  <dateline><placeName ref="#pla-6">Firenze</placeName> 23 Giugno 1827</dateline>
                  <salute>Carissimo <choice><abbr>Sig.</abbr><expan>Signore</expan></choice>
                     <rs ref="#pers-14">Padre</rs></salute>
               </opener>

               <p><seg rend="insetLeft5">Partii da <placeName ref="#pla-7">Bologna</placeName> ai
                     20, e il giorno seguente, la mattina,</seg><lb/> arrivai a
                     <placeName>Firenze</placeName>, dopo un viaggio ottimo. Non so quanto mi
                  tratterrò.<lb/> Il non poter uscir di casa di giorno per la flussion d'occhi
                  che<lb/> mi molesta costantemente, mi dà molta malinconia, e m'impedisce di<lb/>
                  conoscere la città; nella quale veramente non godo nulla. Sono obbliga-<lb/> to a
                  rifiutare tutti gl'inviti che mi vengono fatti, e la gran festa<lb/> fiorentina di
                  domani (giorno di <choice><abbr>S.</abbr><expan>San</expan></choice>
                  <choice><abbr>G.</abbr><expan>Giovanni</expan></choice> Battista) sarà per me
                  un<lb/> giorno feriato. Gli altri avranno corse di bighe, corse di barberi<lb/>
                  dei primi d'Italia, fuochi artifiziali che costano non so quante<lb/> migliaia,
                  ec. Faccia, la prego, i miei saluti più teneri alla <rs ref="#pers-38">Mam-<lb/>
                     ma</rs> e ai fratelli. Sono impaziente di sentire che la <rs ref="#pers-38"
                     >Mamma</rs><lb/> sia perfettamente guarita del piede. Le bacio la mano con
                  tutta<lb/> l'anima, e le chiedo la benedizione.</p>

               <closer>
                  <salute>Il suo amorosissimo figlio</salute>
                  <lb/>
                  <signed><persName ref="#pers-1">Giacomo</persName>.</signed>
               </closer>

            </div>

            <div n="4">

               <fw change="#change-4" hand="#hand-2" place="bottomLeft">1</fw>

            </div>




         </div>

      </body>
   </text>
</TEI>
```

Per rendere il testo leggibile per i lettori, la maggior parte (o tutto) del markup che aiuta a presentare il documento viene nascosto. Ciò garantisce che tu possa soddisfare le esigenze di un pubblico diverso: alcune persone potrebbero voler vedere il TEI del testo, ma altri potrebbero semplicemente volerlo leggere normalmente. Abbiamo già parlato un po' delle funzioni che puoi ottenere dal TEI, ma, se rimangono in gran parte nascoste, potresti chiederti cosa giustifichi la quantità di lavoro necessaria per mettere insieme un testo con codifica TEI .

Ebbene i tag TEI permettono di interrogare il testo, cosa da cui si aprono infinite implicazioni che scoprirai via via, seppure in modo non approfondito.

La codifica, dunque, ha lo scopo di trasmettere concetti umanistici astratti alla macchina in modo che possiamo farne un uso migliore nel nostro lavoro digitale. Alcuni di questi concetti, come le interruzioni di riga, potrebbero essere abbastanza chiari. Altri potrebbero richiedere molta interpretazione. Anche con lo stesso insieme di tag e testi, due persone potrebbero codificare le cose in modo diverso. Puoi fare un'intera vita lavorando con  il TEI e qui abbiamo appena scalfito la superficie. Ma la codifica dei documenti in TEI è un passo importante per prepararli alla loro vita come artefatti digitali. Non tutti i testi devono essere codificati in TEI per poter essere archiviati, ma la stragrande maggioranza dei documenti che troverai negli archivi di scienze umane digitali è stata codificata in questo modo. Il processo aiuta a garantire che i dati complessi delle discipline umanistiche si facciano strada comodamente, eticamente e responsabilmente nel mondo digitale.

### Ulteriori risorse

* TEI web editor [https://digital-editing.fas.harvard.edu/editor/](https://digital-editing.fas.harvard.edu/editor/)
* Ambiente di sviluppo integrato e collaborativo [https://atom.io/](https://atom.io/)&#x20;
* Ambiente di annotazione e analisi collabaorativa [https://portal.catma.de/catma/](https://portal.catma.de/catma/)
* Di Jacob Heil una ottima argomentazione a favore delle pratiche di markup  "[Why We TEI](http://digitalscholarship.ohio5.org/2016/02/why-we-tei-2/)."
* Ryan Cordell in "[On Ignoring Encoding](http://ryancordell.org/research/dh/on-ignoring-encoding/)" fornisce una grande difesa della codifica testuale come parte fondamentale delle discipline umanistiche digitali.
* Introduzione al TEI in italiano [https://tei-c.org/Vault/P4/Lite/teiu5\_it.html](https://tei-c.org/Vault/P4/Lite/teiu5\_it.html)
* Teorie e pratiche nell’uso dell’XML/TEI per la codifica dei testi [https://www.iliesi.cnr.it/iniziative/XML-TEI.pdf](https://www.iliesi.cnr.it/iniziative/XML-TEI.pdf)
