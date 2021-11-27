FROM CircleCI-Public/example-images

MAINTAINER bharu459@gmail.com

ENV ENV_NAME local


ENV BOOTAPP_USR="root" BOOTAPP_GROUP="root" BOOTAPP_PATH="/app.jar"

EXPOSE $SERVER_PORT

COPY wrapper.sh /wrapper.sh

RUN chmod 555 /wrapper.sh

USER root
COPY maven/app.jar $BOOTAPP_PATH
RUN chmod 555 $BOOTAPP_PATH && \
            touch $BOOTAPP_PATH
           


USER $BOOTAPP_USR

# RUN cat ./newrelic/newrelic.yml | sed -e 's/app_name:.*/app_name: docker_boot/' > ./newrelic/newrelic.yml
 
ENTRYPOINT ["/wrapper.sh"]
