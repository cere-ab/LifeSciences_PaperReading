<script type="text/javascript"
   src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js">
</script>

<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [['$','$'], ['\\(','\\)']],
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'] // removed 'code' entry
        }
    });
    MathJax.Hub.Queue(function() {
        var all = MathJax.Hub.getAllJax(), i;
        for(i = 0; i < all.length; i += 1) {
            all[i].SourceElement().parentNode.className += ' has-jax';
        }
    });
</script>



# Paper Review: Gene2vec

## Table of Contents
1. [Jargon Glossary](#jargon-glossary)
2. [Problem Description](#problem-description)
3. [Problem Relevance](#problem-relevance)
4. [Proposed Solution](#proposed-solution)
5. [Positive Points](#positive-points)
6. [Negative Points](#negative-points)
7. [Questions](#questions)
8. [References](#references)

## Jargon Glossary
[_back to contents_](#table-of-contents)

>**term** - description

## Problem Description
[_back to contents_](#table-of-contents)

TODO

## Problem Relevance
[_back to contents_](#table-of-contents)

TODO

## Proposed Solution
[_back to contents_](#table-of-contents)

TODO

```mermaid
%%{init: {
    'theme':'forest',
    'themeVariables': {
        'primaryColor': '#66ff23',
        'secondaryColor': '#99bbff',
        'tertiaryColor': '#22ccff'
    },
    'mermaidMaxSourceCharacters': 5000
}}%%
mindmap
    root )deepSimDEF(
        1- Experimental<br/>Data
            {{input<br/>embedding}}
                (Medline<br/>Bigram)
            {{Protein<br/>Protein<br/>Interaction}}
                (STRING)
            {{Protein<br/>Sequence<br/>Homology}}
                (UniProt in<br/>"FASTA" format)
            {{Gene<br/>Expression}}
                (Eisen'98<br/>Yeast)
                (GTEx<br/>Human)
        2- Pre-training<br/>Embeddings
            {{a. Ist order<br/>word co-occurrence<br/>matrix}}
            {{b. GO term<br/>defintion extend<br/>with neighbours}}
            {{c. Normalised<br/>2nd order co-occurrence<br/>matrix}}
            {{d. Pointwise mutual info}}
            {{e. Latent semantic analysis}}
            {{f. Singular value<br/>rank reduction}}
        3- Training<br/>Model
            {{Layer 1<br/>gene pair init.<br/>embedding}}
                (each gene represented<br/>by multiple terms)
            {{Layer 2<br/>Maxpool all feat.<br/>dim. to 1 elem.}}
            {{Layer 3<br/>FCNN in SCN or channel<br/>merge layer MCN}}
            {{Layer 4<br/>gene merge in SCN or<br/>FCNN in MCN}}
            {{Layer 5<br/>Highway in SCN or<br/>gene merge in MCN}}
            {{Layer 6<br/>FCNN in SCN or<br/>Highway in MCN}}
            {{Layer 7<br/>output in SCN or<br/>FCNN in MCN}}
            {{Layer 8 in MCN<br/>output}}
```
In the above diagram, under **Training Model**, SCN means _Single Channel Network_ and MCN means _Multi-Channel Network_.

### Experimental Data
TODO

### Pre-training Embeddings
```mermaid
---
title: Pre-training Embeddings
---

%%{init: {
    'theme':'forest',
    'mermaidMaxSourceCharacters': 5000
}}%%

flowchart
    direction TB
    pt1[(MEDLINE<br/>bi-gram list)]
    pt1_1{{bi-gram list}}
    pt2[(GO term<br/>definitions<br/>)]
    pt2_1{{term definition text}}
    pt2_2[Extend term defs. via defs.<br/>of ontological neighbours]
    pt3[shortlist bi-grams<br/>in term def. text]
    pt3_1[split bigrams<br/>to individual words]
    pt3_2[create co-occurrence<br/>matrix]
    pt4[Normalized GO term, SOC, vector<br/>centroid of constituent word vectors]
    pt5[PMI on SOC matrix<br/>using all GO terms and all words]
    pt6[LSA on PMI-on-SOC matrix<br/>i.e., SVD on PMI matrix]
    pt7[Rank reduction on resultant<br/>principal components matrix]
    pt8([Initial input vectors])


    pt1 ---> pt1_1
    pt2 --> pt2_1
    pt1_1 --> pt3
    pt2_1 --> pt2_2
    pt2_2 --> pt3
    pt3 --> pt3_1
    pt3_1 --> pt3_2
    pt3_2 --> pt4
    pt4 --> pt5
    pt5 --> pt6
    pt6 --> pt7
    pt7 --> pt8
```

### Training Model
```mermaid
---
title: Training Model
---

%%{init: {
    'theme':'forest',
    'mermaidMaxSourceCharacters': 5000
}}%%

flowchart
    direction TB
    %% The nodes

    t1{{Initialize all GO<br/>term embeddings<br/>look-up table}}
    subgraph t2 ["Data Source"]
        direction TB
        t2_1[(Protein<br/>Protein<br/>Interaction)]
        t2_2[(Gene<br/>Expressions)]
        t2_3[(Protein<br/>Sequence<br/>Homology)]
    end
    t3[select a pair of genes product]
    t4[select each gene of the pair in turn]
    t4_1[find separate sets or channels of GO terms<br/>in BP, CC and MF for the gene]
    t4_2[find embeddings in look-up table]
    t5[MaxPool over each gene, in each channel]
    t6[Merge layer concatenates all channels]
    t7[FCNN layer generates an all<br/>channel learned embedding]
    t8[Merge layer concatenates gene-product pair]
    t9[FCNN highway layer generates gene-<br/>product pair embedding, with gating]
    t10[output layer for particular taks]


    %% The connections
    t2 --> t3
    t3 --> t4
    t4 --> t4_1
    t1 -.-> t4_1
    t4_1 --> t4_2
    t4_2 --> t5
    t5 --> t6
    t6 --> t7
    t7 --> t8
    t8 --> t9
    t9 --> t10
```

## Positive Points
[_back to contents_](#table-of-contents)

TODO

## Negative Points
[_back to contents_](#table-of-contents)

TODO

## Questions
[_back to contents_](#table-of-contents)

TODO

## References
[_back to contents_](#table-of-contents)

[A. Pesaranghader, S. Matwin, M. Sokolova, J.-C. Grenier, R. G. Beiko, and J. Hussin, "deepSimDEF: deep neural embed-
dings of gene products and gene ontology terms for functional analysis of genes," _Bioinformatics_, vol. 38, pp. 3051–3061,
May 2022.](https://doi.org/10.1093/bioinformatics/btac304)
