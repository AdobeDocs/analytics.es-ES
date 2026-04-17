---
title: Requisitos de seguridad para servidores FTP y SFTP
description: Obtenga información acerca de los requisitos de seguridad para servidores FTP y SFTP.
feature: Data Configuration and Collection
role: Admin
source-git-commit: 26ae4edacbc3591d4d3358afe009bf7831d45efb
workflow-type: tm+mt
source-wordcount: '1899'
ht-degree: 2%

---

# Requisitos de seguridad para servidores FTP y SFTP

Esta página cubre los requisitos de seguridad para los servidores FTP y SFTP existentes que reciben datos suministrados por fuentes de datos de Adobe Analytics o por Data Warehouse.

* **Servidores FTP existentes**: Se deben actualizar para usar SFTP, como se describe en la sección siguiente, [Actualizar servidores FTP para usar SFTP](#upgrade-ftp-servers-to-use-sftp).

  La actualización de FTP a SFTP es un requisito, ya que SFTP ofrece una mayor seguridad.

  Como alternativa, para un nivel más alto de seguridad, puede realizar la transición a un destino de nube moderno. (Para obtener más información, consulte [Configurar cuentas de importación y exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-accounts).)

* **Servidores SFTP existentes (y servidores SFTP recién actualizados)**: Debe rotar las contraseñas antiguas, tal como se describe en la sección siguiente, [Rotar la contraseña SFTP](#rotate-your-sftp-password).

  La rotación regular de la contraseña del SFTP es una práctica recomendada de seguridad que ayuda a proteger los datos.

>[!IMPORTANT]
>
>Tenga en cuenta las siguientes situaciones antes de completar los pasos de este artículo.
>
>* **Adobe recomienda realizar la transición a un destino de nube moderno en lugar de actualizar a SFTP, si es posible.**
>FTP y SFTP son tipos de destino heredados. En lugar de actualizar las cuentas de FTP a SFTP y rotar las contraseñas SFTP como se describe en este artículo, Adobe recomienda pasar a un tipo de destino de nube moderno (como Amazon S3, Google Cloud Platform o Azure). Estos destinos en la nube proporcionan un nivel más alto de seguridad. Para obtener más información, consulte [Configurar cuentas de importación y exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-accounts).
>
>* **Si las cuentas FTP y SFTP se usan exclusivamente para clasificaciones, migre a los conjuntos de clasificaciones.**
>Si su cuenta FTP o SFTP se usa exclusivamente para clasificaciones, debería migrar del **importador de clasificaciones** a **conjuntos de clasificaciones**, en lugar de actualizar las cuentas FTP a SFTP y rotar las contraseñas SFTP como se describe en este artículo. El importador de clasificaciones quedará obsoleto y dejará de ser accesible después del **31 de agosto de 2026**. Para obtener más información, consulte [Descripción general de los conjuntos de clasificaciones](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview).

## Requisitos previos

### Inventario de cuentas de FTP

Los procesos descritos en esta página al actualizar servidores FTP para utilizar SFTP deben completarse para cada sitio FTP utilizado para fuentes de datos y Data Warehouse.

Como tal, debe identificar todas las cuentas de FTP que reciban datos para fuentes de datos o Data Warehouse. Esta información se muestra en las opciones de configuración de FTP, tal como se describe en la sección [Tipos de cuentas heredadas](/help/components/locations/configure-import-accounts.md#configure-a-location-account) del artículo [Configurar cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md).

Para cada cuenta, recopile la siguiente información:

* **Host**: El nombre de host del servidor FTP al que se conecta su cuenta (por ejemplo, `ftp.omniture.com`, `ftp2.omniture.com`, etc.).

* **Puerto**: Cuando se usa un servidor SFTP alojado en Adobe, los clientes SFTP se conectan en el puerto 22. Las conexiones FTP no seguras utilizan el puerto 21.

* **Nombre de usuario**: El nombre de usuario usado para iniciar sesión en el servidor FTP.

* **Secreto de cuenta de ubicación**: El secreto de cuenta actual de la cuenta. Secreto de cuenta (contraseña) que se utiliza actualmente para descargar datos enviados a su ubicación FTP. Esta información no está disponible en la interfaz de Adobe Analytics.

### Confirme que puede actualizar las credenciales en las herramientas

Asegúrese de que puede actualizar las contraseñas SFTP en cualquier herramienta o script que utilice para conectarse al sitio SFTP (por ejemplo, un cliente SFTP, un script automatizado o una plataforma de terceros).

Todos los clientes deben conectarse mediante SFTP con una contraseña como reserva.

## Actualización de servidores FTP para utilizar SFTP

>[!IMPORTANT]
>
>Si los datos de FTP se entregan a un socio de terceros (por ejemplo, una empresa de consultoría o un proveedor de análisis), debe coordinarse con ellos antes de seguir los pasos descritos en este artículo.

### Paso 1: Generar las claves SSH de su organización para descargar datos

En esta sección se describe cómo generar las claves SSH de su organización (un par de claves pública y privada) que se usan para **descargar datos** del servidor SFTP.

>[!NOTE]
>
>En un paso futuro, descargará otra clave pública proporcionada por Adobe. Esto forma parte de un segundo par de claves públicas/privadas, que Adobe usa para **cargar datos** en el servidor SFTP.

Para configurar la transferencia segura para descargar datos desde el servidor FTP:

1. Inicie sesión en la estación de trabajo donde descargue datos del servidor FTP.

1. Genere un par de claves pública y privada para utilizarlo en una transferencia segura.

   Cuando se utiliza un servidor FTP alojado en Adobe, Adobe admite claves RSA y ed25519.

   * **En un entorno Linux**: Ejecute el siguiente comando para generar el par de claves ed25519:

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     Si la directiva no le permite utilizar claves ed25519, ejecute el siguiente comando para generar el par de claves RSA:

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **En un entorno Windows**: Use PuTTYgen.

1. Cree un archivo con el nombre [!DNL `authorized_keys`] (sin extensión).

1. Copie el contenido de la clave pública en el archivo [!DNL `authorized_keys`].

1. En un paso futuro, volverá a este archivo de [!DNL `authorized_keys`] para agregar la clave pública de Adobe, que Adobe utiliza para cargar datos en el servidor SFTP. A continuación, agregará el archivo [!DNL `authorized_keys`] al servidor SFTP.

### Paso 2: Crear una nueva cuenta de ubicación SFTP en Adobe Analytics

Cree una nueva cuenta de ubicación SFTP para reemplazar cada cuenta existente de FTP.

Al crear una nueva cuenta de ubicación SFTP, debe utilizar el mismo nombre de host y nombre de usuario que se utilizan en la cuenta de FTP existente que está reemplazando.

>[!NOTE]
>
>En un paso futuro, configurará esta nueva cuenta de ubicación para que se utilice como destino para las fuentes de datos y las entregas de Data Warehouse.

#### Creación de la cuenta SFTP

1. En Adobe Analytics, vaya a [!UICONTROL **Componentes**] > [!UICONTROL **Ubicaciones**].

1. Seleccione la ficha [!UICONTROL **Cuentas de ubicación**].

1. Seleccione [!UICONTROL **Agregar cuenta**].

1. En el campo desplegable [!UICONTROL **Tipo de cuenta**], seleccione [!UICONTROL **SFTP (heredado)**].

1. Complete los campos siguientes:

   | Nombre de campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de host**] | Su nombre de host SFTP (por ejemplo, `ftp.omniture.com`). |
   | [!UICONTROL **Puerto**] | El puerto del cortafuegos a través del cual se enviarán los datos. Es el puerto 22 para conexiones SFTP alojadas en Adobe. |
   | [!UICONTROL **Nombre de usuario**] | Su nombre de usuario SFTP. Utilice el mismo nombre de usuario que utilizó para su cuenta de FTP. |

1. Seleccione [!UICONTROL **Guardar**].

1. En el cuadro de diálogo [!UICONTROL **Cuenta creada**], descargue la clave pública RSA o ed25519 y, a continuación, seleccione **[!UICONTROL Aceptar]**. Es la clave pública SSH que utiliza Adobe para cargar datos en el servidor SFTP. (Utilizará esta clave en la siguiente sección: [Agregue la clave pública SSH de Adobe al servidor SFTP](#add-adobes-ssh-public-key-to-the-sftp-server)).

1. Repita este proceso para cada cuenta SFTP que desee crear.

1. Continúe con la sección siguiente, [Cargue la clave pública en el servidor SFTP](#upload-the-public-key-to-the-sftp-server).

#### Agregue la clave pública SSH de Adobe al archivo `authorized_keys` y cárguela en su servidor FTP

La clave pública que descargó en el paso 7 de la sección anterior es parte de un par de claves pública y privada que Adobe usa para **cargar datos** en el servidor SFTP.

Debe agregar esta clave pública al mismo archivo `authorized_keys` donde agregó anteriormente la clave de descarga de su organización (la que generó en [Paso 1: Genere la clave de descarga de su organización y agréguela a su servidor FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server)).

Para agregar la clave pública SSH de Adobe al archivo `authorized_keys` y cargarla en el servidor FTP:

1. Inicie sesión en la estación de trabajo donde descargue datos del servidor FTP.

1. Abra el archivo [!DNL `authorized_keys`] y agréguele la clave de carga de Adobe. Este archivo ya debería contener la clave de descarga de su organización en [Paso 1: Genere la clave de descarga de su organización y agréguela a su servidor FTP](#step-1-generate-your-organizations-download-key-and-add-it-to-your-ftp-server).

1. Cargue el archivo [!DNL `authorized_keys`] en su servidor FTP:

   1. Conéctese al servidor FTP e inicie sesión con su nombre de usuario y contraseña.\
      Puede ser un servidor FTP alojado en Adobe o su propio servidor FTP.
   1. Cree un directorio [!DNL .ssh], (si no existe todavía).
   1. Cargue el archivo [!DNL `authorized_keys`] en el directorio [!DNL .ssh].

1. Actualice la configuración del cortafuegos para permitir conexiones entrantes desde el servidor SFTP. Cuando utilice un servidor SFTP alojado en Adobe, permita las conexiones entrantes desde los intervalos de IP de Adobe en el puerto 22.

1. Inicie sesión en el servidor con el cliente SFTP para probar la conexión.

1. Repita este proceso con cada cuenta SFTP que haya creado en la sección anterior, [Crear la cuenta SFTP](#create-the-sftp-account).

1. Continúe con la sección siguiente, [Agregar una ubicación dentro de la cuenta](#add-a-location-within-the-account).

#### Añadir una ubicación dentro de la cuenta

1. En la ficha **Ubicaciones**, seleccione **Agregar ubicación**.

1. Especifique un nombre, una descripción y si esta ubicación se utilizará con las fuentes de datos o con Data Warehouse.

1. En el campo [!UICONTROL **Cuenta de ubicación**], seleccione la cuenta que acaba de crear.

1. En el campo [!UICONTROL **Ruta de directorio**], especifique la ruta al directorio en el servidor SFTP. Las carpetas de la ruta de acceso ya deben existir; de lo contrario, se produce un error. Por ejemplo, `/folder_name/folder_name`.

1. Seleccione **Guardar**.

1. Repita este proceso para cada cuenta SFTP que haya creado.

Para obtener instrucciones detalladas, consulte [Configurar ubicaciones de importación y exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-locations).

### Paso 3: Editar fuentes de datos y solicitudes de Data Warehouse para utilizar el nuevo destino SFTP

Actualice las fuentes de datos programadas y las solicitudes de Data Warehouse existentes que actualmente envían datos a destinos FTP para utilizar los nuevos destinos SFTP que haya creado.

#### Editar fuentes de datos

Edite cada fuente de datos programada configurada con el antiguo destino FTP para utilizar el nuevo destino SFTP:

1. En Adobe Analytics, seleccione [!UICONTROL **Administración**] > [!UICONTROL **Fuentes de datos**].

1. Busque la fuente de datos que desea editar. Para localizar una fuente de datos, puede [filtrar y buscar en la lista de fuentes de datos](#filter-and-search-the-list-of-data-feeds).

1. Seleccione la fuente de datos en la columna [!UICONTROL **Nombre de fuente**].

   Se muestra la página [!UICONTROL **Editar _nombre_fuente_**].

1. En la sección [!UICONTROL **Destino**], en el campo [!UICONTROL **Cuenta**], utilice el menú desplegable para seleccionar el nuevo destino SFTP que ha creado.

1. En el campo [!UICONTROL **Ubicación**], utilice el menú desplegable para seleccionar la ubicación en la cuenta SFTP.

1. Seleccione [!UICONTROL **Guardar**].

Para obtener información más detallada, consulte [Editar una fuente de datos](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) en [Administrar fuentes de datos](/help/export/analytics-data-feed/df-manage-feeds.md).

#### Editar solicitudes de Data Warehouse

Edite cada solicitud de Data Warehouse programada que esté configurada con el destino de FTP antiguo para utilizar el nuevo destino de SFTP:

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee editar.

   ![Administrar una solicitud](assets/dw-manage-request.png)

1. Seleccione [!UICONTROL **Editar**].

1. Seleccione la ficha [!UICONTROL **Destino del informe**].

1. En el campo [!UICONTROL **Cuenta**], utilice el menú desplegable para seleccionar el nuevo destino SFTP que ha creado.

1. En el campo [!UICONTROL **Ubicación**], utilice el menú desplegable para seleccionar la ubicación en la cuenta SFTP.

1. Seleccione [!UICONTROL **Guardar cambios**].

Para obtener información más detallada, consulte [Editar solicitudes](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) en [Administrar solicitudes de Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Paso 4: Actualizar la configuración del cortafuegos

Si aún no lo ha hecho, debe actualizar la configuración del cortafuegos de la siguiente manera:

* **Al usar los servidores FTP de Adobe**: debe actualizar la configuración del firewall para permitir **conexiones salientes** en el puerto 22.

* **Al usar su propio servidor FTP**: debe actualizar la configuración del firewall para permitir la conexión **entrante** en cualquier puerto en el que aloje el servicio, que suele ser el puerto 22.

También debe eliminar las reglas antiguas específicas del FTP, como permitir conexiones entrantes en el puerto 21. (FTP utiliza el puerto 21, además de una serie de puertos adicionales para la transferencia de datos. Como práctica recomendada de seguridad, debería eliminar este acceso innecesario a través del cortafuegos).

### Paso 5: Asegúrese de que las fuentes de datos programadas y las solicitudes de Data Warehouse se entreguen correctamente

Después de actualizar cada fuente de datos y solicitud de Data Warehouse existentes para utilizar la nueva cuenta y ubicación SFTP, espere a la siguiente entrega programada. Compruebe que los datos llegan al nuevo destino según lo esperado.

### Paso 6: Rotar la contraseña en el servidor SFTP actualizado

Después de actualizar un servidor FTP a SFTP, también debe rotar la contraseña de SFTP, como se describe en la siguiente sección: [Rotar la contraseña de SFTP](#rotate-your-sftp-password).

## Rotación de la contraseña SFTP

Una contraseña SFTP sirve como método de autenticación de reserva si falla la autenticación basada en claves.

Gire la contraseña de SFTP inmediatamente después de actualizar de FTP a SFTP. Debe continuar rotándolo en un horario regular, de acuerdo con las políticas establecidas.

1. Póngase en contacto con el Servicio de atención al cliente de Adobe y solicite una nueva contraseña.

1. Para cada cuenta SFTP, proporcione **Hostname** y **Username**.

   El Servicio de atención al cliente generará una nueva contraseña para cada cuenta de FTP.

1. Actualice la contraseña en el cliente que utilice para conectarse al servidor SFTP.


<!--
< **_Ignore everything after this_** >

-------

## Set up a new SFTP server or upgrade your existing FTP server

## Upgrade your FTP server to use SFTP where files are delivered or FTP account to use SFTP

Set up an SFTP server where Data Feed and Data Warehouse files can be delivered. This could beYou first need to upgrade your FTP server to use SFTP To upgrade an FTP account to use SFTP, follow the steps in [Connect to an FTP account with SFTP](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md).

## Create an SFTP account

## Rotate the passphrase on SFTP accounts


 
Adobe recommends that you periodically rotate the account secrets (passwords) on your FTP accounts that are associated with Data Feeds and Data Warehouse. 
 
Regular rotation of account secrets is a security best practice that helps protect your data. 
 
To ensure uninterrupted reception of data, follow the steps in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets) prior to changing any account secrets.  
 
>[!IMPORTANT] 
> 
>If your FTP data is delivered to a third-party partner (for example, a consulting firm or Adobe Analytics vendor), coordinate with them before rotating account secrets. The third-party partner will need to update their own tools and scripts with the new account secrets immediately after the new account secrets are provided by your FTP host provider (either Adobe or another provider).

## When rotating account secrets is not necessary 
 
### Transition from FTP to a cloud destination 
 
FTP and SFTP are legacy destination types. Rather than rotating FTP account secrets, Adobe recommends moving to a modern cloud destination type (such as Amazon S3, Google Cloud Platform, or Azure), which provide a higher level of security. For more information, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
### Transition from the Classifications importer to Classification sets 
 
If your FTP account is used exclusively for Classifications, you should migrate from the **Classifications importer** to **Classification sets**, rather than rotating your FTP account secrets. The Classification importer will be deprecated and no longer accessible after **August 31, 2026**. For more information, see [Classification sets overview](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/sets/overview). 

## Prepare to rotate account secrets 
 
Complete the following steps before attempting to rotate FTP account secrets: 
 
### Step 1: Inventory your FTP accounts 
 
Identify all FTP accounts that are receiving data for Data Feeds or Data Warehouse. This information is shown in your FTP configuration settings, as described in the [Legacy account types](/help/components/locations/configure-import-accounts.md#configure-a-location-account) section of the article [Configure cloud import and export accounts](/help/components/locations/configure-import-accounts.md). 
 
For each account, gather the following information: 
 
* **Host**: The FTP destination of the host your account connects to (for example, `ftp.omniture.com`, `ftp2.omniture.com`, and so forth). 
 
* **Port**: SFTP clients connect on port 22. FTP connections that are non-secure use port 21. 
 
* **Username**: The username used to log in to the FTP site. 
 
* **location account secret**: The current account secret for the account. This is the account secret (password) that you use currently when downloading data delivered to your FTP location. This information is not available from the Adobe Analytics interface. 
 
 
### Step 2: Confirm that you can update credentials in your tools 
 
Make sure you can update the FTP account secret in whatever tool or script you use to connect to the FTP site (for example, an FTP client, automated script, or third-party platform). 
 
### Step 3: Create FTP cloud location accounts with your current credentials 
 
Create new FTP cloud location accounts to replace your existing FTP location accounts. These new accounts will be used as the destination for your Data Feeds and Data Warehouse deliveries.  
 
When creating the new FTP accounts, you must use the same hostname, username, and account secret that are used in your existing FTP accounts. 
 
#### Create each FTP account 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 
 
1. Select the **Location accounts** tab. 
 
1. Select **Add account**. 
 
1. In the **Account type** drop-down field, select **FTP (legacy)**. 
 
1. Complete the following fields: 

   | Field name | Function |
   |---------|----------|
   | **Hostname** |  Your Adobe FTP hostname (for example, `ftp.omniture.com`). | 
   | **Port** | SFTP clients connect on port 22. FTP connections that are non-secure use port 21. | 
   | **Username** | Your current FTP username. |
   | **Location account secret** | Your current FTP account secrets (password).  |
 
1. Select **Save**. 
 
Repeat this process for each FTP account. 
 
For detailed instructions, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts). 
 
#### Add a location within the account 
 
1. On the **Locations** tab, select **Add location**. 
 
1. Specify a name, description, and whether this location will be used with Data Feeds or Data Warehouse. 
 
1. In the [!UICONTROL **Location account**] field, select the account you just created. 
 
1. In the [!UICONTROL **Directory path**] field, specify the path to the directory on the FTP server. Folders must already exist; feeds throw an error if the specified path does not exist. For example, `/folder_name/folder_name`. 
 
1. Select **Save**. 
 
Repeat this process for each location. 
 
For detailed instructions, see [Configure cloud import and export locations](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-locations). 
 
### Step 4: Reference the new FTP cloud accounts from any scheduled Data Feeds and Data Warehouse requests 
 
Update any existing scheduled Data Feeds and Data Warehouse requests to use the FTP cloud accounts you created.  
 
* **Data Feeds**: Go to **Admin** > **Data Feeds**, edit each scheduled  Data Feed that uses an FTP account, then change the destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit a data feed](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md). 
 
* **Data Warehouse**: Go to **Tools** > **Data Warehouse**, edit each scheduled Data Warehouse request that uses an FTP account, then change the report destination to the newly created FTP cloud account. 
 
  For detailed instructions, see [Edit requests](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) in [Manage Data Warehouse requests](/help/export/data-warehouse/data-warehouse-requests-manage.md). 
 
### Step 5: Ensure that scheduled Data Feeds and Data Warehouse requests are being delivered correctly. 
 
After updating each existing Data Feed and Data Warehouse request to use the new FTP account and location, wait for the next scheduled delivery. Verify that data arrives at the new destination as expected. 

## Request a new account secret 
 
>[!IMPORTANT] 
>
>Before requesting a new account secret, consider the following:
>
>* The steps in this section apply only if you are using an Adobe-provided FTP account. For example, the FTP hostname is `ftp.omniture.com`, `ftp2.omniture.com` or similar.   If your FTP hostname is not provided by Adobe, please contact your FTP host provider for details on changing the account secret.
> 
>* Request a new account secret only after you complete all the preparation steps described in [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets). 
>
>* After Adobe Customer Care or your third-party FTP host provider provides a new account secret, the old account secret is immediately invalidated. There is no way to revert to the previous account secret. 
>
 
To request a new account secret from Adobe: 
 
1. Contact Adobe Customer Care. 
 
1. For each FTP account, provide the **Hostname** and **Username** for each account that needs a new account secret. 
 
   Customer Care will generate a new account secret for each FTP account. 

1. Continue immediately with the following section, [After you receive the new account secret](#after-you-receive-the-new-account-secret).
 
## After you receive the new account secret 
 
Act immediately after receiving the new credentials. Any delay results in failed deliveries for active Data Feeds and Data Warehouse requests. 
 
### Step 1: Update your tools and scripts 
 
Update the FTP account secret in any tool, script, or automated process that connects to the FTP account. Make sure all team members and third-party partners who access the account are notified. 
 
### Step 2: Update your cloud location accounts 
 
1. In Adobe Analytics, go to **Components** > **Locations**. 

1. Select the **Location accounts** tab. 

1. Find the FTP account that you created in Step 3 of section, [Prepare to rotate account secrets](#prepare-to-rotate-account-secrets).

1. Select **Edit details**. 

1. Enter the new account secret and confirm it. 

1. Select **Save**. 
 
Repeat this process for each account that was reset. 

For more detailed information about this process, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).
 
### Step 3: Test your connections 
 
Verify that your Data Feeds or Data Warehouse requests that use the FTP account are working correctly with the new account secret. 
 
>[!TIP] 
> 
>If your current tools use SFTP with SSH keys that haven't been recently rotated, consider rotating those keys as well.

 
## Troubleshooting 
 
If something goes wrong after the account secret is rotated and you cannot restore connectivity, you can create a new FTP account. After the new account is set up, point your Data Feed or Data Warehouse request to the new account and update your cloud location accordingly. 

For information about how to create an FTP account, see [Configure cloud import and export accounts](https://experienceleague.adobe.com/en/docs/analytics/components/locations/configure-import-accounts).

To set up secure transfer with your FTP server: 

1. Generate a public/private key pair to use for secure transfer.

   This process differs depending on whether your FTP server is Adobe-hosted or self-hosted:

   +++ For an Adobe-hosted FTP server:

   Generate a public/private key pair: 
   
      * **In a Linux environment**: Run the following command to generate the ed25519 key pair: 

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        If your policy does not allow you to use ed25519 keys, run the following command to generate the RSA key pair (**Note:** The RSA key typically applies to customers who operate under FIPS 186-4, as ed25519 is first supported in the newer FIPS 186-5):

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

      * **In a Windows environment**: Use PuTTYgen.

   +++

   +++ For a self-hosted FTP server: 
   
   If you want to set up secure transfer with your own FTP server, you must have an SFTP hostname, username, and SFTP account within Adobe Analytics that contains a valid RSA or ed25519 public key from Adobe. This key must be installed on your SFTP server. You download this public key as part of the process of [creating the SFTP account](#create-the-sftp-account).

   +++

1. Create a file named [!DNL `authorized_keys`] (no extension).



3 basic steps: Set up SFTP on customer side, then on Adobe side, then change passphrase. 

1. FTP site: ftp.omniture.com - Using username/password to connect. Adobe uses the same username/password to connect to the site.

2. user can then upload their public key to that server, then start connecting to that server with their private key using SFTP. (They also need to open Port 22 in the firewall and they would close the other ports they don't need.)

3. In Locations, create a new location, use the same username. 

4. After they create that location, we give them our public key, and they have to install it on their SFTP server.

5. Then they switch all their data feeds to use the new Location. And then we'll use SFTP to send the data. 

6. Then they call Customer Care to get new passphrase (rotate passphrase), and then they change the passphrase on their side. Passphrase is only used if SSH fails (they have the wrong keys--a bad actor could use bad keys and then use the password. But they don't have to coordinate the switching of the passphrase with installation of SFTP. )


If they're using a third-party to do this, the third-party would need to set up SFTP - This is the same as we have documented right now. It doesn't have to be immediate, though, like we were assuming before. 


If it's they're own FTP site, it would be the same. They would need to start using SFTP with their FTP server, then get our public key and install it on their server. Shouldn't matter if the FTP site is hosted by Adobe or not. 

-->

