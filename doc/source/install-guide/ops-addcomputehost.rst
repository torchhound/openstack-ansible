`Home <index.html>`_ OpenStack-Ansible Installation Guide

Adding a compute host
---------------------

Use the following procedure to add a compute host to an operational
cluster.

#. Configure the host as a target host. See `Chapter 3, *Target
   hosts* <targethosts.html>`_ for more information.

#. Edit the ``/etc/openstack_deploy/openstack_user_config.yml`` file and
   add the host to the ``compute_hosts`` stanza.

   If necessary, also modify the ``used_ips`` stanza.

#. Run the following commands to add the host. Replace
   ``NEW_HOST_NAME`` with the name of the new host.

   .. code-block:: shell-session

       # cd /opt/openstack-ansible/playbooks
       # openstack-ansible setup-hosts.yml --limit NEW_HOST_NAME
       # openstack-ansible setup-openstack.yml --skip-tags nova-key-distribute --limit NEW_HOST_NAME
       # openstack-ansible setup-openstack.yml --tags nova-key --limit compute_hosts

--------------

.. include:: navigation.txt
