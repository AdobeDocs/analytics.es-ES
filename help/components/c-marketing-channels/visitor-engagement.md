---
description: Descubra cómo especificar la caducidad de la interacción del visitante en los Canales de marketing.
subtopic: Marketing channels
title: Caducidad del canal de mercadotecnia
topic: Reports and analytics
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
translation-type: tm+mt
source-git-commit: 46dae8ee28b202578f5ad0c2446b1fd63e5144cc
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 81%

---


# Caducidad del canal de mercadotecnia

Obtenga información sobre cómo especificar la caducidad o el período de compromiso de visitante para los Canales de marketing.

El compromiso del visitante especifica la cantidad de tiempo que desea permitir para que la actividad previa del visitante en su sitio web se atribuya al canal de primer toque. El valor predeterminado de la caducidad es de 30 días.

Si el visitante utiliza el sitio con frecuencia, la ventana de participación se abrirá. Debe estar inactivo durante 30 días para que caduque el periodo y se restablezcan los canales. Los canales de primer y último toque de un visitante se restablecerán tras 30 días de inactividad en ese explorador.

Ejemplo:

* Día 1: el usuario llega al sitio y este aparece en la pantalla. Los canales de primer y último contacto se definirán como “Pantalla”.
* Día 2: el usuario entra al sitio a través de una búsqueda natural. El primer contacto permanece como “Pantalla” y el último contacto se establece como “Búsqueda natural”.
* Día 35: el usuario no ha accedido al sitio en 33 días y regresa usando la pestaña que había abierto en su navegador. Suponiendo que se trate de una ventana de participación de 30 días, la ventana se habría cerrado y las cookies del canal de marketing habrían caducado. El canal de primer contacto y último contacto se restablecerán y se configurarán en Actualización de sesión, ya que el usuario accedió con una URL interna.

## Configuración de caducidad de canal de marketing

La configuración de caducidad consiste en lo siguiente:

| Campo | Definición |
|--- |--- |
| Días de inactividad | Cantidad de días que deben transcurrir antes de que caduque el compromiso de primer toque del visitante. El valor predeterminado es 30. |
| Nunca | El período de compromiso del visitante no caduca. |
| Restablecimiento del canal | Termina todos los periodos de compromiso de los visitantes.  Si necesita restablecer todos los datos de canal de mercadotecnia, puede hacer que expiren todos los períodos de compromiso de los visitantes. Podría necesitar restablecer los datos si las reglas de procesamiento están mal configuradas. Todos los valores de canales de primer y último toque expirarán inmediatamente y se restablecerán cuando vuelvan los visitantes. |

## Definir la caducidad del canal de mercadotecnia {#define-expiration}

Especifique el período de compromiso de visitante.

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.
2. En el [!UICONTROL Administrador del grupo de informes], haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Canales de marketing]** > **[!UICONTROL Expiración de canal de marketing]**.

   ![](assets/mchannel_expiration.png)

3. Configure los campos del período de compromiso de visitante.
4. Haga clic en **[!UICONTROL Guardar]**.

