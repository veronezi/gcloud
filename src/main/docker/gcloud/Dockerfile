FROM alpine:3.8

RUN apk add --no-cache bash curl python
RUN mkdir -p /opt
WORKDIR /opt

RUN addgroup -S jdoe && adduser -S -G jdoe jdoe
RUN chown jdoe:jdoe -R /opt

USER jdoe

RUN curl https://sdk.cloud.google.com -o install.gcloud.cli.sh
RUN bash install.gcloud.cli.sh --disable-prompts
RUN rm install.gcloud.cli.sh
ENV PATH=/home/jdoe/google-cloud-sdk/bin:$PATH
VOLUME /home/jdoe/.config
ENTRYPOINT ["/home/jdoe/google-cloud-sdk/bin/gcloud"]