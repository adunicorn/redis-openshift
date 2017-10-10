FROM rhel7
#FROM centos7

RUN yum -y install epel-release; \
  yum repolist; \
  yum install redis hostname -y; \
  yum clean all

COPY redis-master.conf /redis-master/redis.conf
COPY redis-slave.conf /redis-slave/redis.conf
RUN mkdir -p /redis-sentinel ; chmod -R 777 /redis-sentinel /redis-slave
COPY run.sh /run.sh

CMD [ "/run.sh" ]

ENTRYPOINT [ "bash", "-c" ]
