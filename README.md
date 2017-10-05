# Rol de ansible para instalar solr

## "Dependencias"

Para el correcto funcionamiento de este playbook es necesario definir la variable ```$solr_config_templates``` que es el path a los ficheros de configuración de solr.

Ejemplo de los ficheros necesarios:

```bash
├── infocap_content
│   ├── conf
│   │   ├── schema.xml
│   │   ├── solrconfig.xml
│   └── core.properties
└── solr.xml
```

También hay que añadir al requirements.yml las siguientes dependencias.

```
- src: geerlingguy.java
- src: geerlingguy.solr
```

Esto se hace así en lugar de añadirlo en el meta para poder hacer include del rol y poder controlar el include mediante una tarea.
