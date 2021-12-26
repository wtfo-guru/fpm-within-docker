FROM fwd-ubuntu-impish:latest
LABEL org.opencontainers.image.authors="Quien Sabe <qs5779@mail.com>"
# whatever is required for building should be installed in this image; just like BuildDeps for DEB projects.
RUN apt-get update ; apt-get -y install rsync libreadline-dev

RUN apt-get clean && find /var/lib/apt/lists/ /var/lib/apt/lists/partial/ -type f -delete
