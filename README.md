# restring
Functional enrichment terms aggregator

```restring``` is designed to aggregate functional enrichment data, preferably from String-compliant table delimited text (```.tdt```) tables. ```restring``` is currently under **active** development, including this doc, and it's still **not ready for use**.

doc: coming soon

examples: coming soon

## Overview
```restring``` aggregates functional enrichment data from the table delimited text (```.tdt```) tables produced by [String](https://string-db.org/). It returns, in table-friendly format, aggregated results from analyses of multiple comparisons.

What KEGG pathway was found in which comparisons? What pvalues? What DE genes annotated in that pathway were shared in those comparisons? How can I simultaneously show results for all my experimental groups, for all terms, all at once? This can all be managed by ```restring```.

---

Modern high-throughput -omic approaches generate huge lists of differentially expressed (DE) genes/proteins, which can in turn be used for functional enrichment studies. Manualy reviewing a large number of such analyses is time consuming, especially for experimental designs with more than a few groups. Let's consider this experimental setup:

![](https://github.com/Stemanz/restring/raw/main/images/Figure%201.jpg)

This represents a fairly common experimental design, but manually inspecting functional enrichment results for such all possible combinations would require substantial effort. Let's take a look at how we can tackle this issue with ```restring```.

Our sample experimental setup has **two treatments**, given at **two time points** to **three different sample types**. Let's assume those samples are cells of different genotypes, and we'd like to mainly investigate genotype comparisons. After quantifying gene expression by RNAseq, we have DE genes for every comparison. As in many experimental pipelines, each list of DE genes is investigated with functional enrichment tools, such as [String](https://string-db.org/). But every comparison generates one or more tables. ```restring``` makes it easy to generate summary reports from all of them, automatically.

![](https://github.com/Stemanz/restring/raw/main/images/Figure%202.jpg)

---
## Procedure

Head over to [String](https://string-db.org/), and analyze your gene/protein list. Please refer to the [String documentation](https://string-db.org/cgi/help) for help. After running the analysis, hit the ![](https://github.com/Stemanz/restring/raw/main/images/analysis.png) button at the bottom of the page. This allows to download the results as tab delimited text files.

![](https://github.com/Stemanz/restring/raw/main/images/export_supported.png)

```restring``` is designed to work with the results types highlighted in green. For each one of your experimental settings, create a folder with a name that will serve as a label for it. Here's how our [sample data](https://github.com/Stemanz/restring/tree/main/sample_data) is arranged:

![](https://github.com/Stemanz/restring/raw/main/images/files.png)

