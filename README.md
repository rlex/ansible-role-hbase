###### Desc

Installs and configures hbase and required software (zookeeper, hbase master and regionservers, thrift and rest)

###### Deps

This role is essentially plugin for [ansible-role-hadoop](https://github.com/rlex/ansible-role-hadoop) and should be run after it

###### Params for install

For using in host/group vars, allows you to select which parts of hbase to install

```
hbase_master: false
hbase_region: false
hbase_rest: false
hbase_thrift: false
hbase_zookeeper: false
```

You will need to manually specify zookeeper quorum in hbase_zookeeper_quorum:

```
hbase_zookeeper_quorum:
  - hdp-1.staging.lab
  - hdp-2.staging.lab
  - hdp-3.staging.lab
```

Also make sure to set hbase_master_host to ip/hostname pointing to node with hbase_master.

###### Ports

* 16010 - masterserver UI
* 16030 - regionserver UI
