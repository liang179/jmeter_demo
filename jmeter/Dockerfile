FROM alpine

RUN apk --no-cache add xvfb x11vnc novnc curl supervisor openjdk8-jre \
    && curl -L https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-5.4.1.tgz > /tmp/jmeter.tgz \
    && mkdir -p /jmeter \
    && tar -xvf /tmp/jmeter.tgz -C /jmeter \
    && rm /tmp/jmeter.tgz

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
EXPOSE 8080

ENV DISPLAY=:0

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]