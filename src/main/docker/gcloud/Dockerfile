FROM alpine:3.8

RUN apk add --no-cache bash curl python
RUN addgroup -S jdoe && adduser -S -G jdoe jdoe

USER jdoe
WORKDIR /home/jdoe

RUN curl https://sdk.cloud.google.com -o install.gcloud.cli.sh
RUN bash install.gcloud.cli.sh --disable-prompts
RUN rm install.gcloud.cli.sh
ENV PATH=/home/jdoe/google-cloud-sdk/bin:$PATH
RUN mkdir -p /home/jdoe/.config
VOLUME /home/jdoe/.config
ENTRYPOINT ["/home/jdoe/google-cloud-sdk/bin/gcloud"]