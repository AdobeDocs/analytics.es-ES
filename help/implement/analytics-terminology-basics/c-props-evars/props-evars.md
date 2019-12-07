---
description: Las variables de tráfico personalizado, también denominadas propiedades (s.prop) o variables de propiedad, son contadores que contabilizan el número de veces que cada valor se envía a Analytics.
keywords: Analytics Implementation;Traffic prop;prop;conversion;evar;s.prop;custom conversion insight;traffic variable
title: Resumen de props y eVars
topic: Developer and implementation
uuid: 522cab2b-1ef8-4f10-b216-c82b21431487
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen de props y eVars

Las variables de tráfico personalizado, también denominadas propiedades (s.prop) o variables de propiedad, son contadores que contabilizan el número de veces que cada valor se envía a Analytics.

Para determinar qué variables se asignan y dónde, es importante conocer las diferencias entre la funcionalidad prop y eVar. Entender estas diferencias permite a la organización decidir qué tipo de variable es mejor utilizar. Para obtener más información, consulte [Comparación de props y eVars](/help/implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md).

Las propiedades también permiten correlacionar datos personalizados con eventos relativos al tráfico. Estas variables están incorporadas en el código de [!DNL Analytics] en cada página del sitio web. Con las variables [!UICONTROL s.prop], [!DNL Analytics] permite crear informes personalizados, exclusivos de su organización, sector y objetivos empresariales.

Por ejemplo, si usted es fabricante de automóviles, quizás le interese ver "Modelo de automóvil más popular" para complementar el informe "Páginas". Para ello, puede asignar una de las propiedades de tráfico para representar el modelo de automóvil. Después, implemente el código para pasar el modelo de automóvil a las páginas correspondientes.

> [!NOTE] [!DNL Analytics] admite hasta 75 variables [!UICONTROL s.prop].

Las props se utilizan en informes de rutas o en informes de correlación. Por ejemplo: las variables de [!UICONTROL propiedad] pueden utilizarse para mostrar el tipo de contenido, la subsección o el nombre de la plantilla. El informe [!UICONTROL Tráfico personalizado] resultante muestra el tipo de contenido, la subsección o la plantilla que se ve con más frecuencia.

Hay innumerables preguntas comerciales que se pueden responder mediante variables de tráfico personalizado, en función de los datos que capture en su sitio web. La siguiente lista contiene algunos objetivos habituales:

* Comprender la navegación de los usuarios por el sitio web
* Comprender el comportamiento de búsqueda de los usuarios
* Segmentar el tráfico por navegación o categoría
* Segmentar el comportamiento de los visitantes por demografía

Las eVars (o variables de [!UICONTROL perspectiva de conversión personalizada]) se utilizan para identificar en qué medida contribuyen atributos o acciones específicos a los eventos de éxito del sitio. Por ejemplo, en un sitio multimedia, las eVars se pueden usar para identificar en qué medida las promociones internas llevan a los visitantes a registrarse. Cuando un visitante hace clic en la promoción interna, se puede usar una eVar para almacenar un identificador único para dicha promoción. Cuando el mismo visitante completa el registro y se activa un evento de éxito personalizado, el identificador único original recibe el crédito por el evento de registro.

En un sitio de conversión, las eVars se pueden usar para realizar el seguimiento de las diferencias entre los visitantes que han iniciado sesión y los que no a la hora de completar una compra. Cuando un visitante inicia sesión, se configura una eVar como "sesión iniciada". Cuando ese visitante llega a la página de cierre de compra, el evento de cierre de compra se atribuye al valor "sesión iniciada". Cuando un visitante llega a la página Gracias después de la compra, los productos y las cantidades de productos se atribuyen al valor "sesión iniciada". El informe [!UICONTROL eVar personalizada] resultante muestra el número total de cierres de compra y pedidos para los visitantes "sesión iniciada" y "sesión no iniciada".

Para obtener más información, consulte [Variable de tráfico](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html) en la Ayuda y referencia de Analytics.

Para obtener información sobre la configuración de propiedades en Digital Tag Management, consulte [Crear una propiedad web](/help/implement/c-implement-with-dtm/t-create-web-property.md).
