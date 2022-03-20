# Esercizio\*

{% hint style="info" %}
**Instruzioni**

In questa attività ti eserciterai ad applicare la struttura a una breve poesia_**.**_ Prima vedrai come codificare una breve poesia utilizzando la codifica TEI e poi avrai l'opportunità di esercitarti a taggare un'altra breve poesia.

Inizia leggendo e analizzando l'esempio fornito, inclusa la poesia di Milton.

Quindi applica lo stesso tipo di etichettatura all'esercizio che include la poesia di Keats.

(Suggerimento: potresti trovare più facile copiare e incollare la poesia dell'esercizio nel tuo documento di modifica del testo, applicare i tag, quindi copiare e incollare la tua risposta finale nello spazio fornito.)
{% endhint %}

### Un esempio&#x20;

Facciamo pratica applicando la struttura a dati non strutturati in un esempio reale dal vivo. Un esempio in cui potresti voler strutturare i dati è analizzare digitalmente la struttura delle rime di un corpus di poesie. Da solo, il tuo computer non saprà quali parole in una poesia rima, ma se tagghi quelle parole, puoi indicare lo schema di rime per qualsiasi poesia sul tuo computer. Useremo lo standard Text Encoding Initiative (TEI) che precedentemente è stato presentato.

Prendiamo 4 versi del sonetto VII di John Milton's:

(1) How soon hath Time, the subtle thief of youth,&#x20;

(2) Stolen on his wing my three and twentieth year!&#x20;

(3) My hasting days fly on with full career&#x20;

(4) But my late spring no bud or blossom shew'th.

In TEI si presenta come segue

```
<lg>
    <l>How soon hath Time, the subtle thief of <rhyme label="a">youth</rhyme>,</l>
    <l>Stolen on his wing my three and twentieth <rhyme label="b">year</rhyme>!</l>
    <l>My hasting days fly on with full <rhyme label="b">career</rhyme></l>
    <l>But my late spring no bud or blossom <rhyme label="a">shew'th</rhyme>.</l>
</lg>
```

Per indicare l’inzio di ogni riga  si usa il tag  "\<l>" e per indicare la fine di ogni riga , si usa il tag        "\</l>" .

Similmente, per  indicare l’inizio di un gruppo di righe si usa  il tag  "\<lg>" e per indicare la fine dello stesso gruppo di linee si usa il tag  "\</lg>".

Allo stesso modo, marchiamo l’inizio di una parola in rima con il tag \<rhyme> e la fine con il tag \</rhyme> .

La rima dei 4 versi è ABBA ("youth" rima con  "shew'th" e "year" con "career"), così marchiamo le parole finali dei versi  1 e 4 con "a"  e le finali dei versi  2 e3 con  "b".&#x20;

Ora, che hai compreso le basi dei tag TEI, annota la  quantina che segue, indicando lo schema delle rime e le divisioni di riga nello stesso modo di cui sopra. Esamineremo il lavoro insieme.

**Francesco Petrarca: "Solo et pensoso i più deserti campi"**

1\) Solo et pensoso i più deserti campi\
2\) vo mesurando a passi tardi et lenti,\
3\) et gli occhi porto per fuggire intenti\
4\) ove vestigio human l’arena stampi.

