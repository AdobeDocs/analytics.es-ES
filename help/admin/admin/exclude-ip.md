---
description: Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos mejora la precisión del informe al excluir los datos de direcciones IP. Además, puede eliminar datos de la denegación de servicio u otros eventos malintencionados que puedan distorsionar los datos del informe. Puede configurar la exclusión o utilizar el servidor de seguridad.
title: Excluir por dirección IP
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Excluir por dirección IP

Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos mejora la precisión del informe al excluir los datos de direcciones IP. Además, puede eliminar datos de la denegación de servicio u otros eventos malintencionados que puedan distorsionar los datos del informe. Puede configurar la exclusión o utilizar el servidor de seguridad.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE] Las visitas excluidas por dirección IP se facturan como [llamadas al servidor](https://marketing.adobe.com/resources/help/es_ES/reference/primary_server_calls.html).

## Excluir por cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Permite excluir este equipo del seguimiento en su cuenta. Si decide excluir el equipo, no se contará ningún dato generado desde el mismo.

Esta función permite al usuario y a sus compañeros visitar el sitio sin distorsionar los datos del tráfico. Es posible que desee utilizar esta función si no tiene una dirección IP estática (como tener una conexión a Internet de acceso telefónico a través de un proveedor de servicio) y desea excluirse de los datos de su cuenta.

| Elemento | Descripción |
|--- |--- |
| [!UICONTROL Add CNAME] | Genera un vínculo de exclusión que puede utilizar para excluir su dominio. Para obtener ayuda, póngase en contacto con los usuarios de asistencia técnica de la empresa. <br>Puede excluirse el tráfico para que no quede registrado en los grupos de informes desde la página de exclusión de la empresa, donde puede especificarse la exclusión del explorador de la medición. <br>Si la implementación utiliza cookies de terceros, la página de exclusión estará [aquí](https://democorp.112.2o7.net/optout.html?locale=es_ES&amp;popup=true). |

>[!NOTE] La exclusión por equipo solo funcionará si:
>
> * Usted ingresa a su sitio Web desde la misma estación de trabajo.
> * Se habilitan sus cookies en el explorador que está utilizando.
> * No se eliminan sus cookies.  Si se eliminan las cookies, usted deberá excluirse nuevamente.


## Excluir por dirección IP {#section_609FB6461529409D840111A32FEF5C3D}

Una dirección IP es una dirección de Internet. A todos los usuarios de Internet se les asignan direcciones IP numéricas (generalmente a través de proveedores de servicio de Internet) que actúan efectivamente como identificadores electrónicos.

Las vistas de página se cuentan y los visitantes de página únicos se identifican mediante direcciones IP. Al excluir del recuento las direcciones IP, puede evitar que Adobe rastree visitantes frecuentes. Esta función permite que usted y sus colegas visiten el sitio sin distorsionar los datos de tráfico. Puede excluir hasta 50 direcciones IP diferentes.

Puede utilizar indicadores comodín (*) para excluir un rango de direcciones. Por ejemplo, `[!DNL 0.0.*.0]` excluiría todas las direcciones IP entre `[!DNL 0.0.0.0]` y `[!DNL 0.0.255.0]`. Puede excluir hasta 50 direcciones IP diferentes.

## Excluir por servidor de seguridad {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

También se puede bloquear la recopilación de datos de direcciones IP específicas a través de un cortafuegos.

Consulte el artículo Direcciones [IP utilizadas en Experience Cloud](https://marketing.adobe.com/resources/help/es_ES/home/index.html#kb-adobe-ip-addresses) .

## Influencia de la confusión de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP.

Si se elimina el último octeto, esto se realiza antes del filtrado de IP. Como tal, el último octeto se reemplaza por un 0 y las reglas de exclusión de IP deben actualizarse para que coincidan con las direcciones IP con un cero al final. Un * coincidente debe corresponder a un 0.
