FROM alpine:3.18.4

RUN apk -U --no-progress upgrade && \
  apk -U --no-progress add taskd taskd-pki

# Import build and startup script
COPY ./run.sh /app/taskd/

# Set the data location
ARG TASKDDATA
ENV TASKDDATA ${TASKDDATA:-/var/taskd}

# Configure container
VOLUME ["${TASKDDATA}"]
EXPOSE 53589
ENTRYPOINT ["/app/taskd/run.sh"]