FROM jenkins/jenkins:lts

# No setup wizard
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

# Access via admin/admin by default
ENV JENKINS_USER admin
ENV JENKINS_PASS admin

# Jenkins runs groovy files in init.groovy.d
COPY ./init.groovy.d/*.groovy /usr/share/jenkins/ref/init.groovy.d/

COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
