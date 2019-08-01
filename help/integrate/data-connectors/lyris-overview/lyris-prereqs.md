---
description: Describe los requisitos previos para una integración exitosa.
seo-description: Describe los requisitos previos para una integración exitosa.
seo-title: Requisitos previos de integración
solution: Analytics
title: Requisitos previos de integración
uuid: ac 93 bf 4 d-a 071-4 fac -9 d 42-c 4856463 cbb 6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Integration Prerequisites{#integration-prerequisites}

Describe los requisitos previos para una integración exitosa.

Antes de activar esta integración, revise los siguientes elementos comparándolos con las implementaciones de Adobe Analytics y el software de correo electrónico.

Esto garantiza que las prácticas recomendadas y los prerrequisitos apropiados estén presentes antes de la activación, lo que dará como resultado una integración óptima y exitosa.

## Prerequisites for Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Grupo de informes específico**: Tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración
* **Variables de Analytics disponibles y configuradas**: Esta integración requiere eventos personalizados y evars personalizadas, y opcionalmente eventos adicionales y evars adicionales.

   See [Configure Analytics variables for Lyris](../lyris-overview/lyris-analytics-variables.md#task-e70a62dc096d4f548d5070a67822f5e7)

* **Representante autorizado**: Tenga en cuenta que la habilitación de esta integración podría ocasionar que su empresa incurra en gastos conforme al contrato de servicio con Adobe, Inc. o su contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara que es un representante autorizado de su empresa; y, como tal, su empresa acepta pagar las tarifas, en su caso, en el contrato de servicio descrito anteriormente.
* **Almacén de datos de Adobe Analytics**: Esta integración requiere que el almacén de datos de Adobe Analytics esté habilitado para generar segmentos de remarketing. Si no ha habilitado el almacén de datos, póngase en contacto con Adobe para obtener más información.
* **ID del destinatario**: La integración requiere que capture y almacene un "ID de visitante" dentro de una variable de Analytics (evar). El ID de visitante (denominado generalmente «ID de destinatario») es una representación numérica o codificada de una dirección de correo electrónico del sistema Lyris. Este "ID de destinatario" está asociado con el comportamiento de los visitantes en línea en el sitio (abandonos del carro, compras, etc.) que se devuelven al sistema Lyris y se pueden aprovechar para remarketing. Como parte del proceso de configuración, debe identificar una evar para este propósito cuando el asistente lo solicite.
* **Seguimiento externo**: Si actualmente no sigue la mejor práctica para habilitar el seguimiento externo para cada campaña de correo electrónico que envíe, debe hacerlo para garantizar una integración exitosa. Consulte la sección Lyris para obtener más detalles
* **Cumplimiento de privacidad**: Debe comprender que, al habilitar el seguimiento de ID de visitantes o visitantes, es posible que este dispositivo rastree información personal de los visitantes del sitio. Esto tiene implicaciones de privacidad, que requieren la implementación de las medidas adecuadas por parte de su organización, como proporcionar aviso y consentimiento a los visitantes del sitio.

## Prerequisites for Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Cuenta válida de Lyris**: Para utilizar esta integración de Conector de datos, debe tener una cuenta válida de Lyris.
* **Información de la cuenta**: Necesitará la siguiente información sobre su cuenta de Lyris durante esta configuración de integración:

   * *Clave de API de Lyris*: Se utiliza para la población de datos
   * *Parámetros de cadena de consulta*: Se anexan en la URL de la página de aterrizaje para ID de mensaje y ID de destinatario (ID de visitante).
   * *Lyris Server/URL*: El valor del servidor que utiliza en el sistema Lyris
   * *ID del sitio de Lyris*: También conocido como «ID de cliente», es el valor único de su instancia de Lyris HQ. Puede encontrarse en «Información del cliente» en la sección «Página principal de la cuenta» de emaillabs.

