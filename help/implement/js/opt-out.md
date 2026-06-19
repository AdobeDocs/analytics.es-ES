---
title: Vínculos de no participación
description: Obtenga información sobre cómo crear e implementar Vínculos de no participación para los visitantes del sitio.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
role: Developer
TQID: https://experienceleague.adobe.com/3X3RsfI3J96Ml4Q2UvnaaPLfBihSPvD-bfE8-yZujzU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 603
ht-degree: 69%

---

# Implementación de Vínculos de no participación

>[!IMPORTANT]
>
> Este artículo proporciona a **clientes de Adobe Analytics que (están planeando) implementar Adobe Analytics** en su sitio web instrucciones sobre cómo proporcionar a los usuarios del sitio web vínculos de no participación. <p><p>> Si está **visitando un sitio web que ha implementado Adobe Analytics** y desea excluirse, **<span style="color:red">este artículo NO es para usted</span>**. Consulta [Opciones de privacidad de Adobe](https://www.adobe.com/es/privacy/opt-out.html) para controlar cómo usa Adobe tu información.

Algunos visitantes del sitio Web prefieren no incluir su información de navegación en el conjunto de datos. Adobe permite excluir a los visitantes de un sitio web del análisis de su información.

Los vínculos de exclusión permiten a los visitantes del sitio web omitir sus datos en los informes de Analytics. Estos vínculos se limitan a implementaciones de AppMeasurement; Adobe recomienda usar el [servicio de inclusión empresarial de Adobe CX](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=es) en su lugar. El servicio de inclusión (Opt-in) es más robusto y funciona con varios productos empresariales de Adobe CX, incluidos Adobe Analytics y AppMeasurement.

Cuando un visitante llega a una URL de exclusión, se le solicita que instale una cookie de exclusión. Si un usuario decide no rastrearse y se establece una cookie de exclusión, AppMeasurement continúa enviando datos a Adobe. Sin embargo, esos datos no se procesan ni se incluyen en los informes.

>[!TIP]
>
>Adobe también ofrece la configuración de privacidad por grupo de informes. Consulte [Configuración de privacidad](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md) en la guía del usuario del administrador.

## URL de exclusión

La página de exclusión de su organización depende del valor de la variable [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) en la implementación.

* En la extensión de Analytics:
   1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
   1. Haga clic en la propiedad de etiquetas deseada.
   1. Haga clic en la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.
   1. Haga clic en el acordeón [!UICONTROL General] y anote el valor [!UICONTROL Servidor de seguimiento].

* En una implementación de JavaScript:
   1. En el servidor web, abra el archivo AppMeasurement.js que se utiliza en el sitio en un editor de código o texto.
   1. Tenga en cuenta el valor de la variable `trackingServer`.

* Uso de [Adobe CX Enterprise Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Vaya a su sitio mediante el explorador Chrome.
   1. Abra CX Enterprise Debugger y vaya a la [!UICONTROL pestaña Red].
   1. Tenga en cuenta el valor de [!UICONTROL Solicitar URL: Nombre de host].

Una vez encontrado el dominio `trackingServer` de la implementación, anexe la ruta `/optout.html` al final. Por ejemplo:

* Cookies de terceros: `https://example.data.adobedc.net/optout.html`
* Cookies de origen: `https://stats.example.com/optout.html`

## Parámetros de cadena de consulta de exclusión

Hay opciones que se pueden cargar automáticamente en esta página mediante cadenas de consulta.

### Configuración regional

Cambiar automáticamente el idioma de la página de exclusión incluyendo el parámetro de cadena de consulta `locale`. Asigne este parámetro de cadena de consulta uno de los siguientes valores:

* `en_US` (inglés, predeterminado)
* `bg_BG` (búlgaro)
* `zh_CN` (chino simplificado)
* `zh_TW` (chino tradicional)
* `cs_CZ` (checo)
* `da_NK` (danés)
* `nl_NL` (neerlandés)
* `et_EE` (estonio)
* `fi_FI` (finés)
* `fr_FR` (francés)
* `de_DE` (alemán)
* `el_GR` (griego)
* `it_IT` (italiano)
* `jp_JP` (japonés)
* `ko_KR` (coreano)
* `lv_LV` (letón)
* `lt_LT` (lituano)
* `nb_NO` (noruego)
* `pl_PL` (polaco)
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
