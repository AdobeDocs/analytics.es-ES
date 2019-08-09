---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: Requisitos previos
solution: Analytics
title: Requisitos previos
topic: Data Connectors
uuid: b 5 f 5 e 30 c-e 269-41 a 4-9236-5 ddc 404 bfd 94
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Requisitos previos{#prerequisites}

Antes de empezar la integración de Data Connectors de Adobe para DFA, haga lo siguiente:

* Decida si desea integrar con la versión 1.5 de la integración, o si desea esperar la versión 2.0. Esta decisión depende de las funciones que se utilizan en su cuenta DFA y el período de tiempo que desee integrar. Consulte [Acerca de la versión 2.0](../dfa-data-connector-analytics/dfa-version-differences.md#concept-2c7d6a6ab8524dccad96ea0c17228664) para obtener más información.
* Decida cómo los Anunciantes de DFA asignarán grupos de informes de Adobe Analytics. Por ejemplo, si tiene varios Anunciantes de DFA y varios grupos de informes, tendrá que decidir qué par de Anunciantes con qué grupos de informes.
* Implemente código de recopilación de datos en todas las páginas que desee rastrear, usando la versión H.22 o posterior del código de recopilación de datos.
* Conozca el ID del anunciante para una cuenta DFA que forma parte de la Configuración de Floodlight que desee integrar. La integración importa automáticamente todos los Anunciantes que están dentro de la Configuración de Floodlight.
* Conozca el nombre de usuario y las contraseñas de su cuenta DFA.
* Asocie cada Anunciante DFA a solo un grupo de informes de Adobe Analytics. El etiquetado en varios grupos de informes no se admite con la integración de Genesis predeterminada para DFA.
* Agregue un parámetro de cadena de consulta de pulsación a la página de aterrizaje para cada ubicación de DFA que formará parte de la integración. Este parámetro de cadena de consulta es necesario para contar correctamente las pulsaciones.
* Configure sus ubicaciones de DFA de modo que no redirijan visitantes a través de varios dominios. Por ejemplo, una ubicación no debería dirigir encuestados a un micrositio dentro de www.xyz.com si el micrositio luego los redirige a otro sitio, www.fgh.com. Si la respuesta de la campaña abarca varios dominios, los datos de pulsaciones y visualizaciones pueden estar inflados y ser confusos.
* Identifique una variable personalizada en Informes y análisis para almacenar su información de campaña.
* Identifique una eVar de Informes y análisis para almacenar información de visualización de DFA. Use esta eVar únicamente para esta integración de DFA.
* Identifique los eventos de Informes y análisis donde desee almacenar datos de Impresiones y Clics. Puede que desee cambiar el nombre de estos eventos según corresponda. 
* (Opcional) Identifique los eventos de Informes y análisis que almacenarán datos de Costes de DFA. Puede que desee cambiar el nombre de estos eventos según corresponda. 
* (Opcional) Identifique un Evento de éxito y una Variable personalizada de Informes y análisis que almacenarán errores y tiempos de espera de DFA. Estas variables ayudan a diagnosticar problemas que podrían surgir con la integración.
* (Opcional) Cree una cuenta de correo electrónico especial para recibir información y notificaciones relacionadas con la integración de Data Connectors para DFA.

