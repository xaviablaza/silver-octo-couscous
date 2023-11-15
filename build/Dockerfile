FROM ubuntu
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

RUN apt update \
	&& apt install -y \
	curl \
	git \
	golang \
	sudo \
	vim \
	wget \
	build-essential \
	openssl \
	zlib1g-dev \
	libreadline-dev \
	libsqlite3-dev \
	libmysqlclient-dev \
	libpq-dev \
	unixodbc-dev \
	tmux \
	redis-server \
	&& rm -rf /var/lib/apt/lists/*

ARG USER=coder
RUN useradd --groups sudo --no-create-home ${USER} \
	&& echo "${USER} ALL=(ALL) NOPASSWD:ALL" >/etc/sudoers.d/${USER} \
	&& chmod 0440 /etc/sudoers.d/${USER}
USER ${USER}
WORKDIR /home/${USER}
SHELL ["/bin/bash", "-c"]
