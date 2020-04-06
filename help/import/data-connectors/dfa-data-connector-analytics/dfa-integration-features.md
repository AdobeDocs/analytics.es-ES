---
description: 'Una vez activada, la integración Data Connectors DFA proporciona las siguientes métricas para sus informes de Adobe Analytics '
keywords: DFA
title: Funciones de integración
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Funciones de integración {#integration-features}

Una vez activada, la integración Data Connectors DFA proporciona las siguientes métricas para sus informes de Adobe Analytics:

* Vistas
* Clics de DFA
* Impresiones
* (Opcional) Datos de costes de DFA
* (Opcional) Errores de consultas de DFA, Tiempos de espera

>[!NOTE] Esta integración no proporciona soporte para rastreadores de clics (anteriormente comandos de clics). Los rastreadores de clics se utilizan para registrar el número de clics en vínculos de texto, vínculos en mensajes de correo electrónico o en otros elementos que están codificados en un sitio Web.

La integración de DFA de Data Connectors crea automáticamente códigos de seguimiento de DFA a partir de los datos devueltos por DFA. Estos códigos de seguimiento se crean para identificar de forma exclusiva un anuncio junto con su Ubicación y Creativo asociados. A continuación se describe la estructura del código de seguimiento, en función de la versión de la integración. La versión 1.5 tiene este aspecto:

![](assets/DFA_id_struct1_5.png)

La versión 2.0 tiene este aspecto:

![](assets/DFA_id_struct2.png)

Estos ID sirven como clave compartida entre Genesis y DFA para asociar las clasificaciones y métricas correctas.

| ID del sitio | El sitio de terceros en el que se alojó la publicidad. La clasificación Nombre del sitio proporciona un nombre descriptivo de esta ID del sitio. |
|---|---|
| ID de anuncio | ID del mensaje comercial que se entrega a un usuario. La clasificación Nombre del anuncio contiene el nombre de la publicidad tal como lo define su organización en el sistema DFA. Por ejemplo: `Hybrid Coup Textlink - Build`. |
| ID de colocación | Una representación en la cuenta de DFA de un sitio Web, parte de un sitio Web o grupo de sitios Web donde compró espacio de publicidad. |
| ID del creativo | La imagen, Flash SWF u otro recurso que se va a mostrar al visitante. La clasificación Nombre creativo contiene el nombre que ha proporcionado a este elemento creativo en la interfaz de DFA. |

Las otras dos clasificaciones, Herramienta Envío (DoubleClick para anunciantes) y Canal (Publicidad tipo titular), tienen los mismos valores para cualquier campaña DFA y ayudan a distinguir los datos importados de DFA.

## Anulación de duplicación de SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

La integración de DFA ahora reconoce Adobe SearchCenter. Al habilitar la anulación de duplicación de SearchCenter mediante el asistente de Data Connectors, los visitantes guiados por la búsqueda no hacen que se extraigan datos del servidor de Floodlight de DFA y no se completan los *`s.campaign`* con DFA, permitiendo así que SearchCenter los rellene. Además, DFA y SearchCenter ahora rellenan los valores de desduplicación en las variables de cada producto.

La lista siguiente describe la lógica que se habilita cuando se habilita la anulación de duplicación de SearchCenter:

Si **[!UICONTROL DFA]** > **[!UICONTROL SearchCenter deduplication]** está seleccionado en el asistente:

* En el caso de hacer clic en DFA, la integración rellena la cadena “Hacer clic en DFA” con la eVar de SCM configurada.
* En el caso de una visualización de DFA, la integración rellena la cadena “Visualización de DFA” con la eVar de SCM configurada.

Si **[!UICONTROL SearchCenter]** > **[!UICONTROL DFA deduplication]** está seleccionado en el asistente:

* En el caso de una visualización de DFA, la integración rellena la cadena “Visualización de DFA” con la eVar de SCM configurada.

>[!NOTE] Si SearchCenter > Anulación de duplicación de DFA está habilitada y el parámetro de cadena de consulta de SearchCenter está establecido, la visita no se considera para procesamiento de DFA. Esto significa que el parámetro de cadena de consulta de SearchCenter debería ser diferente al parámetro de clics en DFA, y ningún anuncio de visualización debería establecer el parámetro de cadena de consulta de SearchCenter.

