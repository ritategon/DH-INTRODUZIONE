# Sentiment Analysis

We began this book by talking about interpretation on a micro level: close reading asks you to pay attention to every small detail in a text to produce analysis. We have since zoomed out to think about what we could gain from macro reading and how computers enable us to understand texts in new ways. In our final moments, we will loop back around to the beginning.

We have repeatedly stressed the interplay of computation and interpretation: when the computer presents some results to you, your work has only begun. The computer can supply data, but you must interpret that data yourself. The computer does not really read. You do. What you've learned about is how to read _with_ computers.

But you have probably also noticed in the last few chapters that the kinds of readings we are using our computers for have become more sophisticated. When we use software to discover the topics a text is discussing or to identify anonymous authors, we are not quite having them read in the same way as a person would. But we are getting closer. These techniques aim to provide a richer sense of a text, and they do so in quite sophisticated ways. We will close with a somewhat simpler problem, but one that is profoundly difficult for computers: is a particular text happy or sad? For that matter, is a sentence? A word?

This type of analysis that tries to capture the emotional resonance of a text is called **sentiment analysis**. You've probably engaged with this kind of work without realizing it. If you've ever been to [Rotten Tomatoes](https://www.rottentomatoes.com) to see what score a movie has gotten, you are looking at an aggregated number of reviews that have been marked as positive or negative. Businesses have a stake in such things as well. If you tweet about your recent flight, the airline would probably want to know whether you hated it or loved it. The former might result in you being directed to customer service, while the latter could result in a benign response like "thanks for flying with us!"

Sentiment analysis can also offer interesting opportunities for textual analysis. Check out this clip of a lecture by Kurt Vonnegut:

The idea makes enough sense as Vonnegut presents it: at certain times in a story, things are varying degrees of good or bad. As with any form of text analysis, this kind of information could be very useful for understanding a text.

* What kind of emotions does the author employ in the text? When?
* How do emotions map onto other aesthetic categories, like narrative structure?

It would be fascinating to have a computer that could easily mark the sentiments in texts for you. If you have been following dutifuly along, however, you should know that computers can't do much of anything without being explicitly told how. They can do very little in the way of understanding data without a human to guide them. Trying to extract complicated information like the sentimental arc of a text, how we are meant to feel about a sentence, or how an author intended us to feel are all complicated tasks that computers have a difficult time with. In fact, they can be hard for two different people to agree on. Try to guess whether these two sentences would be classified as good or bad:

* "I am very happy."
* "She is so sad."

Those were easy ones: good and bad. Hot and cold. How about this one:

* "It was the best of times, it was the worst of times…"

This sentence is from Charles Dickens's _Tale of Two Cities_ and is probably a bit hard to parse in such a binary way. If it is both good and bad, it probably comes out as neutral, right? But Dickens was talking about the era of the French Revolution here; his whole point was that this was an extraordinary time, hardly a "neutral" situation. In fact, he is interested in juxtaposing different things - best/worst, London/Paris, etc. - not in resolving them. We would probably need some system for determining what to do in such situations.

Try this sentence, by Jane Austen, which complicates matters even further:

* "It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife."

An avid reader of Austen would know that her texts come loaded with satire. It is unlikely she actually means her words to be taken at face value. Virtually no truths actually are _universally_ acknowledged to be true, so the sentence winks at the reader and should not be taken in full seriousness. In fact, much of her work is meant as a scathing criticism of the culture and people around her. These opinions are largely indirect, couched in irony and satire that asks the reader to read against what the text says on the surface.

All of these things are difficult to convey to readers, let alone computers. Sentiment analysis through technology is tricky, but that doesn't mean that researchers don't try. The process is difficult and riddled with error, but also intellectually interesting in a number of ways.

* How do we map complicated abstract ideas like emotion in a way that computers could understand them?
* What can sentiment analysis like this tell us about the objects that we study?

As with any form of text analysis, the potential uses range as widely as your imagination. One compelling recent [use of sentiment analysis](http://varianceexplained.org/r/trump-tweets/) by David Robinson sought to gauge the degree of control that Donald Trump's campaign had over his Twitter account. Knowing that Trump tended to use a Samsung Galaxy to tweet, Robinson wanted to determine if tweets from different techonologies might have different characteristics. If so, one could reasonably separate out his personal persona on Twitter from the one curated by his campaign stuff. Robinson found that we could reasonably determine that the angrier, more hyperbolic tweets came from a Samsung Galaxy (and were more likely to be by Trump himself). The tweets from iPhones were more likely to be "fairly benign declarations." With this knowledge we could reasonably trace the thumbprint of the Trump campaign handlers as distinct from Trump himself.

Computers might not be able to feel, but perhaps we can train them to know what emotions look like. The very idea of measuring sentiment computationally is provocative. If we were working in big business, we would care a lot about the results of such projects. But, as humanists, we can also gain a lot just from trying to model such complicated topics. The process is as enlightening as the product.

### Ulteriori Risorse <a href="#furtherresourcsupervisedclassifiers" id="furtherresourcsupervisedclassifiers"></a>

* "[The Universal Shapes of Stores, According to Kurt Vonnegut](http://io9.gizmodo.com/the-universal-shapes-of-stories-according-to-kurt-vonn-1526559996)" has a brief explanation of Vonngeut's relationshop to the theory about plot trajectories.
* [Matthew L. Jockers](https://orcid.org/0000-0001-5599-3706) ha una serie di post sul suo progetto di sentiment analysis che inizia [qui](https://www.matthewjockers.net/2015/02/02/syuzhet/). In questi post trovi la connessione alla clip di Vonnegut.
