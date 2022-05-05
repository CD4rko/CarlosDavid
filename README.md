## Guía de instalación de ELK en un Servidor on-prem

# Definición

Elastic es un SIEM que se compone de varios servicios en este caso vamos a instalar todos los Servicios que componen el núcleo de Elastic es decir ElasticSearch, Kibana, Fleet, Logstash y un agente de métricas llamado metricbeats.

# índice de la guía


- Instalación de ElasticSearch

1. Primero vamos a añadir la clave PGP de ElasticSearch

<code>wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg</code>

2. Ahora procedereos a instalar el paquete apt-transport-https que nos hará falta.

<code>sudo apt-get install apt-transport-https</code>

3. Ahora añadiremos los repositorios de ElasticSearch 8.X

<code>echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list</code>

- Instalación de Kibana
    - Instalación de Kibana por HTTP
    - Instalación de Kibana por HTTPS
 - Logstash HTTPS
 - Fleet - Elastic-Agent
 - Metricbeat
