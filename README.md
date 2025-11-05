# ansible-role-dovecot-archive
An Ansible role to install and configure Dovecot as an e-mail archive target.

## Requirements
* Debian < 12 (Bookworm and older)

## Usage
Clone (?) this repository into your playbook's `roles` directory (e.g. `roles/dovecot-archive`)

### Example Playbook
```
- hosts: all
  roles:
    - dovecot-archive
```

### Add Users
Add virtual users to `/etc/dovecot/users`.
* Generate a hash of the desired password with `doveadm pw`.
* `5000:5000` is the uid:gid of the `vmail` user:group
```
user:{CRYPT}$2y$05$b/E5k9b98ZPI5FqVgyfkju9j6uv6EEqTBtfDSeiCboHgVZHCIYjFW:5000:5000::
```

## Sources
* [Dovecot 2.3 Configuration Manual](https://doc.dovecot.org/2.3/configuration_manual/)
* [ArchWiki | Virtual user mail system with Postfix, Dovecot and Roundcube](https://wiki.archlinux.org/title/Virtual_user_mail_system_with_Postfix,_Dovecot_and_Roundcube)
