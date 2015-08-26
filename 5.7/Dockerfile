FROM oraclelinux:latest

ENV MYSQL_VERSION mysql-5.7.7-labs-json-linux-el6-x86_64
ENV PATH $PATH:/mysql/bin

RUN yum install -y libaio wget tar \
&& wget http://downloads.mysql.com/snapshots/pb/mysql-5.7.7-labs-json/$MYSQL_VERSION.tar.gz \
&& adduser mysql \
&& tar xvf $MYSQL_VERSION.tar.gz -C / \
&& rm $MYSQL_VERSION.tar.gz \
&& mv /$MYSQL_VERSION /mysql \
&& rm -f /mysql/bin/mysqld-debug \
&& rm -f /mysql/lib/* || true \
&& strip /mysql/bin/* || true

VOLUME /var/lib/mysql
VOLUME /var/lib/mysql-files

COPY docker-entrypoint.sh /entrypoint.sh
COPY my.cnf /etc/mysql/my.cnf
ENTRYPOINT ["/entrypoint.sh"]

EXPOSE 3306
CMD ["mysqld"]

