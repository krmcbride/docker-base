FROM alpine:3.6

RUN apk add --no-cache \
      tzdata \
    && cp /usr/share/zoneinfo/America/Los_Angeles /etc/localtime \
    && echo "America/Los_Angeles" > /etc/timezone \
    && date \
    && apk del tzdata

RUN apk add --no-cache \
    bash \
    ca-certificates \
    curl

# bash
COPY bash-it/ /usr/local/bash-it/
COPY .bashrc /root/
ENV BASH_IT /usr/local/bash-it
ENV BASH_IT_THEME powerline-multiline
ENV SCM_CHECK true
ENV TERM xterm-256color

RUN mkdir -p /usr/src/app
WORKDIR /root
CMD ["bash"]
