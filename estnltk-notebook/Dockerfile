FROM jupyter/minimal-notebook 
USER root

#install dependencies 
RUN echo 'deb http://ftp.de.debian.org/debian jessie-backports main' >> /etc/apt/sources.list
RUN apt-get update

# java 8 
# visilcg3 from libvoikko1
RUN apt-get install -y --no-install-recommends openjdk-8-jdk libvoikko1 && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER jovyan
RUN conda install -y  -c conda-forge -c estnltk estnltk
RUN conda clean --all

##setup tutorials directory 
RUN mkdir ~/estnltk
RUN cd ~/estnltk
RUN git init
RUN git remote add origin https://github.com/estnltk/estnltk.git
RUN git config core.sparseCheckout true
RUN echo "/docs/tutorials" >> .git/info/sparse-checkout
RUN git pull --depth 1 origin master
RUN cp -r ./docs/tutorials ~
RUN cd ~
RUN rm -rf ~/estnltk


RUN python -c 'import estnltk'
