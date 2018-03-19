FROM alpine:latest
RUN apk add --no-cache py-pip && \
    apk add --no-cache python3 && \
    apk add --no-cache sqlite && \
    apk add --no-cache git && \
    apk add --no-cache openssh && \
    apk add --no-cache sshpass
RUN mkdir /workspace
WORKDIR /workspace
ADD Minisat/ /workspace
RUN ssh-keygen -t rsa -f /root/.ssh/id_rsa -q -P ""
RUN git clone https://github.com/miniSat/Minisat.git
RUN pip3 install -r Minisat/requirements.txt
RUN python3 Minisat/manage.py makemigrations
RUN python3 Minisat/manage.py migrate
ENTRYPOINT  [ "python3","Minisat/manage.py","runserver" ]
