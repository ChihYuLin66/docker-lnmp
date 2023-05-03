
# MariaDB 5.5  => MySQL 5.5
# MariaDB 10.0 => MySQL 5.6
# MariaDB 10.1 => MySQL 5.7
# MariaDB 10.2 => MySQL 5.7 / 8.0
# MariaDB 10.3 => MySQL 5.7 / 8.0
# MariaDB 10.4 => MySQL 5.7 / 8.0
# MariaDB 10.5 => MySQL 8.0

FROM mariadb:10.4

#####################################
# Set Timezone
#####################################

ARG TIMEZONE
ENV TIMEZONE=${TIMEZONE}
RUN ln -snf /usr/share/zoneinfo/$TIMEZONE /etc/localtime && \ 
    echo $TIMEZONE > /etc/timezone && \ 
    chown -R mysql:root /var/lib/mysql/


CMD ["mysqld"]

EXPOSE 3306