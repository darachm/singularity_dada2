#Bootstrap: docker
#From: ubuntu:18.04
Bootstrap: localimage
From: ../ubuntu-1804-updated_container/ubuntu.simg

%labels
MAINTAINER darachm

%help

    This container is for providing `dada2` for some bioinformatic pipelines.
    
%post

    apt-get -y update
    #apt-get -y install r-base wget gcc-4.8 g++
    wget https://github.com/benjjneb/dada2/archive/v1.10.zip -O dada2_v1.10.zip
    unzip dada2_v1.10.zip
    #Rscript -e 'install.packages("BiocManager"); BiocManager::install()'
    #Rscript -e 'BiocManager::install(c("Rcpp","Biostrings", "ggplot2", "data.table", "reshape2", "ShortRead", "RcppParallel", "IRanges", "XVector", "BiocGenerics"))'
    Rscript -e 'install.packages("dada2-1.10",repos=NULL,type="source",dependencies=c("Depends","Suggests","Imports"))'

%test

    Rscript -e 'library(dada2);'
