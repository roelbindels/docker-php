FROM edyan/php:7.0
MAINTAINER Roel Bindels <roel.bindels@inetprocess.com>

# Upgrade the system and Install Cron
RUN DEBIAN_FRONTEND=noninteractive apt-get update && \

    DEBIAN_FRONTEND=noninteractive apt-get upgrade -y && \

    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends cron &&\
    
    DEBIAN_FRONTEND=noninteractive apt-get autoremove -y && \
    DEBIAN_FRONTEND=noninteractive apt-get autoclean && \
    DEBIAN_FRONTEND=noninteractive apt-get clean && \
    rm -Rf /var/lib/apt/lists/* /usr/share/man/* /usr/share/doc/*


ADD crontab /etc/cron.d/sugarcrm

# Give execution rights on the cron job
RUN chmod 0644 /etc/cron.d/sugarcrm

# Create the log file to be able to run tail
RUN touch /var/log/cron.log

CMD ["cron", "-f"]