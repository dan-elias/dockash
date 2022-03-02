# based on: https://gist.github.com/demaniak/c56531c8d673a6f58ee54b5621796548

FROM ubuntu:latest

# RUN apt-get update \
#     && apt-get install --yes --no-install-recommends \
#         tini

#################### START - Non-boilerplate section ####################

ARG SOURCE_URL=https://zoom.us/client/latest/zoom_amd64.deb

SHELL ["/bin/bash", "-c"]

RUN export DEBIAN_FRONTEND=noninteractive && DEBCONF_NONINTERACTIVE_SEEN=true \
    && apt-get update \
    && apt-get install --yes --no-install-recommends \
        pulseaudio-utils \
        pulseaudio \
        wget 

RUN mkdir -p /tmp/junk \
    && pushd /tmp/junk \
    && wget -O installer.deb --no-check-certificate ${SOURCE_URL} \
    && popd

RUN export DEBIAN_FRONTEND=noninteractive && DEBCONF_NONINTERACTIVE_SEEN=true \
    && pushd /tmp/junk \
    && apt-get install --yes ./installer.deb  \
    && popd && rm -r /tmp/junk

RUN gsettings set org.gnome.mutter check-alive-timeout 3600000

#################### END - Non-boilerplate section ####################

RUN apt-get purge \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

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

# ENTRYPOINT ["tini", "--"]
