# Solr role

## "Dependencies"

The following dependencies must be added to the requirements.yml:

```yml

- src: geerlingguy.java

- src: geerlingguy.solr

- src: AnsibleShipyard.ansible-zookeeper

```

This are not put in `dependencies: []` in `meta.yml` because in this way it allow to control when each role is executed.

## Available tags

* solr-standalone: install Solr in standalone mode.
* solr-cloud: install Solr in cloud mode.
* solr-zookeeper: install Zookepper and configure Solr in cloud mode.
* solr-active-core: install and configure a Solr core with his collection.

## Active core

When the role installs Solr in cloud mode a flag is created ({{solr_home}}/solr_cloud_mode.flag). This flag is used for the task to differentiate each modes.

The role needs the core name and the config files. The config files can be j2 templates or text files.

Configuration example:

```yml

---
solr_config_j2_templates:
  - {src: "templates/solr_j2/solrconfig.xml.j2", dest: "core_config/solrconfig.xml"}
solr_config_templates_to_sync:
  - {src: "templates/solr/conf/", dest: "core_config/"}
solr_config_core_name: "bitban_content"

```