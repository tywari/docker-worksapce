FROM	ubuntu:latest
LABEL	maintainer="Anuj Tiwari

RUN		apt-get update
RUN		apt-get install -y software-properties-common
RUN		DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata  && \
		ln -fs /usr/share/zoneinfo/Asia/Kolkata /etc/localtime && \
		dpkg-reconfigure --frontend noninteractive tzdata
RUN		add-apt-repository -y ppa:ondrej/php
RUN		apt-get install -y openssh-server nginx mysql-server vim git memcached \
		libmemcached-tools php5.6 php5.6-fpm php5.6-mysql php5.6-curl php5.6-gd \
		php5.6-xml php5.6-mcrypt php5.6-memcached curl php5.6-cli php5.6-mbstring \
		unzip
RUN		wget -qO- https://deb.nodesource.com/setup_8.x | bash -
RUN		apt-get install -y nodejs && node -v && npm -v
RUN		cd ~ && curl -sS https://getcomposer.org/installer -o composer-setup.php && \
		php composer-setup.php --install-dir=/usr/local/bin --filename=composer
		
ENTRYPOINT service php5.6-fpm start && service nginx start && bash
