# Rol de ansible para instalar solr

## "Dependencias"

Para el correcto funcionamiento de este playbook es necesario definir la variable $solr_config_templates que es el path a los ficheros de configuración de solr.

Ejemplo de los ficheros necesarios:

```bash
├── infocap_content
│   ├── conf
│   │   ├── schema.xml
│   │   ├── solrconfig.xml
│   └── core.properties
└── solr.xml
```

