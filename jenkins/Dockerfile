FROM liatrio/jenkins-alpine
COPY jobs /usr/share/jenkins/ref/jobs/
COPY jenkins_home/config.xml /var/jenkins_home/config.xml

RUN apk add --no-cache python3 && \
    if [ ! -e /usr/bin/python ]; then ln -sf python3 /usr/bin/python ; fi && \
    \
    echo "**** install pip ****" && \
    python3 -m ensurepip && \
    rm -r /usr/lib/python*/ensurepip && \
    pip3 install --no-cache --upgrade pip setuptools wheel && \
    if [ ! -e /usr/bin/pip ]; then ln -s pip3 /usr/bin/pip ; fi

RUN apk add aws-cli --update-cache --repository http://nl.alpinelinux.org/alpine/edge/testing
RUN apk update -y && \
    apk add -y gcc musl-dev linux-headers openssl-dev libffi-dev python3-dev make

RUN ln -sf python3 /usr/bin/python

RUN pip install docker-compose
