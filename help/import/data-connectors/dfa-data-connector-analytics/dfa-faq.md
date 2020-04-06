---
description: nulo
keywords: DFA
title: Preguntas frecuentes
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Preguntas frecuentes {#frequently-asked-questions}

## ¿Por qué el asistente de Data Connectors no acepta mis credenciales de inicio de sesión? {#section-f019b3de18774df3954af7881aa564fa}

Si ha comprobado que las credenciales de inicio de sesión son válidas, compruebe a continuación que el nombre de usuario proporcionado a la integración esté habilitado para el acceso a la API. El asistente de Data Connectors utiliza la API de DFA para validar las credenciales de inicio de sesión, así como para desactivar y activar la configuración específica de Adobe en la API de DFA. Acceso a API es una configuración que un administrador debe activar desde la interfaz de DFA. A continuación, asegúrese de que tiene permiso para acceder al ID del anunciante o al ID de configuración de Floodlight seleccionado en el asistente.

## ¿Por qué no veo ningún dato de métricas cargadas por la noche (Impresiones de DFA, Clics de DFA, etc.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Si utiliza la versión 1.5 de la integración, esto puede deberse a que la integración aún no se ha asignado a un ID de sitio de cliente. Se requiere un ID del sitio del cliente (CSID) para que se produzca el intercambio nocturno y para solicitar datos del servidor de publicidad DFA. Los CSID pueden tardar hasta 3 días desde la fecha de integración para intercambiarse con Google. Una vez que el CSID se haya recibido desde Google, se le notificará el nuevo CSID mediante la dirección de correo electrónico de la integración, junto con el código JavaScript más reciente.

Si ha transcurrido más de 3 días y no ha recibido el correo electrónico de configuración y las métricas no fluyen, el problema más probable es que el CSID ya se haya asignado a otra integración. Google mantiene una asignación individual entre CSID y Grupo de informes, lo que significa que si una integración en un grupo de informes usa el mismo ID del anunciante que otra integración en otro grupo de informes, solo se asignará un CSID a la primera. Para cambiar a qué grupo de informes o ID del anunciante está asignado el CSID, se debe abrir una incidencia con el Soporte técnico de Google.

Por ejemplo, supongamos que existe una integración en el grupo de informes A con la ID del anunciante Z que se asigna a un CSID. Si posteriormente se configura otra integración en el grupo de informes B con el anunciante Z, esta integración más reciente NO se reasignará al CSID. Esto requeriría un ticket para Google. Por otro lado, tomemos el ejemplo de una integración en el grupo de informes A, con la ID del anunciante Z y, más adelante, otra integración en el grupo de informes A, el anunciante Z está configurado. Sólo la primera integración recibirá datos para la integración; sin embargo, en este caso, la primera integración se puede desactivar y los datos fluirán a la segunda integración.

>[!NOTE] Los CSID no se usan en la versión 2.0 de la integración y por lo tanto no se aplica el proceso de negociación de CSID.

## Estoy usando la versión 2.0 de la integración y las métricas de costo no aparecen en mis anuncios de DFA. ¿A qué podría deberse? {#section-805748111bbe4bbf918d6dbbb2641fff}

Las métricas de costo deben activarse desde el lado DFA de Google y suministrarse en la interfaz DFA, así como también activarse en el asistente de Data Connectors. El primer lugar para comprobar es que ha asignado un evento de Analytics para el costo de medios de DFA y ha proporcionado un código de moneda. Si ha asignado el evento Coste de medios y finaliza y guarda el asistente, el indicador omnitureCostData de DFA se activará en la API de DFA. Esto indicará a Google que las métricas deben enviarse en el archivo por la noche. Puede comprobar por doble mediante la interfaz de DFA que omnitureCostData está habilitado mirando las propiedades en Floodlight integrado. Finalmente, después de comprobar estos dos lugares, asegúrese de que las publicidades que forman parte de Floodlight integrado especifican los datos de costo y las estructuras de costo. Si no se proporcionan datos de costo en la interfaz de DFA, no aparecerán en Analytics.

## ¿Por qué ciertos anuncios no muestran Impresiones o visualizaciones de DFA pero sí muestran clics y proporción de clics? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Hay algunas publicidades que solo registran datos de clics, llamadas rastreadores de clics. Este tipo de publicidades no devuelven datos de la última impresión cuando se consulta el servidor de Floodlight. Para verificar si una determinada publicidad es un rastreador de clics o una publicidad de sólo clic, comuníquese con la agencia de DFA o con el representante de asistencia de Google.

## ¿Por qué no existe la proporción de clics para anuncios que muestran clics de DFA? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Puede haber una de muchas respuestas a esto.

En primer lugar, compruebe que el anuncio en cuestión tenga una dirección URL de la página de aterrizaje que esté (a) etiquetada con código de Adobe para el mismo grupo de informes en el que está viendo la discrepancia y (b) contenga el parámetro de cadena de consulta *`clickThroughParam`*.

En segundo lugar, compruebe que dispone de una integración que funciona siguiendo los pasos que se indican en [Confirmar una integración DFA correcta](../dfa-data-connector-analytics/dfa-integration.md). Si ve que hay código de seguimiento DFA que viene con la visita de Adobe en la página de aterrizaje, debería ver que ese clic viene en el informe de campañas DFA. Si no ve que esto suceda, verifique que los grupos de informes coincidan entre la variable de la página de aterrizaje *`s.account`* y el grupo de informes que se está viendo en Reports &amp; Analytics. Si coinciden, compruebe si hay códigos de seguimiento en el informe de Vista a través de eVar que tengan un aspecto similar a DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX:XXX.

Indican errores de la regla de VISTA de DFA para compender los datos sin procesar de DFA. Este problema se puede solucionar abriendo un ticket de asistencia técnica a través de su representante de cuentas de Adobe.

Si ninguna de las soluciones anteriores explica el problema, consulte [Reconciliación de discrepancias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) para explorar otras posibilidades.
