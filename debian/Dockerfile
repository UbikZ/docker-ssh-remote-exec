FROM debian:jessie
MAINTAINER Gabriel Malet <gabriemalet@gmail.com>

RUN apt-get update --yes \
	&& apt-get install --no-install-recommends --yes --quiet \
		openssh-client \
		rsync \
	&& apt-get clean \
	&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN mkdir -p /root/.ssh
COPY resources/ssh_config /root/.ssh/config

COPY resources/entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]