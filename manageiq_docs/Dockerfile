FROM alpine:latest
RUN apk add --no-cache py-pip && \
    apk add --no-cache git && \ 
    pip install grip  
RUN mkdir /data
WORKDIR /data
RUN git clone https://github.com/enhance-manageiq/docs.git
ENTRYPOINT ["grip","docs/README.md","0.0.0.0:8080"]
