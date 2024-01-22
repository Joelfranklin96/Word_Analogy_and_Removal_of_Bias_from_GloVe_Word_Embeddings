# Word Analogy and Removal of Bias from GloVe Word Embeddings

1) The word analogies such as (Man:Woman as Boy:?) and (India:Delhi as Japan:?) were found out by measuring the cosine similarities between the GloVe embedding vectors.
2) The cosine similarity between (e_man - e_woman) and (e_boy - e_word) would be maximum when the word embedding is 'girl'.
3) There were other word analogies such as (Man:Woman as Doctor:Nurse) and (Man:Woman as Computer_Programmer:Homemaker) which had 'bias'.
4) The 'bias' was removed from the GloVe word embeddings by neutralization of non-gender specific word embeddings and equalization of gender specific pairs of embeddings.
5) Neutralization -  First the direction of 'bias' was calculated. (e_man - e_woman) would give us the 'bias' direction. We considered 2 more gender specific common pairs and averaged the result. Then the component of non-gender specific word embeddings along the 'bias' direction was made zero.
6) Equalization - The gender specific pairs such as ('man' & 'woman'), ('boy' & 'girl'), ('father' & 'mother'), etc were made equidistant from the axis orthogonal to 'bias' axis without changing the word embedding's meaning. Since after neutralization, the non-gender specific word embeddings would lie on the axis orthogonal to 'bias' axis, they would also be equidistant from the equalized gender specific pair of embeddings, thus removing the 'bias'.
