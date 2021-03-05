---
description: Requisitos previos para utilizar el conector de datos DFA con Adobe Analytics.
keywords: DFA
title: Requisitos previos
topic: Data Connectors
uuid: b5f5e30c-e269-41a4-9236-5ddc404bfd94
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 97%

---


# Requisitos previos {#prerequisites}

Antes de empezar la integración de Data Connectors de Adobe para DFA, haga lo siguiente:

* Decida si desea integrar con la versión 1.5 de la integración, o si desea esperar la versión 2.0. Esta decisión depende de las funciones que se utilizan en su cuenta DFA y el período de tiempo que desee integrar.
* Decida cómo los Anunciantes de DFA asignarán grupos de informes de Adobe Analytics. Por ejemplo, si tiene varios Anunciantes de DFA y varios grupos de informes, tendrá que decidir qué par de Anunciantes con qué grupos de informes.
* Implemente código de recopilación de datos en todas las páginas que desee rastrear, usando la versión H.22 o posterior del código de recopilación de datos.
* Conozca el ID del anunciante para una cuenta DFA que forma parte de la Configuración de Floodlight que desee integrar. La integración importa automáticamente todos los Anunciantes que están dentro de la Configuración de Floodlight.
* Conozca el nombre de usuario y las contraseñas de su cuenta DFA.
* Asocie cada Anunciante DFA a solo un grupo de informes de Adobe Analytics. El etiquetado en varios grupos de informes no se admite con la integración de Genesis predeterminada para DFA.
* Agregue un parámetro de cadena de consulta de clic a la página de aterrizaje para cada ubicación de DFA que formará parte de la integración. Este parámetro de cadena de consulta es necesario para contar correctamente los clics.
* Configure sus ubicaciones de DFA de modo que no redirijan visitantes a través de varios dominios. Por ejemplo, una ubicación no debería dirigir encuestados a un micrositio dentro de www.xyz.com si el micrositio luego los redirige a otro sitio, www.fgh.com. Si la respuesta de la campaña abarca varios dominios, los datos de clics y visualizaciones pueden estar inflados y ser confusos.
* Identifique una variable personalizada en Reports &amp; Analytics para almacenar su información de campaña.
* Identifique una eVar de Reports &amp; Analytics para almacenar información de visualización de DFA. Use esta eVar únicamente para esta integración de DFA.
* Identifique los eventos de Reports &amp; Analytics donde desee almacenar datos de Impresiones y Clics. Puede que desee cambiar el nombre de estos eventos según corresponda.
* (Opcional) Identifique los eventos de Reports &amp; Analytics que almacenarán datos de Costes de DFA. Puede que desee cambiar el nombre de estos eventos según corresponda.
* (Opcional) Identifique un Evento de éxito y una Variable personalizada de Reports &amp; Analytics que almacenarán errores y tiempos de espera de DFA. Estas variables ayudan a diagnosticar problemas que podrían surgir con la integración.
* (Opcional) Cree una cuenta de correo electrónico especial para recibir información y notificaciones relacionadas con la integración de Data Connectors para DFA.

