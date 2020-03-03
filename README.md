VVV site template for techblog.wikimedia.org
============================================

This fork of VVV's [custom-site-template] has been hacked up to provision
a local development environment for working on the techblog.wikimedia.org site
which is hosted by https://wpvip.com/.

Usage
-----
1. Install VVV using [their instructions]
2. Replace `config/config.yml` with the YAML provided below
3. `vagrant up`
4. Visit http://techblog.local.wmftest.net/ to see your local blog

YAML config file
----------------
```yaml
---
sites:
  techblog.wikimedia.org:
    skip_provisioning: false
    description: "Testing for wpvip managed WordPress blog"
    hosts:
      - techblog.local.wmftest.net
    repo: https://github.com/bd808/vvv-wmf-techblog-site-template.git
    custom:
      site_title: "News from the Wikimedia technical movement"
      install_test_content: false

utilities:
  core: # The core VVV utility
    - tls-ca # HTTPS SSL/TLS certificates

vm_config:
  memory: 2048
  cores: 2

general:
  db_backup: false
  db_restore: false
  db_share_type: false
  #github_token: xxxxxx

vagrant-plugins:
  disksize: 10GB # requires the disk size vagrant plugin
```

[custom-site-template]: https://github.com/Varying-Vagrant-Vagrants/custom-site-template
[their instructions]: https://varyingvagrantvagrants.org/docs/en-US/installation/
