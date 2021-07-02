FROM debian:stretch-20210208-slim

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update -y &&\
    apt-get dist-upgrade -y &&\
    apt-get autoremove &&\
    apt-get clean &&\
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


# +--------------------+
# APPLICATION LEVEL VULNERABILITIES (httplib2)
# +--------------------+

COPY lang_dependencies/Pipfile.lock /app/Pipfile.lock
