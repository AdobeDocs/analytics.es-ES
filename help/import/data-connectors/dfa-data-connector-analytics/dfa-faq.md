---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: Preguntas frecuentes
solution: Analytics
title: Preguntas frecuentes
topic: Data Connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Preguntas frecuentes{#frequently-asked-questions}

## Why won't the Data Connectors wizard accept my login credentials? {#section-f019b3de18774df3954af7881aa564fa}

Si ha verificado que las credenciales de inicio de sesión son válidas, verifique luego que el nombre de usuario proporcionado a la integración esté habilitado para acceso de API. El asistente de Data Connectors usa la API DFA para validar credenciales de inicio de sesión, como así también desactivar los ajustes específicos de Adobe en la API DFA. Acceso a la API es un ajuste que un administrador debe activar desde la interfaz de DFA. A continuación, asegúrese de tener permiso para acceder al ID del anunciante o al ID de configuración de Floodlight seleccionada en el asistente.

## ¿Por qué no veo ningún dato de métricas cargadas por la noche (Impresiones de DFA, Clics de DFA, etc.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Si está usando la versión 1.5 de la integración, podría deberse a que la integración no se ha asignado aún a ningún ID del sitio del cliente. Se requiere un ID del sitio del cliente (CSID) para que ocurra el cambio por la noche, y para solicitar datos del servidor de publicidad de DFA. Los CSID pueden tardar hasta 3 días desde la fecha de integración para que se intercambien con Google. Una vez que el CSID se haya recibido de Google, se le notificará a través de la dirección de correo electrónico de la integración del nuevo CSID, junto con el código JavaScript más reciente.

Si ya han transcurrido más de 3 días y aún no ha recibido el correo electrónico de configuración y las métricas no están fluyendo, el problema más factible es que el CSID ya se haya asignado a otra integración. Google mantiene una asignación de 1 a 1 entre CSID y Grupo de informes, lo que significa que si una integración en un grupo de informes usa el mismo ID del anunciante que otra integración en otro grupo de informes, solo se asignará la primera de ID de CS. Para cambiar a qué grupo de informes o ID del anunciante está asignado el CSID, se debe abrir un ticket con el Soporte técnico de Google.

Por ejemplo, imaginemos que existe una integración en el Grupo de informes A con el ID del Anunciante Z al que se asigna un CSID. Si posteriormente se configura otra integración en el Grupo de informes B con el Anunciante Z, esta integración más nueva NO se reasignará al CSID. Esto requeriría un ticket de Google. Por otro lado, tomemos el ejemplo de una integración en el Grupo de informes A, con el ID del Anunciante Z, y luego otra integración en el Grupo de informes A, se configura el Anunciante Z. Solamente la primera integración recibirá datos para la integración. No obstante, en este caso, la primera integración se puede desactivar y los datos fluirán a la segunda integración.

> [!NOTE] Los CSID no se utilizan en la versión 2.0 de la integración, por lo que no se aplica el proceso de negociación de CSID.

## Estoy usando la versión 2.0 de la integración y las métricas de coste no están apareciendo para mis anuncios de DFA. ¿A qué podría deberse? {#section-805748111bbe4bbf918d6dbbb2641fff}

Las métricas de coste deben activarse desde el DFA de Google, y proporcionarse en la interfaz de DFA, así como también activarse en el asistente de Data Connectors. Lo primero que debe verificar es si ha asignado un evento de Analytics para Coste de medios de DFA y ha proporcionado un código de moneda. Si ha asignado el evento de Coste de medios y finaliza y guarda el asistente, el indicador omnitureCostData de DFA se activará en la API de DFA. Esto indicará a Google que las métricas deberían enviarse en el archivo por la noche. Puede comprobar nuevamente mediante la interfaz DFA que omnitureCostData está habilitado al mirar las propiedades en el Floodlight integrado. Finalmente, después de comprobar estos dos lugares, asegúrese de que los anuncios que forman parte del Floodlight integrado especifiquen estructuras de costes y datos de costes. Si no se proporcionan los datos de costes en la interfaz DFA, no aparecerán en Analytics.

## ¿Por qué ciertos anuncios no muestran Impresiones o visualizaciones de DFA pero sí muestran clics y pulsaciones? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Existen algunos anuncios que solo registran datos de clics, denominadas rastreadores de clics. Este tipo de anuncios no devuelven los datos de la última impresión cuando se realizó la consulta al servidor de Floodlight. Para verificar si un anuncio determinado es un rastreador de clics o si es un anuncio de clics solamente, póngase en contacto con su agencia de DFA o con su representante de Soporte técnico de Google.

## Why aren't there any click-throughs for ads that show DFA Clicks? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

La respuesta para esta pregunta pueden ser varias.

En primer lugar, compruebe que el anuncio en cuestión tenga una dirección URL de la página de aterrizaje que esté (a) etiquetada con código de Adobe para el mismo grupo de informes en el que está viendo la discrepancia y (b) contenga el parámetro de cadena de consulta *`clickThroughParam`*.

En segundo lugar, compruebe que dispone de una integración en funcionamiento siguiendo los pasos que se indican en [Confirmación de una integración](../dfa-data-connector-analytics/dfa-integration.md)DFA correcta. Si ve que hay código de seguimiento DFA que viene con la visita de Adobe en la página de aterrizaje, debería ver que esa pulsación viene en el informe de campañas DFA. Si no ve que esto suceda, verifique que los grupos de informes coincidan entre la variable de la página de aterrizaje y el grupo de informes que se está viendo en Informes y análisis. *`s.account`* Si coinciden, consulte los códigos de seguimiento en el informe de eVar de visualización que tengan un formato similar a DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX.

Indican errores de la regla DFA VISTA para resumir los datos sin procesar de DFA. Este problema se puede remediar al abrir un ticket de soporte técnico con su Representante de cuentas de Adobe.

Si ninguna de las soluciones anteriores explica el problema, consulte [Reconciliación de discrepancias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) para explorar otras posibilidades.
