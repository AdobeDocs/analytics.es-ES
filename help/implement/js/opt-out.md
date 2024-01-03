---
title: Vínculos de no participación
description: Obtenga información sobre cómo crear e implementar Vínculos de no participación para los visitantes del sitio.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 71%

---

# Implementación de Vínculos de no participación

>[!IMPORTANT]
>
> **Esta página de ayuda permite a los clientes de Adobe Analytics proporcionar a sus usuarios vínculos de no participación. Si no es cliente de Adobe Analytics, consulte [Opciones de privacidad de Adobe](https://www.adobe.com/es/privacy/opt-out.html) para controlar cómo utiliza el Adobe su información.**

Algunos visitantes del sitio Web prefieren no incluir su información de navegación en el conjunto de datos. El Adobe permite proporcionar a los visitantes de un sitio web un medio para evitar que se analice su información.

Los vínculos de exclusión permiten a los visitantes del sitio web omitir sus datos en los informes de Analytics. Estos vínculos se limitan a implementaciones de AppMeasurement; Adobe recomienda utilizar la variable [Servicio de inclusión de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=es) en su lugar. El servicio de inclusión (Opt-in) es más robusto y funciona con varios productos de Adobe Experience Cloud, incluidos Adobe Analytics y AppMeasurement.

Cuando un visitante llega a una URL de exclusión, se le solicita que instale una cookie de exclusión. Si un usuario decide no rastrearse y se establece una cookie de exclusión, el AppMeasurement continúa enviando datos al Adobe. Sin embargo, esos datos no se procesan ni se incluyen en los informes.

>[!TIP]
>
>Adobe también ofrece la configuración de privacidad por grupo de informes. Consulte [Configuración de privacidad](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md) en la guía del usuario del administrador.

## URL de exclusión

La página de exclusión de su organización depende del valor de la variable [`trackingServer`](../vars/config-vars/trackingserver.md) en la implementación.

* En la extensión de Analytics:
   1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
   1. Haga clic en la propiedad de etiquetas deseada.
   1. Haga clic en la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.
   1. Haga clic en el acordeón [!UICONTROL General] y anote el valor [!UICONTROL Servidor de seguimiento].

* En una implementación de JavaScript:
   1. En el servidor web, abra el archivo AppMeasurement.js que se utiliza en el sitio en un editor de código o texto.
   1. Tenga en cuenta el valor de la variable `trackingServer`.

* Use [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Vaya a su sitio mediante el explorador Chrome.
   1. Abra Experience Cloud Debugger y vaya a la pestaña [!UICONTROL Red].
   1. Tenga en cuenta el valor de [!UICONTROL Solicitar URL: Nombre de host].

Una vez encontrado el dominio `trackingServer` de la implementación, anexe la ruta `/optout.html` al final. Por ejemplo:

* Cookies de terceros: `https://example.data.adobedc.net/optout.html`
* Cookies de origen: `https://stats.example.com/optout.html`

## Parámetros de cadena de consulta de exclusión

Hay opciones que se pueden cargar automáticamente en esta página mediante cadenas de consulta.

### Configuración regional

Cambiar automáticamente el idioma de la página de exclusión incluyendo el parámetro de cadena de consulta `locale`. Asigne este parámetro de cadena de consulta uno de los siguientes valores:

* `en_US` (Inglés, predeterminado)
* `bg_BG` (Búlgaro)
* `zh_CN` (Chino simplificado)
* `zh_TW` (Chino tradicional)
* `cs_CZ` (Checo)
* `da_NK` (Danés)
* `nl_NL` (neerlandés)
* `et_EE` (Estonio)
* `fi_FI` (finés)
* `fr_FR` (francés)
* `de_DE` (Alemán)
* `el_GR` (Griego)
* `it_IT` (Italiano)
* `jp_JP` (Japonés)
* `ko_KR` (Coreano)
* `lv_LV` (Letón)
* `lt_LT` (lituano)
* `nb_NO` (Noruego)
* `pl_PL` (Polaco)
* `pt_BR` (portugués)
* `sk_SK` (eslovaco)
* `es_ES` (español)

Por ejemplo, `https://example.data.adobedc.net/optout.html?locale=ko_KR` carga la página de exclusión en coreano.

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
