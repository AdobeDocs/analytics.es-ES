---
description: 'Una vez activada, la integración Data Connectors DFA proporciona las siguientes métricas para sus informes de Adobe Analytics '
keywords: DFA
seo-description: 'Una vez activada, la integración Data Connectors DFA proporciona las siguientes métricas para sus informes de Adobe Analytics '
seo-title: Funciones de integración
solution: Analytics
title: Funciones de integración
topic: Data Connectors
uuid: 4 ad 8 e 6 e 8-3449-498 a -8596-37 c 0 ac 1657 cd
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Funciones de integración{#integration-features}

Una vez activada, la integración Data Connectors DFA proporciona las siguientes métricas para sus informes de Adobe Analytics:

* Visualizaciones
* Clics de DFA
* Impresiones
* (opcional) Datos de costes de DFA
* (opcional) Errores de consultas de DFA, Tiempos de espera

>[!NOTE]
>
>Esta integración no proporciona compatibilidad con rastreadores de clics (anteriormente comandos de clics). Los rastreadores de clics se usan para registrar la cantidad de clics en vínculos de texto, vínculos en mensajes de correo electrónico o en otros elementos que no son modificables en un sitio web.

La integración de DFA de Data Connectors crea automáticamente códigos de seguimiento de DFA a partir de los datos devueltos por DFA. Estos códigos de seguimiento se crean para identificar de forma exclusiva un anuncio junto con su Ubicación y Creativo asociados. A continuación, se menciona la estructura del código de seguimiento, de acuerdo con la versión de la integración. La versión 1.5 tiene este formato:

![](assets/DFA_id_struct1_5.png)

La versión 2.0 tiene este formato:

![](assets/DFA_id_struct2.png)

Estos ID cumplen la función de clave compartida entre Genesis y DFA para asociar las clasificaciones y métricas correctas.

| ID del sitio | El sitio de terceros en el que se alojó el anuncio. La clasificación del Nombre del sitio proporciona un nombre descriptivo de este ID del sitio. |
|---|---|
| ID de anuncio | Un ID para el mensaje comercial que se entrega a un usuario. La clasificación del Nombre del anuncio contiene el nombre del anuncio tal como lo define su organización en el sistema de DFA. Por ejemplo: `Hybrid Coup Textlink - Build`. |
| ID de ubicación | Una representación en la cuenta de DFA de un sitio web, parte de un sitio web o grupo de sitios web donde ha comprado espacio de publicidad. |
| ID del creativo | La imagen, Flash SWF u otro recurso pensado para ser mostrado al visitante. La clasificación Nombre del creativo contiene el nombre que ha proporcionado a este creativo en la interfaz DFA. |

Las otras dos clasificaciones, Herramienta de entrega (DoubleClick para Anunciantes) y Canal (anuncio tipo titular) tienen los mismos valores para cualquier campaña de DFA y ayudan a distinguir datos importados de DFA.

## Anulación de duplicación de SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

La integración de DFA ahora reconoce Adobe SearchCenter. Al habilitar la anulación de duplicación de SearchCenter mediante el asistente de Data Connectors, los visitantes que llegan por búsqueda no harán que los datos se extraigan del Servidor de Floodlight de DFA, y DFA no se completará *`s.campaign`* permitiendo así que SearchCenter lo rellene. Además, DFA y SearchCenter ahora rellenan valores de anulación de duplicación en las variables para cada producto.

La siguiente lista describe la lógica que se habilita cuando está habilitada la anulación de duplicación de SearchCenter:

If **[!UICONTROL DFA]** &gt; **[!UICONTROL SearchCenter deduplication]** is selected in the wizard:

* En el caso de una pulsación de DFA, la integración rellenará la cadena “Pulsación de DFA” con la eVar de SCM configurada.
* En el caso de una visualización de DFA, la integración rellenará la cadena “Visualización de DFA” con la eVar de SCM configurada.

If **[!UICONTROL SearchCenter]** &gt; **[!UICONTROL DFA deduplication]** is selected in the wizard:

* En el caso de una visualización de DFA, la integración rellenará la cadena “Visualización de DFA” con la eVar de SCM configurada.

>[!NOTE]
>
>Si searchcenter &gt; Anulación de duplicación de DFA está habilitado y el parámetro de cadena de consulta de searchcenter está establecido, la visita no se considerará para el procesamiento de DFA. Esto significa que el parámetro de cadena de consulta de SearchCenter debería ser diferente al parámetro de pulsación de DFA, y ningún anuncio de visualización debería establecer el parámetro de cadena de consulta de SearchCenter.

