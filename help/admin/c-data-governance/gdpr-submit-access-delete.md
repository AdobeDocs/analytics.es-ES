---
description: Cómo enviar solicitudes de acceso y eliminación de datos en Adobe Analytics.
title: Envío de solicitudes de acceso y eliminación
feature: Data Governance
exl-id: bb94cedf-ac9b-4d38-9136-bd3da2acf018
source-git-commit: f135138de15f3fc788e637128daeb064d0d453af
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Envío de solicitudes de acceso y eliminación

Si sus clientes (consumidores/sujetos de datos) desean saber qué datos almacena sobre ellos o deciden que desean que estos se eliminen de sus propiedades de Analytics, usted como responsable del tratamiento de datos es el responsable de responder a esas solicitudes. El controlador de datos determina cómo interactuará su organización con los sujetos de datos (por ejemplo, a través de un portal de usuario para ellos) y gestiona las interacciones con el sujeto de datos. También es responsabilidad del controlador cerrar el bucle con el sujeto de datos cuando se satisfaga la solicitud. En otras palabras, Adobe Experience Cloud, como responsable del tratamiento de datos, no aceptará solicitudes directamente de sujetos de datos ni les devolverá datos directamente. En su lugar, Adobe recibirá solicitudes de y únicamente le devolverá datos a usted como responsable del tratamiento de datos.

También es posible que desee garantizar que sus aplicaciones móviles y sitios web tengan avisos emergentes relevantes y materiales de apoyo sobre los derechos de los sujetos de datos con respecto a sus datos directa o indirectamente identificables y a otros datos que recopile.

## Gestión del consentimiento de los clientes {#section_3012015E7E8942519FB9279CF7057EAB}

Usted, como responsable del tratamiento de datos, es el responsable de obtener un consentimiento explícito por parte de sus sujetos de datos antes de recopilar datos sobre ellos (que posiblemente incluyan datos de Adobe Analytics) y de implementar una [mecanismo de exclusión](https://www.adobe.com/es/privacy/opt-out.html#customeruse) en el sitio web. Esto permite que los sujetos de datos queden excluidos de la recopilación de datos futura de Adobe Experience Cloud.

## Validación de usuarios y sus datos {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

Usted, como responsable del tratamiento de datos, es el responsable de verificar que el sujeto de datos sea quien dice ser y que tenga derecho a los datos que solicita. Además, es su responsabilidad garantizar que se devuelvan los datos correctos al sujeto de datos y que no reciba por accidente datos sobre otros sujetos de datos.

Esto incluye revisar los datos devueltos por Adobe Analytics como parte de una solicitud de acceso de privacidad de datos antes de enviarlos al sujeto de datos. Se debe prestar especial atención si se usan ID de persona y se devuelven no solo datos en los que esté presente un ID concreto, sino también datos de otras visitas en un dispositivo compartido en el que ese ID estaba presente algunas veces. Consulte [Expansión de ID.](/help/admin/c-data-governance/gdpr-id-expansion.md)

Cada archivo combina los datos de todos sus grupos de informes y se eliminan automáticamente las copias adicionales de las visitas replicadas. Puede decidir cuál de estos archivos quiere devolver al sujeto de datos. O puede extraer algunos de estos datos y combinarlos con datos de otros sistemas antes de devolvérselos al sujeto de datos.

## Envío de solicitudes {#submit-requests}

Puede enviar y eliminar solicitudes de acceso a la privacidad de datos a través de nuestra [IU de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=es) o a través de nuestra [API de Privacy Service.](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es)

>[!NOTE]
>
>La API de privacidad de datos admite los envíos en lotes para varios usuarios en una única solicitud. El limite admitido actual es de 1000 usuarios independientes (pueden tener múltiples ID por usuario) en un único archivo JSON de solicitud.

## Ejemplos de solicitudes de JSON {#sample-json-request}

A continuación tiene un JSON que podría enviarse mediante la API o la interfaz de privacidad de datos con el fin de solicitar el procesamiento de privacidad de datos para tres usuarios.

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
            "key": "Data Privacy-1234", 
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
            "key": "Data Privacy-1235", 
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
            "key": "Data Privacy-1236", 
            "action": ["access","delete"], 
            "userIDs": [ 
                { 
                    "namespace": "CRM-ID", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar17 in some report suites", 
                    "value": "ACME-12345678"
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com" 
                } 
            ] 
        } 
    ], 
    "expandIds": true 
} 
```

Tenga en cuenta que existen tres bloques en la sección del usuario que representan tres solicitudes independientes, posiblemente de tres sujetos de datos independientes.

* La primera solicitud es una solicitud de acceso que utiliza un ID de cookie tradicional de Adobe Analytics (AAID).
* La segunda solicitud también es de acceso, pero utiliza una cookie de MCID/ECID.
* La tercera solicitud solicita tanto el acceso como la eliminación de los ID especificados. Mientras que la expansión del ID se especifica para todas las solicitudes, tendrá un mayor impacto en esta tercera solicitud, ya que es la única que utiliza ID sin cookies. Como resultado, esta solicitud también descubrirá los ID de cookie asociados a cualquier dispositivo con el CRM-ID o la dirección de correo electrónico especificados y expandirá la solicitud para incluir también dichos ID.

Tenga en cuenta que

* El valor “5D7236525AA6D9580A495C6C@AdobeOrg” en la sección “companyContexts” debe actualizarse con el valor de su propia organización de Experience Cloud.
* Los campos “tipo” y “área de nombres” se describen de forma más detallada en la sección [Área de nombres](/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md).
* Los campos “descripción” se ignoran.
* Los campos “clave” pueden contener cualquier valor que desee. Si tiene un ID interno que utiliza para realizar el seguimiento de las solicitudes de privacidad de datos, puede introducir ese valor aquí para facilitar las solicitudes de coincidencia en el sistema de Adobe con los de sus propios sistemas.

## Detalles de respuesta {#section_93F554F65DBB48A18B75EB5784056C96}

Esta sección incluye detalles acerca de las respuestas de acceso y eliminación.

**Detalles de respuesta de acceso**

Los datos devueltos en respuesta a una solicitud de acceso le proporcionan, como responsable del tratamiento de datos, una URL que puede usar para descargar un archivo ZIP con un directorio para cada producto de Adobe que posea. En la carpeta de Analytics puede encontrar lo siguiente:

* Archivos de persona: Derivados de las visitas que contengan una etiqueta ID-PERSON coincidente.

   * Un archivo CSV con una fila por cada visita coincidente y una columna para cada campo con una etiqueta ACC-ALL o ACC-PERSON, ordenadas por marca de fecha.
   * Archivo de resumen en HTML con una entrada por cada etiqueta ACC-ALL o ACC-PERSON. Cada entrada enumera todos los valores únicos para ese campo y el número de veces que se produjo cada uno. Los campos que contienen marcadores de tiempo se redondean para especificar solo días únicos.

* Archivos de dispositivo: Derivados de visitas en las que uno de los campos coincide con un ID-DEVICE especificado pero ninguno coincide con un ID-PERSON especificado.

   * Un archivo CSV con una fila por cada visita coincidente y una columna para cada campo con una etiqueta ACC-ALL, ordenadas por marca de fecha.
   * Archivo de resumen en HTML con una entrada por cada etiqueta ACC-ALL. Cada entrada enumerará todos los valores únicos para ese campo y el número de veces que se produjo cada uno. Los campos que contienen marcadores de tiempo se redondean para especificar solo días únicos.

Cada archivo combina los datos de todos sus grupos de informes y se eliminan automáticamente las copias adicionales de las visitas replicadas.

Puede decidir cuál de ellos quiere devolver al sujeto de datos. O puede extraer algunos de estos datos y combinarlos con datos de otros sistemas antes de devolvérselos al sujeto de datos.

**Detalles de respuesta de eliminación**

No se devuelve ningún dato para las solicitudes de eliminación, solo un estado a la API de privacidad de datos que confirma que la solicitud se completó satisfactoriamente.

## Prueba del procesamiento de la privacidad de datos en los datos {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

Normalmente, los clientes de Analytics configuran algunos grupos de informes de prueba para verificar la funcionalidad antes de que se publique al público general. Las aplicaciones o los sitios web de preproducción enviarán datos a estos grupos de informes de prueba/desarrollo/control de calidad para evaluar cómo funcionará todo cuando el código se publique antes de que el tráfico real se envíe a los grupos de informes de producción.

Sin embargo, con una configuración normal, el procesamiento de solicitudes de RGPD no se puede probar primero en estos grupos de informes de prueba antes de aplicar solicitudes a los grupos de informes de producción. El motivo es que una solicitud amparada en la privacidad de datos se aplica automáticamente a todos los grupos de informes de la organización de Experience Cloud, que a menudo son todos los grupos de informes de su empresa.

Hay varias maneras de probar el procesamiento de privacidad de datos antes de aplicarlo a todos los grupos de informes:

* Una opción consiste en configurar una organización de Experience Cloud independiente que solo contenga grupos de informes de prueba. A continuación, utilice esta organización de Experience Cloud para sus pruebas de privacidad de datos y su organización normal de Experience Cloud para el procesamiento real de la privacidad de datos.
* Otra opción consiste en asignar diferentes áreas de nombres a los ID en los grupos de informes de prueba, frente a los de los grupos de informes de producción.

   Por ejemplo, puede utilizar el prefijo “qa-” en cada área de nombres en los grupos de informes de prueba. Al enviar solicitudes de privacidad de datos con solo áreas de nombres con el prefijo qa, estas solicitudes se ejecutarán únicamente en los grupos de informes de prueba. Más adelante, cuando envíe solicitudes sin el prefijo qa, se aplicarán a los grupos de informes de producción. **Es el método recomendado, a menos que utilice los áreas de nombres visitorId, AAID, ECID o customVisitorId, ya que estos son fijos y no puede especificar nombres alternativos en los grupos de informes de prueba**.
