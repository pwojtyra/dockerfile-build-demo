FROM docker.io/centos
LABEL description="This is a test image to test disks"
RUN yum install -y sysstat && \
    yum install -y sudo && \
    yum install -y iproute net-tools bind-utils iputils curl && \
    yum clean all
RUN useradd -m docker && \
    echo "docker:docker" | chpasswd && \
    usermod -aG wheel docker
RUN mkdir /Data && \
    chmod 777 /Data && \
    chmod +t /Data
USER docker
#CMD ["/usr/bin/ping","onet.pl"]
#ENTRYPOINT while true; do /usr/bin/curl http://bluegreen-scm-web-hooks.openshift.lab.is/ >> /Data/dumpfile; done;
ENTRYPOINT while true; do /usr/bin/curl http://application-api-helloworld-test.apps.dev.peum.local/application >> /dev/null; done;
