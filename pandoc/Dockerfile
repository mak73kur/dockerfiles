FROM ubuntu:14.04

ENV REFRESHED_AT 2016-01-30
RUN apt-get -qq update

# install haskell
RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get install -y pandoc texlive-latex-base texlive-xetex latex-xcolor \
    texlive-math-extra texlive-latex-extra texlive-fonts-extra \
    lmodern curl wget git fontconfig make

RUN mkdir -p /source
WORKDIR /source

ENTRYPOINT ["/.cabal/bin/pandoc"]
CMD ["--help"]