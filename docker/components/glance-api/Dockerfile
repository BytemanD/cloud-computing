FROM centos:7

RUN cd /etc/yum.repos.d && mkdir backup && mv *.repo backup
COPY *.repo /etc/yum.repos.d/
RUN rm -r /etc/localtime && ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN yum -y install openstack-glance python-glance python-glanceclient \
    && yum clean all
RUN systemctl enable openstack-glance-api.service openstack-glance-registry.service

EXPOSE 9292
ENTRYPOINT [ "glance-api" ]
