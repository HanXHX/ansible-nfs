NFS Ansible role
================

Install and configure NFS client / server for Debian. It manages cache FS for client. Active support for Debian Jessie+, should work perfectly on other Debian-based systems (Ubuntu).

Requirements
------------

None.

Role Variables
--------------

### Role configuration

Set true to `nfs_server` or `nfs_client`.

### Client

- `nfs_use_client_cache`: set true to enable filescached
- `nfs_cache_path`: cache directory
- `nfs_mounts`: Hashes with keys ->
  - `localpath`: (M) local directory when you want to mount NFS share
  - `remotepath`: (M) remote directory on NFS server
  - `remotehost`: (M) NFS server IP
  - `enabled`: (O) Boolean. Enable/Disable current mount
  - `item.deleted`: (O) Boolean. Delete share.

### Server

- `nfs_exports`: Hashes with keys ->
  - `path`: (M) directory to share
  - `options`: (M) NFS options (you should RTFM "man exports")
  - `owner`: (O) directory owner
  - `group`: (O) directory group
  - `mode`: (O) directory mode

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: HanXHX.nfs, nfs_server: true }
    - hosts: client
      roles:
         - { role: HanXHX.nfs, nfs_client: true }

License
-------

GPL v2

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
