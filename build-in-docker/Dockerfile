FROM debian:stretch-slim

RUN \
	echo "deb http://ftp.debian.org/debian stretch-backports main" >>/etc/apt/sources.list && \
        apt-get -yq update && \
        apt-get -yq install \
                -t stretch-backports meson && \
        apt-get -yq install \
                gnome-common \
                gettext \
                libglib2.0-dev \
                locales \
        && \
        # Set locale
        sed --in-place '/en_US.UTF-8/s/^# //' /etc/locale.gen && \
        locale-gen en_US.UTF-8 && \
	apt-get clean && \
	rm -rf /tmp/* /var/tmp/* /var/lib/apt/lists/*

ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8

CMD /app/build
