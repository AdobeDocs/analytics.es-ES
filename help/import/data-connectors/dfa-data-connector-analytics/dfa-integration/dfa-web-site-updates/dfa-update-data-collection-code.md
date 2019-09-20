---
description: La integración de Genesis para DFA aprovecha el ID de configuración de Floodlight DFA (dfa_SPOTID), que mejora la coherencia de informes entre el sistema de recopilación de datos de Adobe y DFA.
keywords: DFA
seo-description: La integración de Genesis para DFA aprovecha el ID de configuración de Floodlight DFA (dfa_SPOTID), que mejora la coherencia de informes entre el sistema de recopilación de datos de Adobe y DFA.
seo-title: Actualizar el código de la recopilación de datos de su sitio web
solution: Analytics
title: Actualizar el código de la recopilación de datos de su sitio web
topic: Data Connectors
uuid: a97d1b62-f883-48b1-9516-4f889e701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Actualizar el código de la recopilación de datos de su sitio web{#update-your-web-site-s-data-collection-code}

La integración de Genesis para DFA aprovecha el ID de configuración de Floodlight DFA (dfa_SPOTID), que mejora la coherencia de informes entre el sistema de recopilación de datos de Adobe y DFA.

>[!NOTE]
>
>El término Spotlight se cambió a Floodlight en una reciente versión de DFA de Google. El parámetro JavaScript `dfa_SPOTID` recibió su nombre por la terminología de Spotlight pero se usa para ambas versiones.

Para habilitar la integración de DFA en su sitio web, debe actualizar su código de recopilación de datos JavaScript. Para ello, agregue lo siguiente:

* Módulo Integrate para DFA
* Adición al código de la recopilación

## Módulo Integrate para DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

The DFA integration leverages the Adobe Experience Cloud Integrate Module, which adds functionality to your core JavaScript data collection code ( `s_code.js`). El módulo Integrate se incluye como parte del archivo .zip cuando se descarga el código de AppMeasurement para Javascript desde el Administrador [de códigos](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html). Póngase en contacto con su consultor de Adobe solo si necesita ayuda adicional para encontrarla.

Insert the Integrate Module code in the `Modules` section of your website's `s_code.js` file.

## Adición al código de la recopilación {#section-8f98c727f1ba414fb8b4f02d696b8791}

Según las selecciones al activar la integración de DFA en el Asistente para integración, Data Connectors generan y le envían un correo electrónico con una adición personalizada a su código de recopilación de datos JavaScript. Inserte este código en la sección principal del archivo `s_code.js` (no en la función `doPlugins` u otra función).

El código de muestra aparece a continuación con fines ilustrativos únicamente; use el código que recibió por correo electrónico después de completar el Asistente para integración de Data Connectors.

El código de recopilación está formado por los siguientes componentes:

* Ajustes de Integrate de DFA
* Complementos requeridos por la integración

**Ajustes de Integrate de DFA**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

El bloque Ajustes de Integrate de DFA establece variables requeridas por la integración de DFA. Los valores para cada una de estas variables provienen de las siguientes fuentes:

**CSID**: ID del cliente. Generado por DFA una vez que usted completa el Asistente para integración. Data Connectors rellena previamente esta variable con el ID CS de DFA, y también le envía este valor en el correo electrónico de configuración una vez que completa el Asistente para integración. Esta variable no se requiere si el Servicio de publicidad avanzado está habilitado en su cuenta.

**SPOTID**: configuración de Floodlight (antes denominado ID de Spotlight). Data Connectors rellena previamente esta variable con el ID de configuración de Floodlight DFA según la información de cuenta DFA especificada en el Asistente para integración.

**tEvar**: variable de transferencia. Data Connectors rellena previamente esta variable con el nombre de la variable de Analytics que especificó para la variable de Visualización en el Asistente para integración. No cambie este valor sin coordinar cuidadosamente con los servicios o el departamento de ingeniería de Adobe.

**errorEvar**: variable de error. Data Connectors rellena previamente esta variable con el nombre de la variable de Analytics que especificó para la variable de Error en consulta DFA en el Asistente de integración.

**timeoutEvent**: evento de tiempo de espera. Data Connectors rellena previamente esta variable con el nombre de la variable de Analytics que especificó para la variable de Evento de tiempo de espera en el Asistente para integración.

**requestURL**: el host de DFA remoto para realizar una consulta para información de anuncio. No cambie este valor a menos que Adobe se lo indique.

**maxDelay**: especifica el tiempo durante el cual el código de recopilación de datos JavaScript espera una respuesta del servidor de Floodlight DFA, en milisegundos. Adobe recomienda experimentar con este valor para hallar el valor óptimo según el tráfico del sitio. Por ejemplo, al incrementar este valor, generalmente se recopilan más datos de DFA, pero también se incrementa el riesgo de perder datos de visitantes base si el visitante deja el sitio durante el período de demora. Al reducir este valor, baja el riesgo de perder datos de visitas, pero se puede reducir la cantidad de datos de DFA que se envían con los datos de visitas de Adobe.

**visitCookie**: el nombre de la cookie que se usa para restringir llamadas de DFA a una sola por visita.

**clickThroughParam**: un parámetro de consulta, generalmente incluido en todos los anuncios, que notifica al módulo Integrate de que acaba de ocurrir un clic. La presencia de este parámetro en la cadena de consulta hace que la solicitud ocurra en los servidores de Floodlight DFA independientemente de que el visitante ya hubiera sido consultado en los últimos 30 minutos.

**newRsidsProp**: (opcional) asignada a una variable de propiedad de Tráfico sin usar. La integración de DFA recopila y almacena este valor en la cookie de visita para identificar los grupos de informes que recopilaron datos para una visitante particular. Esta propiedad solo es necesaria con implementaciones personalizadas con los servicios de ingeniería de Adobe.

**Complementos requeridos por la integración**

La adición de Código de recopilación incorpora complementos adicionales que mejoran la operación de la integración DFA:

* Limita las consultas DFA a una vez por cada visita.
* Proporciona flexibilidad con el nombre de cookie. Aunque la mayoría de las organizaciones usan s_dfa, puede usar cualquier nombre de cookie válido para la integración de DFA.
* Elimina los redireccionamientos innecesarios. Dado que los datos de visualización se recopilan en tiempo real, los servidores de recopilación de Adobe y DFA podría intercambiar datos en todas las vistas de páginas. El complemento bloquea estos intercambios de datos cuando la información no es necesaria.

>[!CAUTION]
>
>Uno de los mecanismos que utiliza el complemento para eliminar consultas de DFA innecesarias es una cookie de visita basada en dominio. Un grupo de informes de integración que abarca varios dominios infla datos de clic y visualización cuando los visitantes abarcan varios dominios después de una visualización o pulsación influenciada por DFA.

