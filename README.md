# AWS y PostgreSQL
En el presente documento detallaremos los requisitos y pasos necesarios
para poder desplegar nuestra base de datos.  
Como primer paso debemos de preparar nuestra VPC en AWS con los recursos
que necesitamos según las necesidades que buscamos satisfacer, así mismo, 
los puertos que vamos a exponer en nuestro servidor deben de ser habilitados
desde la interfaz de AWS.  

Seguido de esto podemos proceder a la configuración de la base de datos y las
herramientas que vamos a utilizar. Lo cual se detalla en los siguientes documentos:
* [PostgreSQL](./postgre.md)
* [Docker](./docker.md)
  * [Docker Compose](./docker-compose-pg-only.yml)
