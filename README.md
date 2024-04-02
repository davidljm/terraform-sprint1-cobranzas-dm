## Requirements

### Initial

1 - En linea de comandos por medio del comando  $ aws configure , ingresar acces_key y secret_key correspondientes.

2 - En el archivo github.tf modificar los valores del repositorio como token, owner y repository.

3 - Ejecutar los comandos para construir la infraestructura:

    $ terraform init 
    $ terraform plan 
    $ terraform apply
    
    # Se solicitara ingresar el token de Github en consola para cargar las secrets en el repositorio

### GRAFANA
OPEN EC2 CONSOLE OR SSH 

Step 1: sudo su  

Step 2: The installation is via yum repository, create a grafana.repo under:
cd /etc/yum.repos.d/
vi grafana.repo  

Step 3: Put below content in grafana.repo with i and save it with :wq!.

[grafana]
name=grafana
baseurl=https://packages.grafana.com/oss/rpm
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://packages.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt 

Step 4: Once done with the above steps. It's time to install grafana now:

sudo yum -y install grafana  

Step 5: Start the server:

sudo systemctl start grafana-server

systemctl status grafana-server 

Step 6: Open in the browser with te public ip o public dns with :3000 (the port).

The user and pass the firs time is admin admin, change it. 

Step 7: In Grafana Home, go to Configuration --> Data Sources and select add Data source

Step 8: Search CloudWatch

Step 9: in CloudWatch's settings put in Auth Provider access & secret key

Step 10: put yours credentials

Step 11: in CloudWatch's Dashboards import AWS EC2 and AWS EBS, or you can make new dashboards.

Step 12: in Grafana Home select Dashboards and choice EC2 or EBS.