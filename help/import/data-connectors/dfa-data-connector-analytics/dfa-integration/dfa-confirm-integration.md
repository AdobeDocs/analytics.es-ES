---
description: Después de haber realizado todas las actualizaciones de sitios web que se requieran, puede usar un visualizador de tráfico de red, como Charles*, Chrome Developer Tools o Firebug* para confirmar que DFA se está comunicando con los servidores de recopilación de Adobe.
keywords: DFA
seo-description: Después de haber realizado todas las actualizaciones de sitios web que se requieran, puede usar un visualizador de tráfico de red, como Charles*, Chrome Developer Tools o Firebug* para confirmar que DFA se está comunicando con los servidores de recopilación de Adobe.
seo-title: Confirmar una integración DFA correcta
solution: Analytics
title: Confirmar una integración DFA correcta
topic: Data Connectors
uuid: d 658 cd 7 c -6377-439 a -850 c-ecea 8 c 41 f 970
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Confirmar una integración DFA correcta{#confirming-a-successful-dfa-integration}

Después de haber realizado todas las actualizaciones de sitios web que se requieran, puede usar un visualizador de tráfico de red, como Charles*, Chrome Developer Tools o Firebug* para confirmar que DFA se está comunicando con los servidores de recopilación de Adobe.

Después de haber implementado el archivo `s_code.js` que se puede usar con DFA, use el visualizador de tráfico de red para ver las solicitudes entre los servidores de recopilación de datos de Adobe y DFA, buscando lo siguiente:

* A request to DFA's `fls.doubleclick.net/json` service. Este servicio puede responder de forma diferente según la versión de DFA que esté usando. Con la versión 1.5 de Integración de DFA:

   * Un redireccionamiento HTTP 302 a [!DNL ad.doubleclick.net]. Enviará una etiqueta Location: en la respuesta que contiene información acerca del visitante del anuncio.
   * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. Este servicio traduce la información acerca del visitante del anuncio en una cadena con codificación de JSON (JavaScript Object Notation). Estos datos se devuelven con una respuesta 200 OK HTTP.

* Con la versión 2.0 de Integración de DFA (Servicio de publicidad avanzado habilitado):

   * [!DNL fls.doubleclick.net] responderá directamente con 200 OK.

En cualquier caso, una solicitud correcta dará como resultado una solicitud a los servidores de recopilación de datos de Adobe que contiene el parámetro vX (donde X es su número de eVar de visualización). El valor de este parámetro adopta el formato: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Esta cadena contiene datos acerca del último clic y de la última impresión para el visitante actual.
