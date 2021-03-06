Stouts.denyhosts
============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.denyhosts.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.denyhosts)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.denyhosts-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/854)

Ansible role which simple manage denyhosts

#### Variables

```yaml
denyhosts_enabled: yes                  # The role in enabled
denyhosts_version: "2.10"               # Set denyhosts version
denyhosts_url: http://downloads.sourceforge.net/project/denyhost/denyhost-{{denyhosts_version}}/denyhosts-{{denyhosts_version}}.tar.gz
denyhosts_prefix: /opt/denyhosts
denyhosts_work_dir: "{{denyhosts_prefix}}/var/lib/denyhosts"
denyhosts_run_dir: "{{denyhosts_prefix}}/run"
denyhosts_log_dir: "{{denyhosts_prefix}}/var/log"
denyhosts_etc_dir: "{{denyhosts_prefix}}/etc"

denyhosts_daemon: no                     # Run in daemon mode
denyhosts_schedule: "0 * * * *"          # Run each hour

denyhosts_lock_file: "{{denyhosts_run_dir}}/denyhosts.pid"
denyhosts_daemon_log: "{{denyhosts_log_dir}}/denyhosts"

denyhosts_admin_email: "root@localhost"
denyhosts_age_reset_invalid: "10d"
denyhosts_age_reset_restricted: "25d"
denyhosts_age_reset_root: "25d"
denyhosts_age_reset_valid: "5d"
denyhosts_allowed_hosts_hostname_lookup: no
denyhosts_block_service: "sshd"
denyhosts_daemon_log_message_format: "%(asctime)s - %(name)-12s: %(levelname)-8s %(message)s"
denyhosts_daemon_log_time_format: no
denyhosts_daemon_purge: "1h"
denyhosts_daemon_sleep: "30s"
denyhosts_deny_threshold_invalid: 5
denyhosts_deny_threshold_restricted: 1
denyhosts_deny_threshold_root: 1
denyhosts_deny_threshold_valid: 10
denyhosts_sync_server: "http://xmlrpc.denyhosts.net:9911"
denyhosts_hostname_lookup: yes
denyhosts_hosts_deny: '/etc/hosts.deny'
denyhosts_plugin_deny: no
denyhosts_plugin_purge: no
denyhosts_purge_deny: ""
denyhosts_purge_threshold: 0
denyhosts_reset_on_success: yes
denyhosts_secure_log: "/var/log/auth.log"
denyhosts_smtp_date_format: "%a, %d %b %Y %H:%M:%S %z"
denyhosts_smtp_from: "DenyHosts <nobody@{{denyhosts_smtp_host}}>"
denyhosts_smtp_host: "localhost"
denyhosts_smtp_port: 25
denyhosts_smtp_username: ""
denyhosts_smtp_password: ""
denyhosts_smtp_subject: "DenyHosts Report"
denyhosts_suspicious_login_report_allowed_hosts: yes
denyhosts_sync_download: yes
denyhosts_sync_download_resiliency: "5h"
denyhosts_sync_download_threshold: 3
denyhosts_sync_interval: "1h"
denyhosts_sync_upload: yes
denyhosts_syslog_report: no
denyhosts_userdef_failed_entry_regex: no
```

#### Usage

Add `Stouts.denyhosts` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.denyhosts

  vars:
    denyhosts_daemon: yes
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.denyhosts/issues)!
