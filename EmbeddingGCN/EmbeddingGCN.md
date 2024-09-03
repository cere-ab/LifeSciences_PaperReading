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



# Paper Review: EmbeddingGCN

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

>**HMDD** - human miRNA-associated disease database

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
    root )EmbeddingGCN(
        1- Purpose
            {{Link prediction<br/>for}}
                (Pathology)
                (Pharmacology)
                (Physiology)
            {{Using}}
                (Guilt-by<br/>association)
        2- Data<br/>Sources
            {{DisGeNet}}
                (gene-disease<br/>network)
            {{HumanNet}}
                (gene-gene<br/>network)
            {{MeSH vocab.}}
                (disease-disease<br/>network)
                    [HMDD]
        3- Method
            {{i- Build gene<br/>disease graph}}
                (a. make gene-<br/>gene Adjacency)
                (b. make gene-<br/>disease Adjacency)
                (c. make disease-<br/>disease Adj.)
                (d. combine using<br/>Eq. 1 of paper)
            {{ii- initial<br/>node<br/>features<br/>DeepWalk}}
                (a. RandomWalk<br/>sequences at<br/>disease gene)
                (b. word2vec<br/>on sequences)
            {{iii- Kipf GCN +<br/>Spectral Graph Theory}}
                (learn better embeddings)
            {{iv- Decoding}}
                (3-layer FFNN<br/>for classifying<br/>existence of gene-<br/>disease association)
            
        
            
```

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

[Lvxing Zhu, Zhaolin Hong, Haoran Zheng, "Predicting gene-disease associations via graph embedding and graph convolutional networks," in _2019 IEEE International Conference on Bioinformatics and Biomedicine (BIBM)_, pp. 382–389, 2019.](https://ieeexplore.ieee.org/document/8983350)
