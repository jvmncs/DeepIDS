KDDCup99 dataset issues
===
We were first alerted to the problems inherent to the KDDCup99 dataset through [this feature in KDNuggets](http://www.kdnuggets.com/news/2007/n18/4i.html) from Terry Brugger.  Although he makes some mistakes<sup>1</sup> in conflating it with aspects of the original DARPA/Lincoln Labs dataset, he points to some legitimate research on it.  The most thorough analysis can be found in [Tavallaee et al](http://www.ee.ryerson.ca/~bagheri/papers/cisda.pdf).


The problems with KDDCup99 found in Tavallaee et al can be summarized as follows:
1. Severe and unrealistic class imbalance
2. Tons of duplicate samples (75-78%)
3. Most samples are too easily classified for benchmarking based on accuracy/false positive rate

The first two problems make it harder to learn useful models from the dataset, while the third prevents us from measuring false positive rate with precision.  We're not so concerned with the first two, since we managed to develop a pretty strong model despite these.

The third, however, is cause for concern.  This third factor is why we plan on reevaluating our model on the improved NSL-KDD dataset.

Since false positive rate is factored into recall, our results on recall are harder to interpret.  However, our superior performance on precision should suggest that the ensemble of deep nets developed here is viable as a powerful IDS.

<sup>1</sup> For example, TLL, which was known to nearly linearly separate benign vs. malicious connections on its own, was included as a feature in DARPA. Brugger claims this is true of KDDCup99 as well, which is false according to [Tavallaee et al](http://www.ee.ryerson.ca/~bagheri/papers/cisda.pdf).
