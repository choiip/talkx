FROM adoptopenjdk/openjdk8:alpine-slim
ARG TALKX_VERSION=0.1.3
ENV TALKX_VERSION=${TALKX_VERSION}
ADD https://github.com/big-mouth-cn/talkx/releases/download/v$TALKX_VERSION/talkx-$TALKX_VERSION.zip .
RUN addgroup -S talkx \
 && adduser -H -S talkx -G talkx \
 && mkdir -p /talkx && chown -R talkx:talkx /talkx \
 && unzip talkx-$TALKX_VERSION.zip -d /talkx \
 && rm talkx-$TALKX_VERSION.zip 
EXPOSE 8086 8884
WORKDIR /talkx
USER talkx
CMD java -jar lib/talkx-${TALKX_VERSION}.jar