FROM centos:centos7
MAINTAINER Leonel Baer <leonel@lysender.com>

# Install packages
RUN yum -y update &&  yum clean all

RUN rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm

RUN yum -y install git \
    bind-utils \
    pwgen \
    psmisc \
    net-tools \
    hostname \
    curl \
    curl-devel \
    sqlite \
    cronie \
    libevent \
    gearmand \
    libgearman \
    libgearman-devel \
    php56w-common \
    php56w-cli \
    php56w-mcrypt \
    php56w-mysql \
    php56w-soap \
    php56w-xml \
    php56w-mbstring \
    php56w-pdo \
    php56w-gd \
    python \
    python-devel \
    python-pip \
    wget \
    mercurial && yum clean all

# Install dev cron
RUN pip install -e hg+https://bitbucket.org/dbenamy/devcron#egg=devcron

COPY cron /cron

CMD ["devcron.py", "/cron/crontab"]
