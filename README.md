# apache

Reemplace `$ALUMNO` por el nombre de su nombre de usuario en www.tecnologoinformatico.com

EJ: `dmascheroni`

1. Cree el directorio ~/repositorios y dentro clone el
repositorio: `https://github.com/TecnologoInformatico/AdmInf-web.git`
2. Actualice el repositorio de la lista de paquetes.
    `apt update`
3. Instalar el servidor Apache mediante apt.
4. Cree el directorio /var/www/$ALUMNO
5. Asigne como propietario del directorio su usuario.
6. Configure un nuevo Virtual host. (copiando el archivo de configuración por defecto)
  6.1. ServerName $ALUMNO.tecnologoinformatico.com
  6.2. Correo de contacto con el administrador.
  6.3. El root de la aplicación. (/var/www/$ALUMNO)
7. Modifique el archivo /etc/hosts de modo que el ServerName coincida con este equipo `127.0.0.1`.
8. Reinicie el servidor apache para que los cambios tengan efecto.
9. Copie el contenido del directorio ~/repositorios/AdmInf-web a /var/www/$ALUMNO, de tal modo que el contenido del repositorio antes clonado se encuentre en el root de la aplicación.
10. Verifique que el servidor funcione correctamente.
11. Ingrese la IP del servidor y el servername a continuación:

```json
{
    "serverName": "",
    "ip": ""
}
```


```1-
mkdir repositorios
cd repositorios
git clone https://github.com/TecnologoInformatico/AdmInf-web.git

2-
sudo apt update

3-
sudo apt install apache2

4-
sudo mkdir /var/www/ssosa

5-
sudo chown ubuntu /var/www/ssosa

6-
cd /etc/apache2/sites-available/
sudo cp 000-default.conf ssosa.conf
sudo nano ssosa.conf
	ServerName ssosa.tecnologoinformatico.com
	ServerAdmin santiago.sosa.m@estudiantes.utec.edu.uy
	DocumentRoot /var/www/ssosa/

7-
cd ..
cd ..
sudo nano hosts
	127.0.0.1 ssosa.tecnologoinformatico.com

8-
sudo systemctl restart apache2

9-
sudo cp -r ~/repositorios/AdmInf-web/* /var/www/ssosa/

10-
Ingreso 144.22.253.73 en el navegador (Por algun motivo no funciona)

11-
{
    "serverName": "ssosa.tecnologoinformatico.com",
    "ip": "144.22.253.73"
}
```
