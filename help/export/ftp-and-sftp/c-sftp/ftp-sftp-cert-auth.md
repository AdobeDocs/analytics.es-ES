---
description: Solo es posible conectarse a una cuenta de FTP sin contraseña si se usan a la vez una conexión SFTP y un método de autenticación alternativo. Para esto se necesita un conjunto de dos archivos (uno residirá en la cuenta de FTP y otro residirá en el equipo), que es una combinación de clave pública y privada.
keywords: ftp;sftp
title: Conectarse a Adobe a través de un SFTP sin contraseña
uuid: 88728309-50d2-450b-b0e6-7dcdf61b5dbc
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '601'
ht-degree: 100%

---


# Conectarse a Adobe a través de un SFTP sin contraseña

Solo es posible conectarse a una cuenta de FTP sin contraseña si se usan a la vez una conexión SFTP y un método de autenticación alternativo. Para esto se necesita un conjunto de dos archivos (uno residirá en la cuenta de FTP y otro residirá en el equipo), que es una combinación de clave pública y privada.

Esto no es menos seguro que la autenticación con contraseña. Se trata de otra forma de autenticación que no requiere que el usuario escriba la contraseña cada vez. Cuando se usa debidamente, estos archivos permiten al equipo en cuestión iniciar sesión sin tener que indicar la contraseña. Esta configuración se debe establecer en cada equipo. Las demás conexiones que no usen estos archivos de claves tienen que especificar una contraseña.

Algunos clientes exigen un SFTP (Protocolo seguro de transferencia de archivos) para transmitir datos confidenciales. Una conexión SFTP es más segura que una conexión FTP normal, ya que la comunicación se establece a través de datos cifrados. De forma predeterminada, todas las cuentas de FTP de Adobe son compatibles con SFTP. Las conexiones SFTP se pueden abrir con un nombre de usuario y una contraseña válidos usando un cliente de SFTP que se conecte al puerto 22 (las conexiones FTP normales, las que no son seguras, usan el puerto 21).

Cuando se utiliza un SFTP, las claves privadas se pueden utilizar bajo ciertas condiciones para conectarse a la cuenta sin contraseña. Con este método, el equipo puede usar archivos de claves para la autenticación en lugar de la habitual autenticación por contraseña. Esto quiere decir que solo el equipo que posee la clave privada puede conectarse sin contraseña. Los demás equipos o usuarios siguen teniendo que autenticarse con contraseña (salvo que también se hayan configurado claves privadas en estos equipos).

**Para configurar y usar claves privadas para la autenticación sin contraseña**

1. Creación de cuenta de FTP (Adobe).

   Un representante de Adobe puede crear una cuenta de FTP si todavía no la tiene. Póngase en contacto con el administrador de cuentas de Adobe o con el servicio de atención al cliente para solicitar la creación de una cuenta.
1. Creación de clave pública/privada (cliente).

   Cree una combinación de clave pública y privada. La clave privada es un archivo que pertenece a su equipo o servidor y solo existe aquí. El archivo de clave pública se debe cargar a la cuenta de Adobe. Cuando se usan de este modo, es posible conectarse sin autenticarse con la contraseña. El archivo de clave pública de Adobe se combina con el archivo de clave privada que está en el equipo o servidor y efectúa la autenticación de esta forma.

   Si desea crear estos archivos, pídale al grupo de soporte técnico de la red interna que cree una clave adecuada para su entorno. Para crear estos dos archivos, se pueden usar muchas herramientas y aplicaciones.

   A continuación, vemos un ejemplo de cómo crearlos en un entorno de shell de UNIX. Esto tan solo es un ejemplo que sirve como punto de referencia para informar de los requisitos a su equipo o grupo de red interna.

   ```
   // Linux/Unix (bash shell)
   
   // First make sure the ".ssh" directory exists
   
   $ mkdir ~/.ssh
   
   $ cd ~/.ssh
   
   // Now actually generate the key pair
   
   // Usually we will want to create an empty passphrase (just hit "Enter" for both password prompts)
   
   $ ssh-keygen -q -t dsa
   
   Enter file in which to save the key (/home/user/.ssh/id_dsa):
   
   Enter passphrase (empty for no passphrase): ...
   
   Enter same passphrase again: ...
   
   // Rename or copy the public key file to "authorized_keys"
   
   // This "authorized_keys" file is the one that we will upload to the Adobe FTP server in step 3
   
   $ cp id_dsa.pub authorized_keys 
   ```

1. Carga de la clave pública a la cuenta de FTP (cliente).

   Cargue y pruebe la clave pública. Conéctese a la cuenta de FTP de Adobe y cree un directorio [!DNL .ssh], en caso de que no exista. Cargue el archivo [!DNL authorized_keys] en este directorio [!DNL .ssh]. Se puede hacer de varias formas (línea de comandos, cliente de FTP gráfico, etc). Lo que se necesita es poder crear un directorio y cargar el archivo.

   A continuación, vemos otro ejemplo de cómo hacerlo usando un shell de UNIX.

   ```
   $ ftp ftp.Adobe.com
   
   OR (depending on hostname provided by Adobe)
   
   $ ftp ftp2.Adobe.com
   
   // Enter username and password for account as prompted
   
   ftp> mkdir .ssh
   
   ftp> cd .ssh
   
   ftp> put authorized_keys
   
   ftp> exit
   
   // Now test the connection by logging in to the server using "sftp" command:
   
   $ sftp username@ftp.omniture.com
   
   OR (depending on hostname provided by Adobe)
   
   $ sftp username@ftp2.omniture.com
   
   // You should immediately receive an sftp prompt without having to enter the password:
   
   sftp>
   ```

