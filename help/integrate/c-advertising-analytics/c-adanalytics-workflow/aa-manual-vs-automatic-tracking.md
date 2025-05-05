---
description: El tipo de seguimiento determina cómo la implementación de Adobe Analytics realiza un seguimiento de los datos del motor de búsqueda. Este tipo de seguimiento es un paso necesario para aumentar correctamente los datos de Adobe Analytics con los datos del motor de búsqueda.
title: Tipo de seguimiento
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 243da53fda562c856d95db0f6d13b7ee1a9adae5
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 32%

---

# Tipo de seguimiento

El tipo de seguimiento determina cómo la implementación de Adobe Analytics realiza un seguimiento de los datos del motor de búsqueda. Este tipo de seguimiento es un paso necesario para aumentar correctamente los datos de Adobe Analytics con los datos del motor de búsqueda.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

-->

Se admiten dos modos de seguimiento: [!UICONTROL Automático] y [!UICONTROL Manual].

## Seguimiento [!UICONTROL Automático] {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

El seguimiento [!UICONTROL Automático] permite que el motor de Advertising Cloud decida cómo se deben administrar los datos del motor de búsqueda. El seguimiento automático es el enfoque más sencillo, pero es posible que no genere el conjunto de datos mejor integrado.

Como consecuencia, debes marcar una casilla de verificación de confirmación cuando selecciones **[!UICONTROL Automático]** para poder guardar la configuración de la cuenta.

Tenga en cuenta que para configurar una cuenta de motor de búsqueda con tipo **[!UICONTROL Automático]**, debe llevar a cabo las siguientes acciones:

* El parámetro y valor `s_kwcid` se agrega a las plantillas de seguimiento de la cuenta o a las direcciones URL de las páginas de aterrizaje en la cuenta que se agrega. Este parámetro y valor se inserta al final de la dirección URL. Es posible que deba llevar a cabo acciones adicionales si su servidor web requiere un determinado par `key=value` al final de la dirección URL. O una actualización para admitir cualquier nuevo par `key=value` en la dirección URL. Usted es responsable de garantizar que los parámetros de URL añadidos se conserven correctamente en la página de aterrizaje final.
* Además, es posible insertar palabras clave en la URL de destino como parte del valor `s_kwcid` Si contienen caracteres especiales o símbolos, confirme que su servidor web los admite. Por ejemplo, un carácter especial común es `+`, que se utiliza en las palabras clave &quot;Broad Match Modified&quot;.

>[!IMPORTANT]
>
>Obtenga más información sobre si debe agregar el parámetro `s_kwcid` a la [directiva de seguridad de contenido](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).

## Seguimiento manual {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

El seguimiento manual le permite especificar cómo debe tratar el proceso de integración de datos de Advertising Analytics los datos del motor de búsqueda.

### Añadir el seguimiento manual a la cuenta de Google {#section_41C1EB1AEB034544A5BC291F53C05C67}

A continuación, se muestra la cadena que debe añadirse a la cuenta de Google. Debe añadir la cadena a todas las plantillas de seguimiento utilizadas en la cuenta.

>[!IMPORTANT]
>
>El valor *`<Advertising Analytics ID>`* (en **negrita** abajo) es genérico y **se debe sustituir por la cadena del identificador de la cuenta específica**. Puede obtener la cadena del identificador de la cuenta específica en la sección [!UICONTROL Seguimiento] de la pantalla de la cuenta.

**Cadena de seguimiento para campañas:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

Ejemplos de códigos de seguimiento en varios formatos de plantilla de seguimiento:

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`con parámetro de URL adicional**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**Terceros (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**Terceros (DoubleClick)`{lpurl}`**

Para asegurarse de que la cadena se mantiene a través del redireccionamiento a la dirección URL de la página de aterrizaje final, debe codificar la cadena lo suficiente:

* si la dirección URL se redirecciona, y
* no utiliza un valor &quot;unescapedlpurl&quot;.


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Añadir el seguimiento manual a la cuenta de Bing {#section_094F8ACA493C4D65B1F54A695558EBF2}

A continuación, se muestra la cadena que debe añadirse a la cuenta de Bing. Debe añadir la cadena a todos los sufijos finales de las URL utilizadas en la cuenta.

>[!IMPORTANT]
>
>El valor _`<Advertising Analytics ID>`_(en **negrita**&#x200B;abajo) es genérico y **se debe sustituir por la cadena del identificador de la cuenta específica**. Puede obtener la cadena del ID de cuenta específica en la sección &quot;Seguimiento&quot; de la pantalla de la cuenta.

**Cadena de seguimiento para campañas:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![Bing](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

Ejemplos de códigos de seguimiento en diversos formatos de sufijos finales de URL:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`con parámetro de URL adicional**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terceros (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Terceros (DoubleClick)`{lpurl}`**

Para asegurarse de que la cadena se mantiene a través del redireccionamiento a la dirección URL de la página de aterrizaje final, debe codificar la cadena lo suficiente:

* si la dirección URL se redirecciona, y
* no utiliza un valor &quot;unescapedlpurl&quot;.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
