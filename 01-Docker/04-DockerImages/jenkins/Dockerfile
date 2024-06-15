# Use an official OpenJDK runtime as a parent image
FROM openjdk:11-jdk-slim

# Set the environment variables for Jenkins
ENV JENKINS_HOME /var/jenkins_home
ENV JENKINS_VERSION 2.461
ENV JENKINS_WAR https://updates.jenkins.io/download/war/$JENKINS_VERSION/jenkins.war

# Create the Jenkins home and war directories
RUN mkdir -p $JENKINS_HOME && mkdir -p /usr/share/jenkins

# Set the working directory
WORKDIR $JENKINS_HOME

# Install necessary packages including wget and dependencies
RUN apt-get update && \
    apt-get install -y wget fontconfig libfreetype6 && \
    wget $JENKINS_WAR -O /usr/share/jenkins/jenkins.war && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Expose the Jenkins port
EXPOSE 8080

# Define the entry point
ENTRYPOINT ["java", "-jar", "/usr/share/jenkins/jenkins.war"]
