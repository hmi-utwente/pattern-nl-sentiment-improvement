## Dictionaries used in our experiments

This folder contains the dictionaries we used in the paper, and some extra ones that have not been included in the article (but also didn't improve the performance).

In each folder there will be a *nl-sentiment.xml* file, which can be used to replace Pattern's original file of the same name. The original file is found inside the folder where Pattern was installed as a Python library (e.g. *$PYTHON_ENV_FOLDER/pattern3.6/lib/python3.6/site-packages/pattern/text/nl*). 

For running experiments with different dictionaries it is generally handier to copy the *nl* folder inside *pattern/text*, giving it another name (e.g. *nlmoors*) and replacing *sentiment.xml* inside the new folder with the new dictionaries. You can now import the two dictionaries side by side in Python, for example:

    import pattern.nl
    import pattern.nlmoors
    text = 'ik ben niet blij'
    orig_score = pattern.nl.sentiment(text)[0]
    nlmoors_score = pattern.nlmoors.sentiment(text)[0]
    

The folder *5.1.1 Pattern + Moors without stopwords* contains the lexicon for the experiment described in section 5.1.1. 

Inside *5.1.4 Pattern + Moors without neutral bins* there are the lexicon with different threshold as used in the experiments of section 5.1.4. The subfolder *Threshold 005* contains the lexicon where words with sentiment value between -0.05 and +0.05 were removed, *Threshold 015* is the lexicon without words between -0.15 and +0.15, and so on.

Finally, inside *Other dictionaries*, there are a dictionary with all of Moors'et al. lexicon, including stopwords, and one where part-of-speech tags are assigned to each new word from Moors', so that if you use the full lemmatization pipeline of Pattern it can distinguish between words with same spelling but different PoS and different sentiment values.

