FROM centos:7

MAINTAINER NGINX Docker Maintainers "your-email@domain.com"


ENV my_env SANDBOX
ENV my_version 1.0.0

#USER docker

RUN yum install -y wget

#add aliyun yum repo
RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup

RUN wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
 
RUN yum clean all
RUN yum makecache


RUN yum install -y nginx


ADD index.htm /usr/share/nginx/html
#COPY static-html-dir /usr/share/nginx/html


EXPOSE 80


CMD ["nginx", "-g", "daemon off;"]
