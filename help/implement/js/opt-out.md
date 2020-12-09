---
title: Vínculos de no participación
description: Obtenga información sobre cómo crear e implementar Vínculos de no participación para los visitantes del sitio.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 100%

---


# Implementación de Vínculos de no participación

>[!IMPORTANT]
>
>Adobe recomienda utilizar el servicio de inclusión, especialmente para las organizaciones relacionadas con las regulaciones del RGPD. Consulte [Introducción al servicio de inclusión](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/optin-overview.html) en la guía del usuario del servicio de Experience Cloud ID.

Algunos visitantes del sitio Web prefieren no incluir su información de navegación en el conjunto de datos. Adobe permite especificar a los visitantes de un sitio web que así lo consideren que no desean que su información se recopile. Se admiten todos los tipos de implementación; su organización es responsable de su propia política de privacidad y de cumplir con los términos firmados.

Cuando un visitante llega a una URL de exclusión, se le solicita que instale una cookie de exclusión. Si un usuario decide no rastrearse y se establece una cookie de exclusión, su archivo JavaScript continúa enviando datos a los servidores de Adobe. Sin embargo, esos datos no se procesan ni se incluyen en los informes.

>[!TIP]
>
>Adobe también ofrece la configuración de privacidad por grupo de informes. Consulte [Configuración de privacidad](../../admin/admin/privacy-settings.md) en la guía del usuario del administrador.

## URL de exclusión

La página de exclusión de su organización depende del valor de la variable [`trackingServer`](../vars/config-vars/trackingserver.md) en la implementación.

* En Adobe Experience Platform Launch:
   1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) y haga clic en la propiedad que desee.
   2. Haga clic en la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.
   3. Haga clic en el acordeón [!UICONTROL General] y anote el valor [!UICONTROL Servidor de seguimiento].

* En una implementación de JavaScript:
   1. En el servidor web, abra el archivo AppMeasurement.js que se utiliza en el sitio en un editor de código o texto.
   2. Tenga en cuenta el valor de la variable `trackingServer`.

* Use [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html):
   1. Vaya a su sitio mediante el explorador Chrome.
   2. Abra Experience Cloud Debugger y vaya a la pestaña [!UICONTROL Red].
   3. Tenga en cuenta el valor de [!UICONTROL Solicitar URL: Nombre de host].

Una vez encontrado el dominio `trackingServer` de la implementación, anexe la ruta `/optout.html` al final. Por ejemplo:

* Cookies de terceros: `https://example.data.adobedc.net/optout.html`
* Cookies de origen: `https://stats.example.com/optout.html`

## Parámetros de cadena de consulta de exclusión

Hay opciones que se pueden cargar automáticamente en esta página mediante cadenas de consulta.

### Configuración regional

Cambiar automáticamente el idioma de la página de exclusión incluyendo el parámetro de cadena de consulta `locale`. Asigne este parámetro de cadena de consulta uno de los siguientes valores:

* en_US (inglés, predeterminado)
* bg_BG (búlgaro)
* zh_CN (chino simplificado)
* zh_TW (chino tradicional)
* cs_CZ (checo)
* da_NK (danés)
* nl_NL (neerlandés)
* et_EE (estonio)
* fi_FI (finés)
* fr_FR (francés)
* de_DE (alemán)
* el_GR (griego)
* it_IT (italiano)
* jp_JP (japonés)
* ko_KR (coreano)
* lv_LV (letón)
* lt_LT (lituano)
* nb_NO (noruego)
* pl_PL (polaco)
* pt_BR (portugués)
* sk_SK (eslovaco)
* es_ES (español)

Por ejemplo, `https://example.data.adobedc.net/optout.html?locale=ko_KR` carga la página de exclusión en coreano.

>[!TIP]
>
>El valor de la cadena de consulta `en_US` no es obligatorio, ya que la página se carga en inglés de forma predeterminada.

### Ventana emergente

Agrega un botón “Cerrar ventana” a la página, lo que permite que la página de exclusión se convierta en una ventana emergente. Utilice el parámetro de cadena de consulta `popup` y asígnele un valor de `1`.

Por ejemplo, `https://example.data.adobedc.net/optout.html?popup=1` carga la página de exclusión con el botón “Cerrar ventana”.

>[!NOTE]
>
>Históricamente, este parámetro de cadena de consulta forzó la aparición de una ventana emergente. Sin embargo, la mayoría de los exploradores modernos le dan control sobre las ventanas emergentes al usuario final.

### Opción de exclusión de un solo clic

Permite al usuario desactivar inmediatamente el seguimiento. Agregue los dos parámetros de cadena de consulta `opt_out` y `confirm_change`, dando a cada uno un valor de `1`.

Por ejemplo, `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` instala inmediatamente la cookie de exclusión en la página del visitante.

### Opción de inclusión de un solo clic

Permite que el usuario vuelva a realizar el seguimiento inmediatamente eliminando la cookie de exclusión. Agregue los dos parámetros de cadena de consulta `opt_in` y `confirm_change`, dando a cada uno un valor de `1`.

Por ejemplo, `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` elimina inmediatamente la cookie de exclusión del visitante.
