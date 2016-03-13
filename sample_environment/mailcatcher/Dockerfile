FROM helder/ruby:2.2
MAINTAINER Helder Correia <me@heldercorreia.com>

RUN gem install mailcatcher -v 0.5.12 --no-rdoc --no-ri

# smtp (1025) and ip (1080) ports
EXPOSE 1025 1080

CMD ["mailcatcher", "--smtp-ip=0.0.0.0", "--smtp-port=1025", "--http-ip=0.0.0.0", "--http-port=1080", "-f"]