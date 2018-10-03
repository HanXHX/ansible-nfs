NFS Ansible role
================

Install and configure NFS client / server for Debian. It manages cache FS for client. Active support for Debian Jessie+Stretch, should work on other Debian-based systems (Ubuntu).

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

Donation
--------

If this code helped you, or if you’ve used them for your projects, feel free to buy me some :beers:

- Bitcoin: `1BQwhBeszzWbUTyK4aUyq3SRg7rBSHcEQn`
- Ethereum: `63abe6b2648fd892816d87a31e3d9d4365a737b5`
- Litecoin: `LeNDw34zQLX84VvhCGADNvHMEgb5QyFXyD`
- Monero: `45wbf7VdQAZS5EWUrPhen7Wo4hy7Pa7c7ZBdaWQSRowtd3CZ5vpVw5nTPphTuqVQrnYZC72FXDYyfP31uJmfSQ6qRXFy3bQ`

No crypto-currency? :star: the project is also a way of saying thank you! :sunglasses:

Author Information
------------------

- Twitter: [@hanxhx_](https://twitter.com/hanxhx_)
