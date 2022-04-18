# remote_psql_access
Playbook de Ansible para habilitar el acceso remoto a Postgresql

Los archivos ".conf" son archivos de configuración de Postgresql, que han sido modificados con la configuración necesaria para permitir el acceso remoto.

Lo que hace el playbook es coger esos archivos de configuración y transferirlos a los hosts de destino, de esta forma se reemplazan los antiguos por los nuevos.
Luego se reinicia el servicio de Postgresql y ya estaría todo listo.

Deberás modificar el archivo "hosts" poniendo las ip de los hosts a los que quieras que el playbook les afecte. También deberás modificar el archivo "vars.yml" poniendo la ruta en la que tienes almacenado los archivos de configuración de Postgresql (file1 y file2), es muy importante que NO modifiques la variable "Dest".

Una vez ejecutado el playbook, introduce el comando "psql -h (ip del servidor) -U (nombre de usuario) (nombre de la base de datos)" y así te conectarás de forma remota a tu servidor de base de datos.

Ej: psql -h 192.168.40.60 -U root databse1
--------------------------------------------
## Información de la modificiación realizada:
Se ha añadido una tasks que reinicia el firewall para que se apliquen los cambios
#
Playbook original de @ffrias9
