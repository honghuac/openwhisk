# Dockerfile for python actions, overrides and extends ActionRunner from actionProxy
FROM dockerskeleton

RUN apk add --no-cache \
        bzip2-dev \
        gcc \
        libc-dev \
        libxslt-dev \
        libxml2-dev \
        libffi-dev \
        openssl-dev \
        python-dev

# Install common modules for python
RUN pip install \
    beautifulsoup4==4.5.1 \
    httplib2==0.9.2 \
    kafka_python==1.3.1 \
    lxml==3.6.4 \
    python-dateutil==2.5.3 \
    requests==2.11.1 \
    scrapy==1.1.2 \
    simplejson==3.8.2 \
    twisted==16.4.0

ENV FLASK_PROXY_PORT 8080

RUN mkdir -p /pythonAction
ADD pythonrunner.py /pythonAction/

CMD ["/bin/bash", "-c", "cd pythonAction && python -u pythonrunner.py"]
