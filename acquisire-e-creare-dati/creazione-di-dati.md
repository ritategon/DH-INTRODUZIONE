# Creazione di Dati

I dati delle Digital Humanities sono spesso generati da fonti fisiche e analogiche. Ad esempio, se si desidera digitalizzare un libro raro del XVI secolo, è possibile recuperare il libro fisico, fotografare le pagine ed eseguire il riconoscimento ottico dei caratteri (OCR; su questo tema e sui problemi connessi vedi anche [qui](../data-cleaning/problems-with-data/) e [qui](../issues/google-ngram.md)) per riconoscere i caratteri scritti e trasformare le immagini in un formato di file di testo. In questa sezione, partendo proprio dall'OCR, esploreremo diverse modalità di digitalizzazione comuni all'interno delle Digital Humanities, che vanno dalla digitalizzazione del testo alla digitalizzazione dei manufatti archeologici, insieme a esempi del loro utilizzo.

### Digitalizzazione di testi con OCR

La digitalizzazione di testo analogico può essere una sfida in quanto comporta la trasformazione di qualsiasi cosa, dal testo scritto a mano a quello stampato, in rappresentazioni di testo digitali. In genere, i professionisti delle discipline umanistiche digitali utilizzeranno una strategia computazionale chiamata Optical Character Recognition (OCR) per riconoscere automaticamente i caratteri di testo nelle immagini scattate da un testo. Questo può essere un approccio rapido ed efficace per creare dati di testo digitali da un'origine testuale analogica, senza dover trascrivere manualmente i dati di testo. Tuttavia, in alcuni casi, l'OCR non funziona e i professionisti di Digital Humanities potrebbero dover trascrivere manualmente alcuni dati di testo (vedi esempio sotto). Esempio: se si desidera digitalizzare un libro raro del XVI secolo, è possibile recuperare il libro fisico, fotografare le pagine ed eseguire il riconoscimento ottico dei caratteri (OCR) per riconoscere i caratteri scritti e trasformare le immagini in un formato di file di testo. Vedi sotto per un flusso di lavoro idealizzato per tale digitalizzazione.

Vedi sotto un utile schema del workflow di digitalizzazione&#x20;

{% embed url="https://courses.edx.org/asset-v1:HarvardX+DigHum_01+1T2019+type@asset+block@Idealized_Digitization_Workflow.jpg" %}
Ideal Digitization Workflow - Created by Ceilyn Boyd for HarvardX
{% endembed %}

L'esecuzione dell'OCR non garantisce necessariamente che il testo sia interpretabile dal computer.

{% hint style="info" %}
Esempio di lettura OCR fallita su un testo scritto a mano_:_

i _j cm_

_C o ^ ^ j\&i z?i f 3/ J_&#x20;

_tjle < jL/f-} 0 -el\<x.c^> i j^v/awi^i A 3$ #4| £5 7# /o J ''"^ ;3_

&#x20;_(P\&AAjuk ^->^Wa'^ -f /o'/j_ _/_ ^ ^3\*
{% endhint %}

Pertanto, se l'OCR non riesce, potrebbero essere necessari passaggi aggiuntivi, come l'identificazione manuale di parole e caratteri. Nota che il testo scritto a mano, con i suoi caratteri più idiosincratici, non viene riconosciuto con successo dal computer, ma il testo stampato viene riconosciuto con successo. Vedi su questo la sezione [Micro e Macro Tasking](../crowdsourcing/crowdsourcing.md) in Crowdsourcing" per i dettagli su come digitalizzare con maggiore successo un testo così eccentrico.

### Digitalizzare gli oggetti

Molti professionisti delle discipline umanistiche, come archeologi e storici dell'arte, studiano il mondo più ampio degli oggetti creati dagli esseri umani, così come i loro testi. Tali oggetti possono includere le immagini che le persone scattano, le opere d'arte fisiche che producono o gli oggetti utilitaristici quotidiani che usano.

I professionisti delle DH potrebbero voler digitalizzare oggetti per una serie di motivi. Ad esempio, alcuni professionisti cercano di comprendere le proprietà degli oggetti su scala aggregata o statistica tramite strategie computazionali. In questo caso, la digitalizzazione di oggetti potrebbe comportare la raccolta di dati tabulari che contengono misurazioni su un artefatto e la sua rappresentazione digitale in database relazionali. Altri digitalizzano oggetti in modo da presentarli a un pubblico più ampio. Gli oggetti che cercano di rappresentare, ad esempio, potrebbero essere a rischio di essere distrutti e richiedere almeno la conservazione digitale. Inoltre, gli oggetti nei musei possono essere accessibili solo a un piccolo gruppo di persone, rendendo necessaria la digitalizzazione degli oggetti per condividerli più ampiamente con il mondo. Ai fini della presentazione, è spesso più efficace acquisire immagini bidimensionali ad alta risoluzione o scansioni tridimensionali degli oggetti, in modo che possano essere vissute in modi simili all'artefatto analogico originale. Esempio: un esempio di digitalizzazione di oggetti è il [Progetto Giza](http://giza.fas.harvard.edu), descritto nella sezione [Esempi di DH](../esempi-di-dh/). Gli studiosi hanno utilizzato una vasta quantità di informazioni (misure archeologiche, immagini, ecc.) per realizzare una ricostruzione virtuale tridimensionale dell'altopiano di Giza come poteva sembrare quando era costruito per la prima volta, fornendo nuovi modi per vedere, esplorare e imparare sulle piramidi e sui cimiteri circostanti.

### Digitalizzare Informazioni Audiovisive&#x20;

Sia che studino musica dal vivo, sia che cerchino di catturare visivamente l'esperienza umana, altri professionisti delle discipline umanistiche digitali registrano digitalmente informazioni sul mondo che li circonda tramite immagini, video e audio. Potrebbe anche essere necessario convertire i moduli analogici (ad es. fotografie su carta, nastri o dischi in vinile) in digitali per consentire analisi digitali uniche di questi diversi moduli. I moduli digitali facilitano anche la presentazione (e la conservazione per) un nuovo pubblico attraverso servizi popolari come YouTube. Inoltre, le scansioni di immagini ad alta risoluzione o la rappresentazione digitale di audio e video possono consentire ai ricercatori di insegnare ai modelli di apprendimento automatico a identificare caratteristiche particolari nei dati che l'occhio umano non è in grad di cogliere.
