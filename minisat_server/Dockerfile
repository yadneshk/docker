# Choose Alpine as base image
FROM alpine:latest

# Install required packages
RUN apk add --no-cache sqlite \
            python3 \
            py-pip \
            curl \            
            openssh  \
            sshpass \        
            libvirt-client \
            virt-install

# Install Docker Machine
RUN curl -L https://github.com/docker/machine/releases/download/v0.14.0/docker-machine-`uname -s`-`uname -m` >/tmp/docker-machine && \
    install /tmp/docker-machine /usr/local/bin/docker-machine

# Create a directory /workspace
RUN mkdir /workspace

# Make /workspace as working directory
WORKDIR /workspace

# Copy all Minisat files and directories in working directory
ADD Minisat/ /workspace

# Create public key
RUN ssh-keygen -t rsa -f /root/.ssh/id_rsa -q -P ""

# Install all python modules required by Minisat
RUN pip3 install -r requirements.txt

# Generate SQL queries
RUN python3 manage.py makemigrations

# Execute SQL queries upon database
RUN python3 manage.py migrate

# Run Minisat server
ENTRYPOINT  [ "python3","manage.py","runserver" ]