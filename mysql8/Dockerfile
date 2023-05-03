# ARG MYSQL8_VERSION
FROM mysql:8.0.32

#####################################
# Set Timezone
#####################################

ARG TIMEZONE
ENV TIMEZONE ${TIMEZONE}
RUN ln -snf /usr/share/zoneinfo/$TIMEZONE /etc/localtime && \
    echo $TIMEZONE > /etc/timezone && \ 
    chown -R mysql:root /var/lib/mysql/

CMD ["mysqld"]

EXPOSE 3306
