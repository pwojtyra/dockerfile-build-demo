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
ENTRYPOINT while true; do curl http://$CLOUD_TASKS_IP/$(awk -v min=5000 -v max=10000 'BEGIN{srand(); print int(min+rand()*(max-min+1))}'); done;