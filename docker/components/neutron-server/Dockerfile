FROM centos:7

COPY *.repo /etc/yum.repos.d/
RUN rm -r /etc/localtime && ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN yum install -y openstack-neutron openstack-neutron-ml2 openstack-neutron-openvswitch \
    && yum clean all
RUN systemctl enable neutron-server

ENTRYPOINT [ "/usr/sbin/init" ]
