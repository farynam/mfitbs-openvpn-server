Role Name
=========

Simple private network deployment tool through Ansible based on OpenVPN. This is a server part.

Requirements
------------

* Ansible 2.8.5
* Debian 10

Role Variables
--------------

###### EasyRSA host
* easy_rsa_host - host on which easyrsa will be installed.
* EASY_RSA_BIN - easyrsa script path.
* ca_cn - easyrsa CA cert base file name.
* PKI_DIR - easyrsa cert repo path

###### Server host
* server_host - Openvpn server/hub inventory name.
* server_port - Openvpn server/hub port.
* client_to_client - is client to client communication allowed.

###### all
* id_type - ID type (certficate field subject-alt-name) in cert can be DNS or IP
* proto - proto for openvpm connections values:tcp,udp 
* host_pki_dir - host PKI dir (where keys, certs, ... being kept).
* dh - openvpn Diffie–Hellman file name base
* dh_len - Diffie–Hellman param length. 
* cipher - openvpn cipher.
* log_status - openvpn status log.
* log - openvpn log. 

Dependencies
------------

* mfitbs-openvpn-easyrsa
* mfitbs-openvpn-generic

Example Playbook
----------------

- name: Install server
  hosts: server
  roles:
  - role: openvpn-server


License
-------

MIT

Author Information
------------------

Marcin Faryna
