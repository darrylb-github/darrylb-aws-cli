FROM docker:latest

RUN apk --no-cache update && \
    apk --no-cache add redis && \
    apk --no-cache add python py-pip py-setuptools ca-certificates curl groff less && \
    pip install --upgrade pip && \
    pip --no-cache-dir install awscli && \
    rm -rf /var/cache/apk/*