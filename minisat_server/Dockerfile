# Choose Fedora as base image
FROM fedora

# Install required packages
RUN dnf install sqlite  \            
                openssh  \
                sshpass -y

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