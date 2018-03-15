FROM alpine:latest
RUN apk add --no-cache py-pip && \
    apk add --no-cache git && \ 
    pip install grip 
RUN mkdir /data
WORKDIR /data
RUN git clone https://github.com/miniSat/Minisat-documentation.git
ENTRYPOINT ["grip","Minisat-documentation/README.md","0.0.0.0:8080"]
