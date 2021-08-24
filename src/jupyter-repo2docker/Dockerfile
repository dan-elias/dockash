FROM continuumio/miniconda3:latest
COPY --from=docker:latest /usr/local/bin/docker /usr/local/bin/

RUN apt-get --allow-releaseinfo-change update \
    && apt-get  install --yes --no-install-recommends \
            git \
    && apt-get purge  &&  apt-get clean  &&  rm -rf /var/lib/apt/lists/*

RUN conda update conda \
    && conda install -y -c conda-forge \
           jupyter-repo2docker \
    && useradd -ms /bin/bash normaluser \
       && echo "normaluser:password" | chpasswd

RUN groupadd docker \
      && usermod -aG docker normaluser

USER normaluser
WORKDIR /home/normaluser

ENTRYPOINT []
CMD []
