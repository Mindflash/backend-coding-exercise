FROM alpine

# install dependencies
RUN apk add --update ca-certificates curl tar
RUN curl -fsSL -o /tmp/brainspark_linux_amd64.tar.gz https://github.com/Mindflash/backend-coding-exercise/releases/download/v1.0.0-beta.0/brainspark_linux_amd64.tar.gz
RUN cd /tmp && tar -xvzf /tmp/brainspark_linux_amd64.tar.gz && \
    mv /tmp/brainspark /usr/local/bin/brainspark && \
    chmod +x /usr/local/bin/brainspark

# configure filesystem
RUN mkdir -p /etc/brainspark

ENTRYPOINT ["brainspark"]