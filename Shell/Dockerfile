FROM oraclelinux:latest

RUN yum install -y wget
RUN wget http://repo.mysql.com/yum/mysql-tools-preview/el/7/x86_64/mysql-shell-1.0.3-1.el7.x86_64.rpm
RUN yum install -y mysql-shell-1.0.3-1.el7.x86_64.rpm

COPY docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]

CMD ["mysqlsh"]

