---
description: Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos elimina los datos de las direcciones IP para conseguir mayor precisión en los informes. También es posible eliminar datos de ataques de negación de servicio u otros eventos dañinos que pueden distorsionar los datos de los informes. Puede configurar la exclusión o utilizar el cortafuegos.
title: Excluir por dirección IP
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '554'
ht-degree: 100%

---


# Excluir por dirección IP

Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos elimina los datos de las direcciones IP para conseguir mayor precisión en los informes. También es posible eliminar datos de ataques de negación de servicio u otros eventos dañinos que pueden distorsionar los datos de los informes. Puede configurar la exclusión o utilizar el cortafuegos.

**[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Excluir por dirección IP]**

>[!NOTE]
>
>Las visitas excluidas por dirección IP se facturan como [llamadas al servidor](https://docs.adobe.com/content/help/es-ES/analytics/technotes/terms.html).

## Excluir por cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Permite excluir a un ordenador del seguimiento que se realiza en su cuenta. Si se decide excluir un equipo, no se tendrán en cuenta los datos generado en él.

Esta función permite al usuario y a sus compañeros visitar el sitio sin distorsionar los datos del tráfico. Esta función puede resultar útil si el usuario no dispone de una dirección IP estática (por ejemplo, si tiene una conexión a Internet de acceso telefónico a través de un proveedor de servicios) y desea excluirse de los datos de su cuenta.

| Elemento | Descripción |
|--- |--- |
| [!UICONTROL Agregar CNAME] | Genera un vínculo de no participación con el que puede excluirse un dominio. Para obtener ayuda, póngase en contacto con los usuarios de asistencia técnica de la empresa. <br>Puede excluirse el tráfico para que no quede registrado en los grupos de informes desde la página de exclusión de la empresa, donde puede especificarse la exclusión del explorador de la medición. <br>Si la implementación utiliza cookies de terceros, la página de exclusión estará [aquí](https://democorp.112.2o7.net/optout.html?locale=es_ES&amp;popup=true). |

>[!NOTE]
>
>La exclusión por equipo solo funcionará si:
>
> * Se accede al sitio web desde la misma estación de trabajo.
> * Se habilitan las cookies en el explorador en uso.
> * No se eliminan las cookies del usuario (de hacerlo, el usuario deberá excluirse de nuevo).


## Excluir por dirección IP {#section_609FB6461529409D840111A32FEF5C3D}

Una dirección IP es una dirección de Internet. Todos los usuarios de Internet tienen asignadas direcciones IP numéricas (por lo general, a través de proveedores de servicios de Internet) que actúan de forma efectiva como identificadores electrónicos.

Mediante las direcciones IP, se contabilizan las vistas de página y se identifican los visitantes de página únicos. Si se excluyen de la contabilización algunas direcciones IP, se puede evitar que Adobe realice un seguimiento de los visitantes frecuentes. Esta función permite al usuario y a sus compañeros visitar el sitio sin distorsionar los datos del tráfico. Pueden excluirse hasta 50 direcciones IP diferentes.

Pueden utilizarse indicadores comodín (*) para excluir un intervalo de direcciones. Por ejemplo, `[!DNL 0.0.*.0]` excluiría todas las direcciones IP entre `[!DNL 0.0.0.0]` y `[!DNL 0.0.255.0]`. Puede excluir hasta 50 direcciones IP diferentes.

## Excluir por servidor de seguridad {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

También se puede bloquear la recopilación de datos de direcciones IP específicas a través de un cortafuegos.

Consulte el artículo [Direcciones IP utilizadas en Experience Cloud](https://helpx.adobe.com/es/analytics/kb/adobe-ip-addresses.html).

## Influencia de la confusión de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP.

Si se elimina el último octeto, será antes del filtrado de la IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un * coincidente debe corresponder a un 0.
