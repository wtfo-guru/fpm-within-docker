FROM debian:buster
LABEL org.opencontainers.image.authors="Quien Sabe <qs5779@mail.com>"
COPY 80-acquire-retries /etc/apt/apt.conf.d/
RUN apt-get update && apt-get -y install apt-transport-https curl gnupg2 rubygems-integration \
  ruby-dev ruby build-essential rsync && apt-get -y dist-upgrade

RUN gem install fpm -v 1.14.1
RUN curl -sSL https://apt.wtforg.net/APT-WTFORG-GPG.asc | apt-key add -
RUN echo "deb https://apt.wtforg.net buster main" > /etc/apt/sources.list.d/apt-wtforg.list
RUN apt-get -y update  ; apt-get -y install apt-current
RUN /bin/echo -e "MAXDELTA=3600\nCLEANUP_DOWNLOADED_PACKAGES=\"true\"\nCLEANUP_DOWNLOADED_LISTS=\"true\"\n" > /etc/apt-current.conf

RUN apt-get clean && find /var/lib/apt/lists/ /var/lib/apt/lists/partial/ -type f -delete
