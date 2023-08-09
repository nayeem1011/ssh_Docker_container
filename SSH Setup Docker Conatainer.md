# ssh_Docker_container
# Create a Dockerfile:
Create a file named Dockerfile (with no file extension) and add the following content:

FROM ubuntu:latest

  RUN apt-get update && \
   apt-get install -y openssh-server && \
   mkdir /var/run/sshd
  
  RUN echo 'root:password' | chpasswd

# Build the Docker Image:
In your terminal, navigate to the directory containing the Dockerfile and run
the following command to build the Docker image:

### docker build -t ssh-container .
# Run the Docker Container:
After building the image, you can run a container based on that image.
You'll need to map a port for SSH access. By default, SSH uses port 22,
but you can map it to a different port on your host system if needed.

Run the following command to start the container:

### docker run -d -p 2222:22 --name ssh-server ssh-container

# Access the SSH Server:

### ssh root@localhost -p 2222



