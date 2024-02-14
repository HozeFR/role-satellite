Satellite_installation
=========

A role to install a Satellite server and configure some features

Requirements
------------

The satellite machine must have theses specifications : 
RAM : 20Go
CPU : 8
Disk : 100Go 

Do not forget to set enough space in your partition 

You need to create a file env_vars.yml and put all the variables added in the satellite_installation/defaults/main.yml file
Or, if you do not, please change the vars_files in the play.yml file. 

Role Variables
--------------

All vars are in the env_vars.yml but you can put them elsewhere

SATELLITE: dns_entry
ORG: orga
LOCATION: location
ORGLABEL: orglabel
REDHAT_TOKEN_LOGIN: numbers|name
REDHAT_TOKEN_PASS: <Token Password>
SYNC_PLAN: Daily.Sync.Plan
interval: daily
sync_date: "2016-02-01 01:00:00"

initial_admin: initial_admin
initial_passwd: initial_passwd

dns_ip: X.X.X.X

proxy_hostname: superproxy
proxy_user: superuser
proxy_password: superpassword
proxy_port: proxy_port
subscription_user: user
subscription_password: password_vaulted

repo_list:
  - name: "Red Hat CodeReady Linux Builder for RHEL 8 x86_64 (RPMs)"
    version: 8.6
    product: Red Hat CodeReady Linux Builder for x86_64
  - name: "Red Hat CodeReady Linux Builder for RHEL 9 x86_64 (RPMs)"
    version: 9.2
    product: Red Hat CodeReady Linux Builder for x86_64
  - name: "Red Hat Enterprise Linux 8 for x86_64 - BaseOS (RPMs)"
    version: 8.6
    product: Red Hat Enterprise Linux for x86_64
  - name: "Red Hat Enterprise Linux 8 for x86_64 - AppStream (RPMs)"
    version: 8.6
    product: Red Hat Enterprise Linux for x86_64
  - name: "Red Hat Enterprise Linux 9 for x86_64 - BaseOS (RPMs)"
    version: 9.2
    product: Red Hat Enterprise Linux for x86_64
  - name: "Red Hat Enterprise Linux 9 for x86_64 - AppStream (RPMs)"
    version: 9.2
    product: Red Hat Enterprise Linux for x86_64

CCVname: Global content view

products:
  - Red Hat CodeReady Linux Builder for x86_64
  - Red Hat Enterprise Linux for x86_64

lifecycle_environnement: Library

CCVname: Global content view # nom de la composite content view

products:
  - Red Hat CodeReady Linux Builder for x86_64
  - Red Hat Enterprise Linux for x86_64

lifecycle_environnement: Library


Dependencies
------------

The role needs the collection community.general

