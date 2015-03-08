Foorge Loadbalancer
===================

Loadbalancer component for Foorge Clusters using HAProxy. It provides services
for routing public traffic to web processes, optionally with SSL termination.

Requirements
------------

- Ubuntu
- qafoo.base role
- qafoo.consul role

Minimal example
---------------

    ---
    - hosts: loadbalancer
      roles:
        - name: "foorge.loadbalancer"
          loadbalancer_public_domains:
            - { server: "qafoo.com", process: "web" }
            - { server: "staging.qafoo.com", process: "web_stage" }
            - { server: "shop.qafoo.com", process: "web_shop", port: 443, certificate: "qafoo.pem" }

License
-------

MIT
