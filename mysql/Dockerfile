FROM mysql:5.7-debian
LABEL maintainer="aisna@protonmail.com"

  # set timezome
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update && apt-get install -y git tig lsof htop vim subversion
RUN apt-key adv --keyserver pgp.mit.edu --recv-keys 467B942D3A79BD29
