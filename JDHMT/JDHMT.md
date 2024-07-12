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



# Paper Review: JDHMT

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
    root )JDHMT(
        1- Objectives
            {{Data<br/>Format}}
                (Two triplets)
            {{Build<br/>database}}
            {{Joint<br/>decomposition<br/>matrix & tensor}}
        2- Embedding<br/>categories
            {{Proximity<br/>Preserving}}
            {{Message<br/>Passing}}
            {{Relation<br/>Learning}}
                (This<br/>Paper)
        3- Data<br/>Sources
            {{BioGRID}}
            {{BioSNAP}}
            {{CTD}}
            {{DisGeNET}}
            {{Disease-Ontology}}
            {{HPO}}
            {{NCBI}}
            {{EXTRA}}
                (AGAC)
                (Entrez)
                (MESH)
                (SNP)
                (KEGG)
                (GWAS)
        4- Proposed<br/>Solution
            {{Two triplets}}
                (Matrix for<br/>uni-relational)
                (Tensor for<br/>multi-relational)
            {{Convex optimization<br/>for joint decomposition}}
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
    pt1[(TEST)]
    
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
