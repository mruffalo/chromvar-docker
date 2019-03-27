FROM openanalytics/r-base

LABEL maintainer="mruffalo@cs.cmu.edu"

RUN apt-get update && apt-get install -y \
    sudo \
    libcurl4-openssl-dev \
    libgsl-dev \
    libssl-dev \
    libxml2-dev \
    && rm -rf /var/lib/apt/lists/*

# R packages needed for chromVAR
RUN R -e "options(internet.info=0, warn=2); install.packages('BiocManager'); BiocManager::install(c('chromVAR', 'motifmatchr', 'BSgenome.Hsapiens.UCSC.hg19', 'JASPAR2016'))"
