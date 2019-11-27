FROM "rocker/r-ver:latest"
MAINTAINER ben@artins.org

# Install curl
RUN apt-get update -y -qq && apt-get install -y -qq --no-install-recommends curl libcurl4-openssl-dev libz-dev

# Install rmarkdown
RUN Rscript -e 'install.packages(c("rmarkdown", "lubridate", "RCurl", "rmdformats"))'

### Install pandoc 2.x
RUN cd /tmp && \
  curl -L -O "https://github.com/jgm/pandoc/releases/download/2.7.3/pandoc-2.7.3-1-amd64.deb" && \
  dpkg -i /tmp/pandoc-2.7.3-1-amd64.deb && \
  rm /tmp/*.deb
