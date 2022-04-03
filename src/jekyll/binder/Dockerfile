FROM ubuntu:latest

# Set up user
ARG NB_USER
ARG NB_UID
ENV USER ${NB_USER}
ENV HOME /home/${NB_USER}

RUN groupadd \
        --gid ${NB_UID} \
        ${NB_USER} && \
    useradd \
        --comment "Default user" \
        --create-home \
        --gid ${NB_UID} \
        --no-log-init \
        --shell /bin/bash \
        --uid ${NB_UID} \
        ${NB_USER}

RUN apt-get update \
    && apt-get install --yes --no-install-recommends \
        tini
 
#################### START - Non-boilerplate section ####################

RUN apt-get install --yes --no-install-recommends \
        ruby-full \
        build-essential \
        zlib1g-dev

RUN gem install \
        jekyll

RUN gem install minima

EXPOSE 4000

#################### END - Non-boilerplate section ####################

RUN apt-get purge \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["tini", "--"]
