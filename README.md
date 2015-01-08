## alban.andrieu.awstats

[![Travis CI](http://img.shields.io/travis/AlbanAndrieu/ansible-awstats.svg?style=flat)](http://travis-ci.org/AlbanAndrieu/ansible-awstats) [![Branch](http://img.shields.io/github/tag/AlbanAndrieu/ansible-awstats.svg?style=flat-square)](https://github.com/AlbanAndrieu/ansible-awstats/tree/master) [![Donate](https://img.shields.io/gratipay/AlbanAndrieu.svg?style=flat)](https://www.gratipay.com/AlbanAndrieu)  [![Ansible Galaxy](http://img.shields.io/badge/galaxy-alban.andrieu.awstats-blue.svg?style=flat)](https://galaxy.ansible.com/list#/roles/2538) [![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)

Ensures that mod awstats is installed (using apt) on apache.

### Installation

This role requires at least Ansible `v1.6.3`. 

To install it, run:

    ansible-galaxy install alban.andrieu.awstats

### Role dependencies

- `geerlingguy.apache`

### Role variables

List of default variables available in the inventory:

```yaml
        awstats_enabled: yes                       # Enable module
    
    # Package states: present or installed or latest
    awstats_pkg_state: present
    # Repository states: present or absent
    #awstats_repository_state: present
    
    apache_directory : "apache2"
    apache_conf_path: "/etc/{{ apache_directory }}"
    apache_log_path: "/var/log/{{ apache_directory }}"
    #apache_log_path: "${APACHE_LOG_DIR}"
    
    awstats_conf_path: "/etc/awstats"
    #awstats_conf_file: "awstats.conf.local"
    awstats_domain: "home.nabla.mobi"
    awstats_conf_file: "awstats.{{ awstats_sitedomain }}.conf"
    awstats_logfile: "{{ apache_log_path }}/access.log"
    awstats_sitedomain: "{{ awstats_domain }}"
    
    apache_awstats_enabled: yes
    apache_create_vhosts: yes
    
    apache_vhosts_awstats:
      - {servername: "localhost", serveradmin: "alban.andrieu@nabla.mobi", documentroot: "/usr/lib/cgi-bin"}
```


### Detailed usage guide

Describe how to use in more detail...


### Authors and license

`alban.andrieu.awstats` role was written by:
- [Alban Andrieu](fr.linkedin.com/in/nabla/) | [e-mail](mailto:alban.andrieu@free.fr) | [Twitter](https://twitter.com/AlbanAndrieu) | [GitHub](https://github.com/AlbanAndrieu)
- License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/AlbanAndrieu/ansible-awstats/issues)!

***

README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).
