=====================
pb.retrieve.lldp.yaml
=====================

-----------------------
retrieve LLDP neighbors
-----------------------

retrieve.lldp
=============

This module will retrieve LLDP neighbors from a JunOS device

Example
-------

Here is a basic example:

.. code-block:: yaml

    ### ---------------------------------------------------------------------------
    ### RETRIEVE LLDP NEIGHBORS FROM DEVICE
    ### ---------------------------------------------------------------------------
    - hosts: all
      connection: local
      roles: 
        - juniper.junos

      tasks:
        - name: "### RETRIEVE LLDP NEIGHBORS WITH NETCONF ###"
          juniper_junos_rpc:
            host: "{{ ansible_host }}"
            user: "automation"
            passwd: "juniper123"
            rpc: get-lldp-neighbors-information
          register: output_lldp_neighbors

        - name: "### PRINT OUTPUT TO THE SCREEN ###"
          debug:
            msg: "{{ output_lldp_neighbors }}"
