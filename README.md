Role Name
=========

Installs and configures Snort IDS https://snort.org/

Requirements
------------

None

Vagrant
-------
Spin up Environment under Vagrant to test.
````
vagrant up
````

Role Variables
--------------

````
---
# defaults file for ansible-snort
snort_blacklist_path: /etc/snort/rules
snort_dynamic_library_rules: []
  #- bad-traffic.rules
  #- chat.rules
  #- dos.rules
  #- exploit.rules
  #- icmp.rules
  #- imap.rules
  #- misc.rules
  #- multimedia.rules
  #- netbios.rules
  #- nntp.rules
  #- p2p.rules
  #- smtp.rules
  #- snmp.rules
  #- specific-threats.rules
  #- web-activex.rules
  #- web-client.rules
  #- web-iis.rules
  #- web-misc.rules
snort_external_net: '!$HOME_NET'  #define external networks..if snort_home_net is any then set this to any
snort_home_net: 192.168.0.0/16  #define your home_net..if snort_external_net is any then set this to any
snort_interface: eth0  #defines snort interface to listen on
snort_oinkmaster_rules_url: http://rules.emergingthreats.net/open/suricata/emerging.rules.tar.gz
snort_options: ''  #define additional snort options to pass to startup
snort_preproc_rule_path: /etc/snort/preproc_rules
snort_preproc_rules: []
  #- preprocessor.rules
  #- decoder.rules
  #- sensitive-data.rules
snort_rule_path: /etc/snort/rules
snort_rules:
  - local.rules
  #- app-detect.rules
  - attack-responses.rules
  - backdoor.rules
  - bad-traffic.rules
  #- blacklist.rules
  #- botnet-cnc.rules
  #- browser-chrome.rules
  #- browser-firefox.rules
  #- browser-ie.rules
  #- browser-other.rules
  #- browser-plugins.rules
  #- browser-webkit.rules
  - chat.rules
  - community-sql-injection.rules
  - community-web-client.rules
  - community-web-dos.rules
  - community-web-iis.rules
  - community-web-misc.rules
  - community-web-php.rules
  - community-sql-injection.rules
  - community-web-client.rules
  - community-web-dos.rules
  - community-web-iis.rules
  - community-web-misc.rules
  - community-web-php.rules
  #- content-replace.rules
  - ddos.rules
  - dns.rules
  - dos.rules
  - experimental.rules
  #- exploit-kit.rules
  - exploit.rules
  #- file-executable.rules
  #- file-flash.rules
  #- file-identify.rules
  #- file-image.rules
  #- file-java.rules
  #- file-multimedia.rules
  #- file-office.rules
  #- file-other.rules
  #- file-pdf.rules
  - finger.rules
  - ftp.rules
  - icmp-info.rules
  - icmp.rules
  - imap.rules
  #- indicator-compromise.rules
  #- indicator-obfuscation.rules
  #- indicator-scan.rules
  #- indicator-shellcode.rules
  - info.rules
  #- malware-backdoor.rules
  #- malware-cnc.rules
  #- malware-other.rules
  #- malware-tools.rules
  - misc.rules
  - multimedia.rules
  - mysql.rules
  - netbios.rules
  - nntp.rules
  - oracle.rules
  #- os-linux.rules
  #- os-mobile.rules
  #- os-other.rules
  #- os-solaris.rules
  #- os-windows.rules
  - other-ids.rules
  - p2p.rules
  #- phishing-spam.rules
  #- policy-multimedia.rules
  #- policy-other.rules
  - policy.rules
  #- policy-social.rules
  #- policy-spam.rules
  - pop2.rules
  - pop3.rules
  #- protocol-dns.rules
  #- protocol-finger.rules
  #- protocol-ftp.rules
  #- protocol-icmp.rules
  #- protocol-imap.rules
  #- protocol-nntp.rules
  #- protocol-pop.rules
  #- protocol-rpc.rules
  #- protocol-scada.rules
  #- protocol-services.rules
  #- protocol-snmp.rules
  #- protocol-telnet.rules
  #- protocol-tftp.rules
  #- protocol-voip.rules
  #- pua-adware.rules
  #- pua-other.rules
  #- pua-p2p.rules
  #- pua-toolbars.rules
  - rpc.rules
  - rservices.rules
  #- scada.rules
  - scan.rules
  #- server-apache.rules
  #- server-iis.rules
  #- server-mail.rules
  #- server-mssql.rules
  #- server-mysql.rules
  #- server-oracle.rules
  #- server-other.rules
  #- server-samba.rules
  #- server-webapp.rules
  #- shellcode.rules
  - smtp.rules
  - snmp.rules
  #- specific-threats.rules
  #- spyware-put.rules
  - sql.rules
  - telnet.rules
  - tftp.rules
  - virus.rules
  #- voip.rules
  #- web-activex.rules
  - web-attacks.rules
  - web-cgi.rules
  - web-client.rules
  - web-coldfusion.rules
  - web-frontpage.rules
  - web-iis.rules
  - web-misc.rules
  - web-php.rules
  - x11.rules
snort_so_rule_path: /etc/snort/so_rules
snort_send_stats: true  #true/false
snort_startup: boot
snort_stats_threshold: 1
snort_whitelist_path: /etc/snort/rules
````

Dependencies
------------

None

Example Playbook
----------------

###### Galaxy
    - hosts: servers
      roles:
         - { role: mrlesmithjr.snort }

###### GitHub
    - hosts: servers
      roles:
        - { role: ansible-snort }

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com
