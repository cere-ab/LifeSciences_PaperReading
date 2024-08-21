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



# Paper Review: ModalityChoices

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
    root )ModalityChoices(
        1- Data<br/>Sources
            {{STRING<br/>v11.5}}
                (Human protein<br/>coding genes)
            {{Ensemble<br/>gene ID}}
                [BioMart<br/>]
                    {{External<br/>gene/disease<br/>identifiers}}
                [HUGO gene<br/>nomenclature<br/>comm.]
                    {{gene names<br/>external src}}
            {{GTEx Proj.<br/>gene expr.}}
                [Protein-coding genes<br/>subset of TPM mat.]
            {{Polygenic<br/>Priority Score}}
            {{Genom-wide<br/>ess. screen<br/>DepMap}}
            {{TCGA<br/>omics dataset}}
            {{UK Biobank}}
                [Genebass<br/>trait-gene association]
                [GWAS blood biomarker]
            {{PubMed}}
                (gene2ensembl)
                (gene2pubmed)

        2- Embeddings
            {{OMICS<br/>embeddings}}
                ((GTEx))
                ((DepMap))
                ((ProtTrans))
            {{STRING<br/>embeddings}}
                ((STRING<br/>v11.5))
                    (full gene-gene<br/>Ix graph)
                    (gene-gene Ix<br/>graph with studied<br/>edges removed)
            {{PoPS<br/>embeddings}}
                ((gene expression<br/>experiments<br/>excluding any<br/>manual curation))
                ((GE exp.<br/>pathways annot.<br/>PPI db))
        
        3- Downstream<br/>Tasks
            (Human<br/>curated)
                {{Disease Gene<br/>list predictions}}
                    [XGBoost]
                {{HPO annotation<br/>Predictions}}
                    [2-layer<br/>multi-class<br/>classifier]
                {{Cancer gene<br/>prediction}}
                    [XGBoost]
            (Statistical<br/>association)
                {{Predict<br/>gene level association<br/>scores for 22 uncorrelated<br/>blood biomarker GWAS studies}}
                    [?? unclear method]
                {{Predict<br/>trait-gene<br/>association}}
                    [logistic regression]
            (Annotation<br/>Inequality)
                {{Predict per gene<br/>publication-count bins}}
                    [?? unclear method]
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

[F. Brechtmann, T. Bechtler, S. Londhe, C. Mertes, and J. Gagneur, "Evaluation of input data modality choices on functional gene embeddings," _NAR Genomics and Bioinformatics_, vol. 5, p. lqad095, 11 2023.](https://academic.oup.com/nargab/article/5/4/lqad095/7337624)
