FROM nginx
LABEL maintainer="aisna@protonmail.com"
#COPY nginx.conf /etc/nginx/nginx.conf
# set timezome
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
#
# Install package and PHP Core extensions
RUN apt-get update && apt-get install -y \
        git tig lsof htop vim subversion
