---
title: ID de AMO
description: El ID de Adobe Media Optimizer, utilizado en las integraciones de Adobe Advertising.
feature: Dimensions
exl-id: 90642896-43dd-4ac0-bfb8-7fe34c0e0302
TQID: 'https://experienceleague.adobe.com/SzHWYAzd9iYcd5AU86TVL6Bfca4UsuijV141jBuS0y8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 793
ht-degree: 2%

---

# ID de AMO

El **[!UICONTROL ID de AMO]** es una colección de identificadores concatenados que se usan en integraciones de Adobe Advertising. Los valores almacenados en esta dimensión se organizan automáticamente en dimensiones de clasificación independientes y más legibles para su uso en los informes de Analytics. La dimensión se crea automáticamente al habilitar la integración de [Analytics para Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview).

## Rellene esta dimensión con datos

Esta dimensión recopila sus valores de varias formas:

* Para el tráfico de clics, los datos se recopilan del parámetro de cadena de consulta `s_kwcid` en la [URL de página](page-url.md), normalmente en la página a través de la cual entra el tráfico impulsado por anuncios en el sitio.
* El tráfico de clics también se puede capturar cuando la dirección URL no contiene códigos de seguimiento, pero Adobe Advertising JavaScript detecta un clic en los dos minutos anteriores.
* Para el tráfico de visualización admitido, Adobe Advertising complementa los valores del backend con un ID suplementario (`SDID`).

## Elementos de dimensión

Los elementos de Dimension incluyen ID de AMO, también denominados `s_kwcid` valores. El formato exacto depende de si el tráfico se originó en DSP o en Search, Social y Commerce. Los ID de AMO son menos granulares que los de EF y se utilizan principalmente para clasificaciones e ingesta de métricas de Adobe Advertising en Analytics.

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**: indica el canal de visualización.
* **`ad key`**: identificador alfanumérico generado por Adobe Advertising para el anuncio.
* **`placement key`**: identificador alfanumérico generado por Adobe Advertising para la ubicación.

Valor de ejemplo:

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### Anuncios de Search, Social y Commerce

Los ID de AMO de Search, Social y Commerce comienzan por `AL`, seguidos por el ID de usuario del anunciante, el ID de cuenta de red de anuncios y los identificadores específicos de la red. Los ID de cuenta de red y compartidos incluyen:

* **`3`**: Google Ads
* **`10`**: Microsoft Advertising
* **`45`**: Meta
* **`86`**: Yahoo! Mostrar red
* **`87`**: Naver
* **`88`**: Baidu
* **`90`**: Yandex
* **`94`**: Yahoo! Anuncios de Japón
* **`105`**: Yahoo Native (obsoleto)
* **`106`**: Pinterest (obsoleto)

#### Google Ads

Google Ads utiliza dos formatos relacionados. Las cuentas más recientes pueden incluir el ID de campaña y el ID de grupo de publicidad, que admite la creación de informes de nivel de campaña y de grupo de publicidad para las campañas Máximo rendimiento y borradores/experimentos.

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**: ID creativo de Google Ads.
* **`matchtype`**: tipo de coincidencia de palabra clave (`e` para exacto, `p` para frase, `b` para amplio).
* **`placement`**: dominio en el que se hizo clic en el anuncio.
* **`network`**: red en la que se produjo el clic (`g` para la búsqueda de Google, `s` para un socio de búsqueda, `d` para la visualización).
* **`product partition`**: ID de grupo de productos para anuncios de productos.
* **`keyword`**: palabra clave de activación en sitios de búsqueda o palabra clave que mejor coincide en sitios de contenido.
* **`campaign id`**: ID de campaña de Google Ads, cuando está presente.
* **`ad group id`**: ID de grupo de anuncios de Google Ads, cuando está presente.

En el caso de los anuncios dinámicos de búsqueda, el campo de palabra clave se rellena con el destino automático.

Ejemplo:

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**: Microsoft Advertising Creative ID.
* **`keyword/order item id`**: ID de palabra clave de Microsoft Advertising.
* **`campaign id`**: ID de campaña de Microsoft Advertising.
* **`ad group id`**: ID del grupo de anuncios de Microsoft Advertising.

Los formatos de Microsoft heredados pueden seguir existiendo para algunas cuentas no migradas.

Ejemplo:

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### Baidu

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**: ID creativo de Baidu.
* **`placement`**: sitio web en el que se hizo clic en el anuncio.
* **`keyword id`**: ID de palabra clave Baidu.

#### Yahoo Anuncios de Japón

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**: Yahoo! ID creativo de anuncios de Japón.
* **`matchtype`**: tipo de coincidencia de palabra clave (`be` exacta, frase `bp`, `bb` amplia).
* **`network`**: red en la que se produjo el clic (nativo `n`, búsqueda `s`).
* **`keyword`**: Palabra clave de activación.

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**: ID de creatividad de Yandex.
* **`source type`**: tipo de sitio en el que se mostró el anuncio (`b` búsqueda, `c` contexto/contenido, `ct` categoría).
* **`phrase id`**: ID de palabra clave Yandex.

## Clasificaciones

Al habilitar la integración de [Analytics para Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview), se crean automáticamente las siguientes clasificaciones. La integración mantiene automáticamente los valores de clasificación.

| Clasificación | Descripción | DSP | Buscar,<br>Social y<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL Cuenta]** | El nombre de la cuenta. | &comprobar; | &comprobar; |
| **[!UICONTROL URL para mostrar el anuncio]** | Dirección URL mostrada en el anuncio. | | &comprobar; |
| **[!UICONTROL Descripción del anuncio]** | La descripción del anuncio (DSP) o el cuerpo del anuncio (Search, Social y Commerce). | &comprobar; | &comprobar; |
| **[!UICONTROL URL de destino de anuncio]** | La URL de destino del anuncio. | | &comprobar; |
| **[!UICONTROL Grupo de anuncios]** | El nombre del grupo de publicidad. | | &comprobar; |
| **[!UICONTROL Plataforma de publicidad]** | El nombre del DSP de publicidad o del motor de búsqueda. | &comprobar; | &comprobar; |
| **[!UICONTROL Título de anuncio]** | El tipo de anuncio (DSP) o su título (Search, Social y Commerce). | &comprobar; | &comprobar; |
| **[!UICONTROL Tipo de anuncio]** | El tipo de anuncio, como `text`, `video`, `display` o `native`. | &comprobar; | &comprobar; |
| **[!UICONTROL Atributo de AdCloud 1]** -<br>**[!UICONTROL Atributo de AdCloud 5 &#x200B;]** | Clasificaciones de marcadores de posición reservadas para atributos personalizados futuros. No está en uso actualmente. | | |
| **[!UICONTROL Campaign]** | Nombre de la campaña. | &comprobar; | &comprobar; |
| **[!UICONTROL Nombre de experiencia Creative]** | Nombre de la experiencia creativa asociada con la interacción publicitaria, que representa un grupo de variaciones creativas utilizadas en las pruebas o la personalización. | &comprobar; | |
| **[!UICONTROL Nombre de rama de Creative]** | Nombre de la rama de una experiencia creativa que representa una variación o ruta específica en el experimento creativo. | &comprobar; | |
| **[!UICONTROL ID de sucursal de Creative]** | Identificador único asignado a una rama creativa dentro de una experiencia creativa. | &comprobar; | |
| **[!UICONTROL Nombre de Creative]** | Nombre del recurso específico y creativo que se proporcionó al usuario. | &comprobar; | |
| **[!UICONTROL Nombre de variante de Creative]** | Nombre de la variante específica de un elemento creativo utilizado dentro de una experiencia o rama creativa. | &comprobar; | |
| **[!UICONTROL Palabra clave]** | La palabra clave. | | &comprobar; |
| **[!UICONTROL Tipo de coincidencia de palabra clave]** | La palabra clave y el tipo de coincidencia. | | &comprobar; |
| **[!UICONTROL Tipo de aterrizaje]** | Si la entrada de la página de aterrizaje fue una visualización o un clic. | &comprobar; | &comprobar; |
| **[!UICONTROL Tipo de coincidencia]** | El tipo de coincidencia de búsqueda. | | &comprobar; |
| **[!UICONTROL Red]** | RTB (DSP) o el nombre de la red de publicidad (Search, Social y Commerce). | &comprobar; | &comprobar; |
| **[!UICONTROL Optimización]** | El nombre del paquete (DSP) o el nombre del portafolio (Search, Social y Commerce). | &comprobar; | &comprobar; |
| **[!UICONTROL Ubicación]** | El nombre de la ubicación. | &comprobar; | |
| **[!UICONTROL Destino del producto]** | El destino de un producto para un anuncio de lista de productos. | | &comprobar; |
