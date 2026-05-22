---
title: Requisitos de seguridad para servidores FTP y SFTP
description: Obtenga información acerca de los requisitos de seguridad para servidores FTP y SFTP.
feature: Data Configuration and Collection
role: Admin
TQID: 'https://experienceleague.adobe.com/qbBCeUihfvRTQm7LvR8jylRWf8rRlzFoZfs62l0fito'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 1933
ht-degree: 100%

---

# Requisitos de seguridad para servidores FTP y SFTP

Esta página cubre los requisitos de seguridad para los servidores FTP y SFTP existentes que reciben datos suministrados por fuentes de datos de Adobe Analytics o por Data Warehouse.

* **Servidores FTP existentes**: se deben actualizar para usar SFTP, como se describe en la sección siguiente, [Actualizar servidores FTP para usar SFTP](#upgrade-ftp-servers-to-use-sftp).

  La actualización de FTP a SFTP es un requisito, ya que SFTP ofrece una mayor seguridad.

  Como alternativa, para un nivel más alto de seguridad, puede realizar la transición a un destino en la nube moderno. (Para obtener más información, consulte [Configurar cuentas de importación y exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-accounts).)

* **Servidores SFTP existentes (y servidores SFTP recién actualizados)**: debe rotar las contraseñas antiguas, tal como se describe en la sección siguiente, [Rotar la contraseña SFTP](#rotate-your-sftp-password).

  La rotación periódica de la contraseña del SFTP es una práctica recomendada de seguridad que ayuda a proteger los datos.

>[!IMPORTANT]
>
>Tenga en cuenta las siguientes situaciones antes de completar los pasos de este artículo.
>
>* **Adobe recomienda realizar la transición a un destino en la nube moderno en lugar de actualizar a SFTP, en la medida de lo posible.**
>FTP y SFTP son tipos de destino heredados. En lugar de actualizar las cuentas de FTP a SFTP y rotar las contraseñas SFTP como se describe en este artículo, Adobe recomienda pasar a un tipo de destino en la nube moderno (como Amazon S3, Google Cloud Platform o Azure). Estos destinos en la nube proporcionan un nivel más alto de seguridad. Para obtener más información, consulte [Configuración de las cuentas de importación y exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-accounts).
>
>* **Si las cuentas FTP y SFTP se usan exclusivamente para clasificaciones, migre a los conjuntos de clasificaciones.**
>Si su cuenta FTP o SFTP se usa exclusivamente para clasificaciones, debería migrar del **importador de clasificaciones** a **Conjuntos de clasificaciones**, en lugar de actualizar las cuentas FTP a SFTP y rotar las contraseñas SFTP como se describe en este artículo. El importador de clasificaciones quedará obsoleto y dejará de ser accesible después del **31 de agosto de 2026**. Para obtener más información, consulte [Información general de los conjuntos de clasificaciones](https://experienceleague.adobe.com/es/docs/analytics/components/classifications/sets/overview).

## Requisitos previos

### Realizar un inventario de cuentas de FTP

Debe completar los pasos de actualización de SFTP en esta página para todos los sitios FTP utilizados con fuentes de datos o Data Warehouse.

Como tal, debe identificar todas las cuentas de FTP que reciban datos para fuentes de datos o Data Warehouse. Esta información se muestra en los ajustes de configuración de FTP, tal como se describe en la sección [Tipos de cuentas heredadas](/help/components/locations/configure-import-accounts.md#configure-a-location-account) del artículo [Configurar cuentas de importación y exportación en la nube](/help/components/locations/configure-import-accounts.md).

Para cada cuenta, recopile la siguiente información:

* **Host**: el nombre de host del servidor FTP al que se conecta su cuenta (por ejemplo, `ftp.omniture.com`, `ftp2.omniture.com`, etc.).

* **Puerto**: cuando se usa un servidor SFTP alojado en Adobe, los clientes SFTP se conectan al puerto 22. Las conexiones FTP no seguras utilizan el puerto 21.

* **Nombre de usuario**: nombre de usuario que se utiliza para iniciar sesión en el sitio FTP.

* **Secreto de cuenta de ubicación**: el secreto de cuenta actual de la cuenta. Este es el secreto de cuenta (contraseña) que se utiliza actualmente para descargar datos enviados a su ubicación FTP. Esta información no está disponible en la interfaz de Adobe Analytics.

### Confirme que puede actualizar las credenciales en las herramientas

Asegúrese de que puede actualizar las contraseñas SFTP en cualquier herramienta o script que utilice para conectarse al sitio SFTP (por ejemplo, un cliente SFTP, un script automatizado o una plataforma de terceros).

Todos los clientes deben conectarse mediante SFTP con una contraseña como reserva.

## Actualizar servidores FTP para utilizar SFTP

>[!IMPORTANT]
>
>Si los datos de FTP se entregan a un socio de terceros (por ejemplo, una empresa de consultoría o un proveedor de análisis), debe coordinarse con ellos antes de seguir los pasos descritos en este artículo.

### Paso 1: generar las claves SSH de su organización para descargar datos

En esta sección se describe cómo generar las claves SSH de su organización (un par de claves pública y privada) que se usan para **descargar datos** del servidor SFTP.

>[!NOTE]
>
>En un próximo paso, descargará otra clave pública proporcionada por Adobe. Esto forma parte de un segundo par de claves públicas o privadas, que Adobe usa para **cargar datos** en el servidor SFTP.

Para configurar la transferencia segura para descargar datos desde el servidor FTP:

1. Inicie sesión en la estación de trabajo donde descargue datos del servidor FTP.

1. Genere un par de claves pública o privada para utilizarlo en una transferencia segura.

   Cuando se utiliza un servidor SFTP alojado en Adobe, Adobe admite las claves RSA y ed25519.

   * **En un entorno Linux**: ejecute el siguiente comando para generar el par de claves ed25519:

     ```
     ssh-keygen -t ed25519 -C "your-comment-or-email"
     ```

     Si la política no le permite utilizar claves ed25519, ejecute el siguiente comando para generar el par de claves RSA:

     ```
     ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
     ```

   * **En un entorno Windows**: use PuTTYgen.

1. Cree un archivo con el nombre [!DNL `authorized_keys`] (sin extensión).

1. Copie el contenido de la clave pública en el archivo [!DNL `authorized_keys`].

1. En un próximo paso, volverá a este archivo de [!DNL `authorized_keys`] para añadir la clave pública de Adobe, que Adobe utiliza para cargar datos en el servidor SFTP. A continuación, añadirá el archivo [!DNL `authorized_keys`] al servidor SFTP.

### Paso 2: crear una nueva cuenta de ubicación SFTP en Adobe Analytics

Cree una nueva cuenta de ubicación SFTP para reemplazar cada cuenta existente de FTP.

Al crear una nueva cuenta de ubicación SFTP, debe utilizar el mismo nombre de host y nombre de usuario que se utilizan en la cuenta de FTP existente que está reemplazando.

>[!NOTE]
>
>En un próximo paso, configurará esta nueva cuenta de ubicación para que se utilice como destino para las fuentes de datos y las entregas de Data Warehouse.

#### Crear la cuenta SFTP

1. En Adobe Analytics, vaya a [!UICONTROL **Componentes**] > [!UICONTROL **Ubicaciones**].

1. Seleccione la pestaña [!UICONTROL **Cuentas de ubicación**].

1. Seleccione [!UICONTROL **Añadir cuenta**].

1. En el menú desplegable [!UICONTROL **Tipo de cuenta**], seleccione [!UICONTROL **SFTP (heredado)**].

1. Complete los campos siguientes:

   | Nombre de campo | Función |
   |---------|----------|
   | [!UICONTROL **Nombre de host**] | Su nombre de host SFTP (por ejemplo, `ftp.omniture.com`). |
   | [!UICONTROL **Puerto**] | El puerto del cortafuegos a través del cual se enviarán los datos. Es el puerto 22 para conexiones SFTP alojadas en Adobe. |
   | [!UICONTROL **Nombre de usuario**] | Su nombre de usuario SFTP. Utilice el mismo nombre de usuario que utilizó para su cuenta de FTP. |

1. Seleccione [!UICONTROL **Guardar**].

1. En el cuadro de diálogo [!UICONTROL **Cuenta creada**], descargue la clave pública RSA o ed25519 y, a continuación, seleccione [!UICONTROL **Aceptar**]. Es la clave pública SSH que utiliza Adobe para cargar datos en el servidor SFTP. (Utilizará esta clave en la siguiente sección: [Añadir la clave pública SSH de Adobe al servidor SFTP](#add-adobes-ssh-public-key-to-the-sftp-server)).

1. Repita este proceso para cada cuenta SFTP que desee crear.

1. Continúe con la sección siguiente, [Cargue la clave pública en el servidor SFTP](#upload-the-public-key-to-the-sftp-server).

#### Añada la clave pública SSH de Adobe al archivo [!DNL `authorized_keys`] y cárguela en su servidor FTP

La clave pública que descargó en el paso 7 de la sección anterior es parte de un par de claves pública o privada que Adobe usa para **cargar datos** en el servidor SFTP.

Debe añadir esta clave pública al mismo archivo [!DNL `authorized_keys`] al que añadió anteriormente la clave de descarga de su organización (la que generó en [Paso 1: generar las claves SSH de su organización para descargar datos](#step-1-generate-your-organizations-ssh-keys-for-downloading-data)).

Para añadir la clave pública SSH de Adobe al archivo [!DNL `authorized_keys`] y cargarla en el servidor FTP:

1. Inicie sesión en la estación de trabajo donde descargue datos del servidor FTP.

1. Abra el archivo [!DNL `authorized_keys`] y añada la clave de carga de Adobe. Este archivo ya debería contener la clave de descarga de su organización en [Paso 1: genere las claves SSH de su organización para descargar datos](#step-1-generate-your-organizations-ssh-keys-for-downloading-data).

1. Cargue el archivo [!DNL `authorized_keys`] al servidor FTP:

   1. Conéctese al servidor FTP e inicie sesión con su nombre de usuario y contraseña.
Puede ser un servidor FTP alojado en Adobe o su propio servidor FTP.
   1. Cree un directorio [!DNL .ssh], (si no existe todavía).
   1. Cargue el archivo [!DNL `authorized_keys`] en el directorio [!DNL .ssh].

1. Actualice la configuración del cortafuegos para permitir conexiones entrantes desde el servidor SFTP. Cuando utilice un servidor SFTP alojado en Adobe, permita las conexiones entrantes desde los intervalos de IP de Adobe en el puerto 22.

1. Pruebe la conexión iniciando sesión en el servidor mediante su cliente SFTP.

1. Repita este proceso con cada cuenta SFTP que haya creado en la sección anterior, [Crear la cuenta SFTP](#create-the-sftp-account).

1. Continúe con la sección siguiente, [Añadir una ubicación dentro de la cuenta](#add-a-location-within-the-account).

#### Añadir una ubicación dentro de la cuenta

1. En la pestaña [!UICONTROL **Ubicaciones**], seleccione [!UICONTROL **Añadir ubicación**].

1. Especifique un nombre, una descripción y si esta ubicación se utilizará con las fuentes de datos o con Data Warehouse.

1. En el campo [!UICONTROL **Cuenta de ubicación**], seleccione la cuenta que acaba de crear.

1. En el campo [!UICONTROL **Ruta de directorio**], especifique la ruta al directorio en el servidor SFTP. Las carpetas de la ruta ya deben existir; de lo contrario, se produce un error. Por ejemplo, `/folder_name/folder_name`.

1. Seleccione [!UICONTROL **Guardar**].

1. Repita este proceso para cada cuenta SFTP que haya creado.

Para obtener una información más detallada, consulte [Configurar las ubicaciones de importación y exportación en la nube](https://experienceleague.adobe.com/es/docs/analytics/components/locations/configure-import-locations).

### Paso 3: editar fuentes de datos y solicitudes de Data Warehouse para utilizar el nuevo destino SFTP

Actualice las fuentes de datos programadas y las solicitudes de Data Warehouse existentes que actualmente envían datos a destinos FTP para utilizar los nuevos destinos SFTP que haya creado.

#### Editar fuentes de datos

Edite cada fuente de datos programada configurada con el antiguo destino FTP para utilizar el nuevo destino SFTP:

1. En Adobe Analytics, seleccione [!UICONTROL **Administrador**] > [!UICONTROL **Fuentes de datos**].

1. Busque la fuente de datos que desea editar. Para localizar una fuente de datos, puede [filtrar y buscar en la lista de fuentes de datos](#filter-and-search-the-list-of-data-feeds).

1. Seleccione la fuente de datos en la columna [!UICONTROL **Nombre de fuente**].

   Se muestra la página [!UICONTROL **Editar _feed_name_**].

1. En la sección [!UICONTROL **Destino**], en el campo [!UICONTROL **Cuenta**], utilice el menú desplegable para seleccionar el nuevo destino SFTP que ha creado.

1. En el campo [!UICONTROL **Ubicación**], utilice el menú desplegable para seleccionar la ubicación en la cuenta SFTP.

1. Seleccione [!UICONTROL **Guardar**].

Para obtener información más detallada, consulte [Editar una fuente de datos](/help/export/analytics-data-feed/df-manage-feeds.md#edit-a-data-feed) en [Administrar fuentes de datos](/help/export/analytics-data-feed/df-manage-feeds.md).

#### Editar las solicitudes de Data Warehouse

Edite cada solicitud de Data Warehouse programada que esté configurada con el destino de FTP antiguo para utilizar el nuevo destino de SFTP:

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee editar.

   ![Administrar una solicitud](assets/dw-manage-request.png)

1. Seleccione [!UICONTROL **Editar**].

1. Seleccione la pestaña [!UICONTROL **Destino del informe**].

1. En el campo [!UICONTROL **Cuenta**], utilice el menú desplegable para seleccionar el nuevo destino SFTP que ha creado.

1. En el campo [!UICONTROL **Ubicación**], utilice el menú desplegable para seleccionar la ubicación en la cuenta SFTP.

1. Seleccione [!UICONTROL **Guardar cambios**].

Para obtener información más detallada, consulte [Editar solicitudes](/help/export/data-warehouse/data-warehouse-requests-manage.md#edit-requests) en [Administrar solicitudes de Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

### Paso 4: actualizar la configuración del cortafuegos

Si aún no lo ha hecho, debe actualizar la configuración del cortafuegos de la siguiente manera:

* **Al usar los servidores FTP de Adobe**: debe actualizar la configuración del cortafuegos para permitir conexiones **salientes** en el puerto 22.

* **Al usar su propio servidor FTP**: debe actualizar la configuración del cortafuegos para permitir la conexión **entrante** en cualquier puerto en el que aloje el servicio, que suele ser el puerto 22.

También debe eliminar las reglas antiguas específicas del FTP, como permitir conexiones entrantes en el puerto 21. (FTP utiliza el puerto 21, además de una serie de puertos adicionales para la transferencia de datos. Como práctica recomendada de seguridad, debería eliminar este acceso innecesario a través del cortafuegos).

### Paso 5: asegúrese de que las fuentes de datos programadas y las solicitudes de Data Warehouse se entreguen correctamente

Después de actualizar cada fuente de datos y solicitud de Data Warehouse existentes para utilizar la nueva cuenta y ubicación SFTP, espere a la siguiente entrega programada. Compruebe que los datos llegan al nuevo destino según lo esperado.

### Paso 6: rotar la contraseña en el servidor SFTP actualizado

Después de actualizar un servidor FTP a SFTP, también debe rotar la contraseña de SFTP, como se describe en la siguiente sección: [Rotar la contraseña SFTP](#rotate-your-sftp-password).

## Rotar la contraseña SFTP

Una contraseña SFTP sirve como método de autenticación de reserva si falla la autenticación basada en claves.

Rote la contraseña SFTP inmediatamente después de actualizar de FTP a SFTP. Debe seguir rotándola de manera regular, de acuerdo con las políticas establecidas.

1. Póngase en contacto con el Servicio de atención al cliente de Adobe y solicite una nueva contraseña.

1. Para cada cuenta SFTP, proporcione un **Nombre de host** y un **Nombre de usuario**.

   El Servicio de atención al cliente generará una nueva contraseña para cada cuenta de FTP.

1. Actualice la contraseña en el cliente que utilice para conectarse al servidor SFTP.


