FROM centos:7

COPY *.repo /etc/yum.repos.d/
RUN rm -r /etc/localtime && ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN yum install -y openstack-neutron-openvswitch openvswitch \
    && yum clean all
RUN systemctl enable neutron-openvswitch-agent

ENTRYPOINT [ "/usr/sbin/init" ]
