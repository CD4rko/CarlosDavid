## Guía completa de instalación de ELK en un Servidor on-prem

# Definición

Elastic es un SIEM que se compone de varios servicios en este caso vamos a instalar todos los Servicios que componen el núcleo de Elastic es decir ElasticSearch, Kibana, Fleet, Logstash y un agente de métricas llamado metricbeats.

# Guía

- Instalación de ElasticSearch

1.Primero vamos a añadir la clave PGP de ElasticSearch

<code>wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg</code>

2.Ahora procedereos a instalar el paquete apt-transport-https que nos hará falta.

<code>sudo apt-get install apt-transport-https</code>

3.Ahora añadiremos los repositorios de ElasticSearch 8.X

<code>echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list</code>

4.Actualizaremos la máquina y después procederemos con la instalación de ElasticSearch

<code>sudo apt update && sudo apt install elasticsearch -y</code>

5.Después de instalar el elasticsearch veremos que nos da una contraseña del usuario elastic esa contraseña la guardaremos en un keepas o similar para utilizarla posteriormente.

(/assets/Elasticsearch/elasticsearch1.jpg)

6.Lo siguiente que haremos será abrir el fichero de configuración de elasticsearch y ver que tenemos

(/assets/Elasticsearch/elasticsearch2.jpg)

- Instalación de Kibana
    - Instalación de Kibana por HTTP
    - Instalación de Kibana por HTTPS
 - Logstash HTTPS
 - Fleet - Elastic-Agent
 - Metricbeat
