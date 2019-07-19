FROM openshift/jenkins-slave-base-centos7
MAINTAINER Manny Evangelista <man@redhat.com>

LABEL com.redhat.component="jenkins-slave-image-mgmt" \
      name="skopeojenkinsslave" \
      architecture="x86_64" \
      io.k8s.display-name="Jenkins Slave Image Management" \
      io.k8s.description="Image management tools on top of the jenkins slave base image" \
      io.openshift.tags="openshift,jenkins,slave,copy"
USER root

RUN set -x && \
    yum install skopeo -y

RUN curl -sLo /tmp/oc.tar.gz https://mirror.openshift.com/pub/openshift-v3/clients/3.11.104/linux/oc.tar.gz && \
tar -xzvf /tmp/oc.tar.gz -C /tmp/ && \
mv /tmp/oc /usr/local/bin/ && \
rm -rf /tmp/oc.tar.gz
RUN oc version

RUN yum install sshpass -y

USER 1001s