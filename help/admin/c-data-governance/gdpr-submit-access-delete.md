---
description: 'null'
seo-description: 'null'
seo-title: Envío de solicitudes de acceso y eliminación
title: Envío de solicitudes de acceso y eliminación
uuid: d 006 cd 5 c-e 3 cd -4385-8683-acaf 73 cb 681 b
translation-type: tm+mt
source-git-commit: 5d678322934033ad4d04750f59cf305cab512647

---


# Envío de solicitudes de acceso y eliminación


## Información general {#section_BD70882995894C1CA19C205C49FEC23C}

Si sus clientes (consumidores o interesados) desean saber qué datos almacena sobre ellos o deciden que desean que estos se eliminen de sus propiedades de Analytics, usted como responsable del tratamiento de datos debe encargarse de tratar dichas solicitudes. El responsable del tratamiento de datos determina cómo interactuará la organización con los interesados (por ejemplo, mediante un portal de usuario para ellos) y gestiona las interacciones con cada interesado. El responsable del tratamiento de datos también se encarga de cerrar el proceso con el interesado cuando se satisfaga la solicitud. Dicho de otro modo, Adobe Experience Cloud, como encargado del tratamiento de datos, no aceptará solicitudes directamente de interesados ni les devolverá datos directamente. Adobe recibirá solicitudes suyas y únicamente le devolverá datos a usted, el responsable del tratamiento de datos.

También debería garantizar que sus aplicaciones móviles y sitios web tengan avisos emergentes relevantes y materiales de apoyo sobre los derechos de los interesados en lo relativo a sus datos directa o indirectamente identificables y a otros datos que recopile.

## Gestión del consentimiento de los clientes {#section_3012015E7E8942519FB9279CF7057EAB}

Usted, como responsable del tratamiento de datos, es el responsable de obtener un consentimiento explícito por parte de sus interesados antes de recopilar datos sobre los mismos (que posiblemente incluyan datos de Adobe Analytics) y de [implementar un mecanismo de desistimiento](https://marketing.adobe.com/resources/help/en_US/dtm/opt-in.html) en su sitio web. Esto permite que sus interesados queden excluidos de la recopilación de datos futura de Adobe Experience Cloud.

## Validación de usuarios y sus datos {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

Usted, como responsable del tratamiento de datos, se encarga de verificar que el interesado sea quien dice ser y que tenga derechos sobre los datos que solicita. Además, es su responsabilidad garantizar que se devuelvan los datos correctos al interesado y que no reciba por accidente datos de otros interesados.

Para ello, debe revisar los datos que devuelva Adobe Analytics como parte de una solicitud de acceso de RGPD antes de remitírselos al interesado. Se debe prestar atención especial si se usan ID de persona y se devuelven no solo datos en los que esté presente un ID concreto, sino también datos de otras visitas en un dispositivo compartido en el que ese ID estaba presente algunas veces ([expansión de ID](../../admin/c-data-governance/gdpr-analytics-ids.md#section_D55C0722BC834118BE6F958C30AD5913)).

Cada archivo combina los datos de todos sus grupos de informes y se eliminan automáticamente las copias adicionales de las visitas replicadas. Puede decidir cuál de estos archivos quiere devolver al interesado. O puede extraer algunos de estos datos y combinarlos con datos de otros sistemas antes de devolvérselos al interesado.

## Envío de solicitudes {#section_F70F4D91B7FF4242876338A66D2125C3}

Puede enviar las solicitudes de acceso y eliminación del RGPD mediante nuestro [portal de interfaz del RGPD](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) o a través de la [API RGPD](https://www.adobe.io/apis/experienceplatform/gdpr.html).

>[!NOTE]
>
>La API GDPR admite envíos por lotes para varios usuarios en una única solicitud. El limite admitido actual es de 1000 usuarios independientes (pueden tener múltiples ID por usuario) en un único archivo JSON de solicitud.

## Ejemplos de solicitudes de JSON {#section_DB9DE6492FE740918F91D413E7BAB88F}

A continuación tiene un JSON que podría enviarse mediante la API o la interfaz del RGPD con el fin de solicitar el procesamiento de RGPD para tres usuarios.

```
{ 
    "companyContexts": [ 
        { 
            "namespace": "imsOrgID", 
            "value": "5D7236525AA6D9580A495C6C@AdobeOrg" 
        } 
    ], 
    "users": [ 
        { 
            "key": "GDPR-1234", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "AAID", 
                    "namespaceId", 10, 
                    "type": "standard", 
                    "description": "Legacy Visitor ID", 
                    "value": "2D783E5885312539-4000010360000181", 
                } 
            ] 
        }, 
        { 
            "key": "GDPR-1235", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "ECID", 
                    "namespaceId": 4, 
                    "type": "standard", 
                    "description": "This is the ID generated by the Adobe ID service.", 
                    "value": "22470866493385587460528148368265592748", 
                } 
            ] 
        }, 
        { 
            "key": "GDPR-1236", 
            "action": ["access","delete"], 
            "userIDs": [ 
                { 
                    "namespace": "CRM-ID", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar17 in some report suites", 
                    "value": "ACME-12345678", 
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com", 
                } 
            ] 
        } 
    ], 
    "expandIds": true 
} 
```

Tenga en cuenta que existen tres bloques en la sección del usuario que representan tres solicitudes independientes, posiblemente de tres interesados diferentes.

* La primera solicitud es una solicitud de acceso que utiliza un ID de cookie tradicional de Adobe Analytics (AAID).
* La segunda solicitud también es de acceso, pero utiliza una cookie de MCID/ECID.
* La tercera solicitud solicita tanto el acceso como la eliminación de los ID especificados. Mientras que la expansión del ID se especifica para todas las solicitudes, tendrá un mayor impacto en esta tercera solicitud, ya que es la única que utiliza ID sin cookies. Como resultado, esta solicitud también descubrirá los ID de cookie asociados a cualquier dispositivo con el CRM-ID o la dirección de correo electrónico especificados y expandirá la solicitud para incluir también dichos ID.

Tenga en cuenta lo siguiente:

* El valor “5D7236525AA6D9580A495C6C@AdobeOrg” en la sección “companyContexts” debe actualizarse con el valor de su propia organización de Experience Cloud.
* Los campos “type” y “namespace” se describen de forma más detallada en la sección [Espacios de nombres](../../admin/c-data-governance/gdpr-namespaces.md#concept_26C6392D92194BC1BA3986A144AF285D).
* Los campos “descripción” se ignoran.
* Los campos “key” pueden contener cualquier valor que desee. Si tiene un ID interno que utilice para realizar el seguimiento de las solicitudes de RGPD, podría colocar ese valor aquí para facilitar las solicitudes de coincidencia en el sistema de Adobe con los de sus propios sistemas.

## Detalles de respuesta {#section_93F554F65DBB48A18B75EB5784056C96}

Esta sección incluye detalles acerca de las respuestas de acceso y eliminación.

**Detalles de respuesta de acceso**

Los datos devueltos en respuesta a una solicitud de acceso le proporcionan, como responsable del tratamiento de datos, una URL que puede usar para descargar un archivo ZIP con un directorio para cada producto de Adobe que posea. En la carpeta de Analytics puede encontrar lo siguiente:

* Archivos personales: Derivados de visitas que contienen una etiqueta ID-PERSON coincidente

   * Un archivo CSV con una fila por cada visita coincidente y una columna para cada campo con una etiqueta ACC-ALL o ACC-PERSON, ordenadas por marca de fecha.
   * Archivo de resumen en HTML con una entrada por cada etiqueta ACC-ALL o ACC-PERSON. Cada entrada enumera todos los valores únicos para ese campo y el número de veces que se produjo cada uno. Los campos que contienen marcadores de tiempo se redondean para especificar solo días únicos.

* Archivos de dispositivo - Derivados de visitas individuales en las que uno de los campos coincide con un ID de ID especificado pero ninguno coincide con una ID específica

   * Un archivo CSV con una fila por cada visita coincidente y una columna para cada campo con una etiqueta ACC-ALL, ordenadas por marca de fecha.
   * Archivo de resumen en HTML con una entrada por cada etiqueta ACC-ALL. Cada entrada enumerará todos los valores únicos para ese campo y el número de veces que se produjo cada uno. Los campos que contienen marcadores de tiempo se redondean para especificar solo días únicos.

Cada archivo combina los datos de todos sus grupos de informes y se eliminan automáticamente las copias adicionales de las visitas replicadas. 

Puede decidir cuál de ellos quiere devolver al interesado. O puede extraer algunos de estos datos y combinarlos con datos de otros sistemas antes de devolvérselos al interesado.

**Detalles de respuesta de eliminación**

No se devuelve ningún dato para las solicitudes de eliminación, solo un estado a la API de RGPD que confirma que la solicitud se completó satisfactoriamente.

## Prueba de procesamiento de RGPD en los datos {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

Normalmente, los clientes de Analytics configuran algunos grupos de informes de prueba para verificar la funcionalidad antes de que se publique al público general. Las aplicaciones o los sitios web de preproducción enviarán datos a estos grupos de informes de prueba/desarrollo/control de calidad para evaluar cómo funcionará todo cuando el código se publique antes de que el tráfico real se envíe a los grupos de informes de producción.

Sin embargo, con una configuración normal, el procesamiento de solicitudes de RGPD no se puede probar primero en estos grupos de informes de prueba antes de aplicar solicitudes a los grupos de informes de producción. El motivo es que una solicitud amparada en el RGPD se aplica automáticamente a todos los grupos de informes de la organización de Experience Cloud, que a menudo son todos los grupos de informes de su empresa.

Hay varias maneras de probar el procesamiento de RGPD antes de aplicarlo a todos los grupos de informes:

* Una opción consiste en configurar una organización de Experience Cloud independiente que solo contenga grupos de informes de prueba. A continuación, utilice esta organización de Experience Cloud para sus pruebas de RGPD y su organización normal de Experience Cloud para el procesamiento real de RGPD.
* Otra opción consiste en asignar diferentes espacios de nombres a los ID en los grupos de informes de prueba, frente a los de los grupos de informes de producción.

   Por ejemplo, puede codificar cada espacio de nombres con "qa-" en los grupos de informes de prueba. Al enviar solicitudes de RGPD con solo espacios de nombres con el prefijo qa, estas solicitudes se ejecutarán únicamente en los grupos de informes de prueba. Más adelante, cuando envíe solicitudes sin el prefijo qa, se aplicarán a los grupos de informes de producción. **Es el método recomendado, a menos que utilice los espacios de nombres visitorId, AAID, ECID o customVisitorId, ya que estos son fijos y no puede especificar nombres alternativos en los grupos de informes de prueba**.
