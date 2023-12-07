FROM jenkins/jenkins:latest

USER root

# Update the packages
RUN apt-get update && apt-get install --yes apt-transport-https ca-certificates curl software-properties-common

# Add Docker repository
RUN curl -sL "https://download.docker.com/linux/debian/gpg" | apt-key add -
RUN add-apt-repository "deb https://download.docker.com/linux/debian $(lsb_release -cs) stable"

# Install Docker CE CLI
RUN apt-get update && apt-get install --yes docker-ce-cli

# Switch to Jenkins user
USER jenkins

# Install latest plugins
RUN jenkins-plugin-cli --plugins "blueocean:latest docker-workflow:latest"