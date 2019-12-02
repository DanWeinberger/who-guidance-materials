FROM "rocker/r-ver:latest"
MAINTAINER ben@artins.org

# Install needed OS packages
RUN apt-get update -y -qq && apt-get install -y -qq --no-install-recommends \
  curl \
  libcurl4-gnutls-dev \
  libgit2-dev \
  libssh2-1-dev \
  libssl-dev \
  libxml2-dev \
  libz-dev

# Install needed R packages
RUN Rscript -e 'install.packages(c(\
  "htmlTable", \
  "devtools", \
  "rmarkdown", \
  "lubridate", \
  "RCurl", \
  "rmdformats" \
))'
RUN Rscript -e 'devtools::install_github(\
  "weinbergerlab/InterventionEvaluatR" \
)'

### Install pandoc 2.x
RUN cd /tmp && \
  curl -L -O "https://github.com/jgm/pandoc/releases/download/2.7.3/pandoc-2.7.3-1-amd64.deb" && \
  dpkg -i /tmp/pandoc-2.7.3-1-amd64.deb && \
  rm /tmp/*.deb
