# Investigating context-dependent mutation of antibody via masked language model

## Introduction

Epistasis is the phenomenon where the effects of mutations in a gene are dependent on the presence of mutations in other genes[ref]. In the context of antibody sequences, this means that the impact of a mutation in one part of an antibody might be influenced by mutations in other parts of the sequences[ref]. [sequencing_of_two_paragraphs]

Specifically, mutations in heavy chains [illustration] of antibodies are <u>emphasized</u> because <u>specific regions</u> on heavy chains are responsible for targeting antigens. Hence, their mutations play a <u>prominent role</u> in the binding specificity of antibodies. It is hence <u>important</u> to investigate the epistatisis of mutations on the heavy chains of antibody sequences, which can used to improve antibody designs in terms of binding affinity, statility and specificity[ref].
<!-- 重写 epistasis 对 antibody affinity 的影响 -->
Recent studies on quantitative analysis of epistasis of protein sequences, in general, have shed light on studies of epistatic mutations of antibodies in specific. Methods such as direct coupling analysis (DCA) are effective in diagnosing the correlations between mutations at different sites. For example, using the concept of Shannon entropy to quantify the diversity of amino acids observed at a specific site, a DCA model defines context-dependent entropy(CDE) and context-independent entropy(CIE). By comparing both, we could interpret to what extent, the mutations at a specific site depend on the rest of the sequence. The closer the two quantities are, the less context-dependent the mutations at a specific site are. <!-- 把这句话改 formal -->
However, some limitations are involved in DCA. For example, when analysing context-dependence of mutations at a specific site, DCA assumes conditional independence of other sites[ref] while pairwise correlation might not be sufficient in predicting properties of mutations at a specific site given the rest of the sequence. Another limitation of DCA is that it provides a single matrix representing the conditional distribution of <u>residues</u> given sites on the rest of the sequence, which may lack interpretability concerning the structure of heavy chains through treating some neighbouring sites as a holistic region.

In consideration of these two limitations, the masked language model is introduced to study the mutation effects of antibodies. As a masked language model (MLM) makes predictions on the masked symbol given the rest of the sequence, we can make a direct comparison of the <u>softmax</u> output of MLM and the results of DCA on the conditional distribution of symbols at the same site. Meanwhile, using a transformer with multi-head attention, more insights can be obtained by extracting the attention weights of each head. This helps interpret the context dependence of mutations concerning the structures of heavy chains via attention across different regions of the sequences.
<!-- 还是加一两句 transformeer 的介绍 -->

Fortunately, a few transformers specialized in antibody sequences have been trained and the method of training can be utilised to develop interpretable models in our cases. Specifically, the architecture of antiBERTa is adapted to train a masked language model. <!-- 介绍 bert -->

## Results

## Experimental procedures

A selection of 3146 heavy chain sequences from the SAbDab database[^sabdab] is used.
 
[^sabdab]: https://opig.stats.ox.ac.uk/webapps/sabdab-sabpred/sabdab/search/
