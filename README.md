## Requirements


1 - En linea de comandos por medio del comando  $ aws configure , ingresar acces_key y secret_key correspondientes.

2 - En el archivo github.tf modificar los valores del repositorio como token, owner y repository.

3 - Ejecutar los comandos para construir la infraestructura:

    $ terraform init 
    $ terraform plan 
    $ terraform apply
    
    # Se solicitara ingresar el token de Github en consola para cargar las secrets en el repositorio
