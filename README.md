# NAT16_metabolomics_analysis
NAT16 F63S variant and histidine metabolism in CKD (simulated data)

It simulates what we'd expect to see if a broken version of the NAT16 gene disrupts histidine metabolism, and whether that gets worse in chronic kidney disease. None of the data is real. The point is to build and test the analysis and figures now, so the pipeline is ready when actual metabolomics and RNA-seq data come in.

The script makes 120 fake samples in four groups: healthy or CKD, each with the normal gene or the variant. For each sample it generates expression values for six genes and levels for a set of metabolites including N-acetylhistidine, histidine, carnosine, histamine, urocanate, oxidative stress and inflammation markers, and eGFR. Most metabolites are calculated from the gene expression values plus noise, so the correlations mean something. Group averages are set to reflect what we think should happen.

It then produces boxplots by group, a correlation heatmap, a volcano plot, a pathway diagram, scatter plots of NAT16 against each metabolite, a dot plot of how correlations shift in disease, and summary stats.

To run it you need R 4.0 or newer. The first chunk installs any missing packages. Open it in RStudio and run all chunks, or use rmarkdown::render("metabolomics.Rmd"). The seed is fixed, so you get the same output every time. It writes three CSVs and five PNG figures into your working directory.
