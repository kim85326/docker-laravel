FROM docker.io/centos:centos7

# 安裝 EPEL 擴充資源庫
RUN yum install -y epel-release

# 安裝網路工具
RUN yum install -y net-tools bind-utils

# 安裝 PHP
ARG PHP_VERSION="7.3"
RUN curl -O https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN curl -O http://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN rpm -Uvh epel-release-latest-7.noarch.rpm
RUN rpm -Uvh remi-release-7.rpm
RUN yum-config-manager --enable remi-php$(echo ${PHP_VERSION} | cut -c 1,3)
RUN yum install -y php-json php-xml php-mbstring php-mysqlnd php-gd php-mcrypt php-cli php-pdo

# 安裝 Composer
RUN yum install -y composer

# 安裝 GIT
RUN yum install -y git

# 安裝 nvm 與 NodeJS
ARG NODE_VERSION="10.15.3"
ARG NVM_DIR="/usr/local/nvm"
RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
RUN /bin/bash -c "source $NVM_DIR/nvm.sh && nvm install $NODE_VERSION && nvm use --delete-prefix $NODE_VERSION"
ENV PATH      $NVM_DIR/versions/node/$NODE_VERSION/bin:$PATH

# 清理安裝檔
RUN rm -rf /root/*
RUN yum clean all

WORKDIR /var/www

ENTRYPOINT ["/bin/bash"]