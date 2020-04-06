---
description: Importe datos de seguimiento de aplicaciones de terceros en Analytics.
title: Introducción a Data Connectors de Analytics
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Descripción general de Data Connectors

Adobe proporciona a las organizaciones información práctica en tiempo real con respecto a las estrategias digitales y a las iniciativas de marketing. Data Connectors permite importar datos de seguimiento de aplicaciones de terceros en Analytics, de modo que puede recopilar y usar datos desde una ubicación central. Si usa uno de los productos asociados, puede crear una integración que importa los datos de la aplicación a los informes de marketing. Una vez integrados, puede generar informes que incluyan datos de la aplicación.

Por ejemplo, una integración de correo electrónico que desee utilizar un socio de correo electrónico para distribuir una campaña por correo electrónico. Cuando los visitantes llegan a su página web, usted quiere saber quiénes han llegado hasta ella en respuesta a su campaña por correo electrónico. Data Connectors integra los datos de su socio de correo electrónico en los informes de marketing para que pueda determinar esta información para medir la eficacia de su campaña por correo electrónico.

**Requisitos del sistema**

Data Connectors debería integrarse apropiadamente con los exploradores más populares. Sin embargo, los informes se ven y funcionan mejor en sistemas que cumplen las siguientes recomendaciones:

* Explorador: Microsoft Internet Explorer versión 6 y posterior
* Cookies: Requerido
* JavaScript: Habilitado
* Sistema operativo: Basado en Windows
* Macromedia Flash Player: versión 6 o superior
* Resolución del monitor: 1024 x 768 (800 x 600 funcionará)
* Profundidad de color: 16 bits o superior

Adicionalmente, la colección de datos mejora cuando los exploradores web de los usuarios tienen JavaScript habilitado.

**Requisitos previos**

Antes de configurar la integración de Data Connectors para su producto, haga lo siguiente:

* Tenga a mano las credenciales de acceso necesarias para la cuenta del producto del socio, con derechos para acceder a todos los datos que desee integrar con informes de marketing. Es posible que desee crear una cuenta de correo electrónico especial para los distribuidores de informes y para las notificaciones relativas a las operaciones integradas.
* Identifique las variables personalizadas que contienen la información de su campaña. Esto se conoce comúnmente como el código de seguimiento de campañas, pero su organización podría utilizar otra terminología.
* Determine los eventos que desea que reciban impresiones y datos sobre los clics. Es posible que desee cambiar el nombre de los eventos según corresponda.
* Coloque el código adecuado en la página de aterrizaje para que Analytics pueda realizar el modelado adecuado con los datos procedentes del producto asociado. En las Reseñas de Data Connectors en la pestaña Recursos, encontrará instrucciones específicas para cada producto asociado.

## Añadir una integración

Debe tener una cuenta actual para acceder a la página de aterrizaje de [!UICONTROL Data Connectors] (consola). También es aconsejable que esté familiarizado con Adobe Analytics.

1. Inicie sesión en Adobe Experience Cloud.
1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.
1. Haga clic en **[!UICONTROL Add New]**.
1. Avance por la **[!UICONTROL Add Integration]** interfaz.

   En función de la integración de producto individual, puede que deba proporcionar información concreta sobre la configuración como parte del proceso de integración.

   Cuando la integración termina, el icono del producto del socio aparece en la página Red de Data Connectors y está disponible en los menús.

## Consola de Data Connectors

Después de activar una integración, esta se muestra en la página [!UICONTROL Data Connectors]. Puede ver los detalles y realizar cambios de configuración en la consola. Puede ver las integraciones activas y las integraciones de todos los conjuntos de informes de su empresa. También puede ver un registro de actividad, configurar una integración como un panel, configurar una integración y encontrar ayuda.

![Consola de Data Connectors](assets/data-connectors-console.png)

## Segmentos de remarketing en Data Connectors

Los segmentos de remarketing son archivos de datos que se crean en función de las variables usadas en una integración de Data Connectors.

Adobe Analytics los envía en archivos distintos diarios por medio de Data Warehouse a una FTP creada por Adobe para el tercero. A continuación, el tercero distribuye los archivos al cliente. Normalmente, las empresas los utilizan para enfocar el remarketing a quienes posiblemente hayan visitado el sitio web y echado un vistazo al producto sin comprarlo. (Por ejemplo, se pone en contacto con un cliente que ofrece un descuento para un producto que vio pero que no terminó comprándolo).

**Segmentos**

* [!UICONTROL Cart Abandonment]:: El porcentaje de visitantes que agregaron un artículo al carro pero no lo compraron. Técnicamente es una métrica calculada compuesta de pedidos divididos por Añadas del carro de compras.
* [!UICONTROL Purchases]:: Los ID de destinatario (o ID de visitante) que realizaron compras en función del ID de mensaje en un producto específico.
* [!UICONTROL Product Views]:: De manera similar a [!UICONTROL Cart Abandonment], esta es también una métrica calculada. It reports [!UICONTROL Product Views] divided by Orders, because customers&#39; viewing the product shows some interest.

**Ejemplos de implementación**

Para implementar correctamente los segmentos de remercadotecnia, deben cumplirse las siguientes condiciones:

* Se ha establecido un contrato de Data Connectors y su empresa ha completado la fase de implementación con un consultor de Adobe.
* El evento correspondiente se activa al mismo tiempo que la variable products:
   * Abandono del carro de compras: evento `scAdd`
   * Compras: evento `purchase`
   * Vistas del producto: evento `prodView`

>[!NOTE] Si el producto se define sin un evento asociado, el evento prodView se activa automáticamente.
Si no se cumplen los requisitos anteriores, no se informa correctamente de los segmentos de remarketing correspondientes.

[!UICONTROL Cart Abandonment]:: se activa después de que el usuario agrega un producto al carro de compras:

```
s.products=";cat";
s.events="scAdd";
```

[!UICONTROL Purchases]:: se activa en la página de confirmación de compra:

```
s.products=";
cat;1;50";
s.events="purchase";
//Note: Though optional, adding the purchaseID variable increases accuracy by preventing duplicate purchases
```

**Problemas comunes**

| Problema | Descripción |
| -----------| ---------- |  
| No se muestra ninguna información de ID de producto en el archivo de segmento de remarketing. | Esto ocurre cuando se activa el evento correcto, pero no hay ninguna variable de producto en la misma solicitud de imagen. Para corregir esto, asegúrese de que la variable products y el evento correspondiente se activen en la misma página, como se muestra en los ejemplos de implementación anteriores. |
| No se reciben los archivos de segmentos de remercadotecnia. | Si no recibe los archivos, pida a uno de los usuarios de asistencia técnica de su organización que se ponga en contacto con ClientCare para investigar la causa de que los informes no se reciban correctamente. |


>[!IMPORTANT] Es habitual que los consultores también configuren una solicitud de Data Warehouse como un informe diario programado, además de su integración de Data Connectors estándar con el archivo del segmento de remarketing. Esta solicitud de Data Warehouse incluye variables de Data Connectors, así como variables que no sean de este tipo, y se puede programar solo en base a la solicitud específica de su empresa. Para evitar confusiones durante la resolución de problemas, especifique si el archivo en cuestión es el archivo del segmento de remarketing real o bien una solicitud de Data Warehouse que contiene variables que no sean de Genesis.
