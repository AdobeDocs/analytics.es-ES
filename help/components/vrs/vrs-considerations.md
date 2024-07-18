---
description: Los grupos de informes virtuales y el etiquetado de grupos múltiples tienen diferentes ventajas. Aprenda cuál es la mejor opción para su organización.
keywords: Grupo de informes virtuales
title: Grupos de informes virtuales y consideraciones sobre el etiquetado de grupos múltiples
feature: VRS
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
source-git-commit: 6e9ea48df286b2bde6a071ab3d0f29a764382c6d
workflow-type: tm+mt
source-wordcount: '1636'
ht-degree: 79%

---

# Grupos de informes virtuales y consideraciones sobre el etiquetado de grupos múltiples

Los grupos de informes virtuales le permiten ver datos de un grupo de informes que recopila datos de sus propiedades digitales, pero con un segmento aplicado de forma permanente.

En muchos casos, puede utilizar grupos de informes virtuales para reemplazar el etiquetado de grupos múltiples. Cambiar a grupos de informes virtuales puede eliminar de forma efectiva la necesidad de realizar [llamadas secundarias al servidor](/help/admin/admin/c-server-call-usage/overage-overview.md). Por ejemplo: su organización tiene 6 sitios web diferentes, cada uno de los cuales envía datos a su propio grupo de informes, así como a un grupo de informes globales combinados. Cada sitio realiza una llamada secundaria al servidor, una al grupo de informes de marca individual y otra al grupo de informes globales. En su lugar, puede enviar datos de todos los sitios únicamente al grupo de informes globales y, a continuación, utilizar varios grupos de informes virtuales para separar cada marca.

La sustitución del etiquetado de grupos múltiples con un grupo de informes globales y un grupo de informes virtuales le permite simplificar la implementación de Adobe Analytics y reducir el consumo de llamadas al servidor. Además, se aconseja como práctica recomendada. Sin embargo, hay algunas limitaciones importantes de los grupos de informes virtuales que hay que tener en cuenta. Las siguientes directrices le ayudarán a decidir si la implementación de grupos de informes virtuales creados en un grupo de informes global es la estrategia adecuada.

## Directrices

Si no está seguro de si los casos de uso descritos se aplican a usted y a su organización, consulte con los demás administradores de Adobe Analytics o con el equipo de cuenta de Adobe. Pueden ayudarle a evaluar las necesidades de la empresa y recomendarle la mejor solución.

Tenga en cuenta las siguientes consideraciones a la hora de determinar si debe utilizar el etiquetado de grupos múltiples o los grupos de informes virtuales:

### Publicación de segmentos en Adobe Experience Cloud

Con los grupos de informes virtuales no se pueden compartir segmentos con Adobe Experience Cloud. Los usuarios que deseen compartir un segmento con Experience Cloud deben tener acceso al grupo de informes de origen.

Los segmentos no se pueden publicar en Adobe Experience Cloud desde un grupo de informes virtual para su personalización y segmentación. Todos los usuarios que publiquen segmentos deben tener acceso a un grupo de informes para este fin. Por ejemplo, quiere que los usuarios solo tengan acceso a los datos de su región geográfica, pero quiere que puedan crear y compartir segmentos de Adobe Analytics en Adobe Experience Cloud para realizar la segmentación en Adobe Target. En este caso, Adobe recomienda utilizar el etiquetado de grupos múltiples. Si no le importa que los usuarios tengan acceso al grupo de informes globales o no necesita publicar segmentos para usarlos en otras soluciones, se pueden utilizar los grupos de informes virtuales.

### Límites únicos (poco tráfico)

Si tiene un grupo de informes globales que combina un gran número de sitios juntos, es posible que se encuentre con el elemento de línea de [poco tráfico](/help/technotes/low-traffic.md) con frecuencia. Si usa etiquetado de grupos múltiples, esto es solo un problema para el grupo de informes globales (es menos probable que los grupos de informes individuales vean poco tráfico). Si utiliza grupos de informes virtuales, se comparten límites únicos, lo que provoca que los grupos de informes individuales también muestren poco tráfico. Considere utilizar el etiquetado de grupos múltiples si desea evitar agrupar los datos en bloques de poco tráfico.

Por ejemplo, una organización de medios de gran tamaño posee 100 propiedades web. Cada propiedad publica algunos miles de artículos de noticias al mes, además de alojar todos los artículos de meses anteriores. Esta organización utiliza un grupo de informes globales donde eVar1 es “Nombre del artículo”. Supongamos que en este informe hay aproximadamente 5 millones de nombres de artículos únicos por mes de las diversas propiedades combinadas. Si se utiliza un grupo de informes virtuales, solo se incluirá en el grupo de informes virtuales una parte de los 5 millones de valores. Los restantes se incluyen en poco tráfico. Si se utiliza el etiquetado de grupos múltiples, cada grupo de informes individual puede ver su propio conjunto de valores únicos.

Adobe El Servicio de atención al cliente a veces puede aumentar los límites de valor único para un pequeño número de dimensiones, lo que puede eliminar este problema por completo. Para obtener más información, consulte con su equipo de cuenta y con el servicio de atención al cliente.

### Compartir variables entre grupos de informes

Los grupos de informes virtuales no tienen conjuntos de dimensiones y métricas propios, sino que los heredan de su grupo de informes principal. El grupo de informes globales debe capturar todas las dimensiones y métricas de todos los sitios web. Actualmente, los grupos de informes tienen un máximo de 250 eVars y 1000 eventos personalizados.

Cada sitio tiene diferentes necesidades de implementación. Algunas dimensiones y eventos se pueden compartir entre dos sitios. Por ejemplo, un registro por correo electrónico puede utilizar el mismo evento en varios sitios web, lo que activa el mismo evento personalizado. Otras dimensiones pueden ser específicas de un sitio. Por ejemplo: solo uno de los sitios tiene la capacidad de que el usuario cambie su imagen de perfil. Este evento personalizado solo se implementa en el sitio web que lo admita.

Asegúrese de que el número de dimensiones y métricas únicas se pueda ajustar a un único grupo de informes globales. Si descubre que hay demasiadas dimensiones o métricas únicas, revise cada dimensión dentro de cada implementación. Es probable que haya superposición y dimensiones que no sean cruciales para el éxito del negocio. Considere también utilizar [las clasificaciones](/help/components/classifications/c-classifications.md). Por ejemplo, en lugar de capturar el “Nombre de producto” en eVar5, cree una clasificación de “Nombre de producto” basada en la dimensión “Producto”. Las clasificaciones de un grupo de informes de origen están disponibles automáticamente para todos los grupos de informes virtuales dependientes.

>[!TIP]
>
>Con la introducción de [revisión](/help/analyze/analysis-workspace/curate-share/curate.md), puede cambiar el nombre de una dimensión o métrica determinada por grupo de informes virtuales.

### Matices de segmentación

Un grupo de informes virtuales a un nivel fundamental no es más que un segmento aplicado a un grupo de informes. Las dimensiones basadas en visitas y visitantes pueden proporcionar resultados de informes poco intuitivos.

Por ejemplo: tiene dos sitios web, A y B, que envían datos a un grupo de informes globales. Algunos visitantes inevitablemente pasan del sitio A al sitio B y este movimiento de uno a otro es visible en las rutas del grupo de informes globales. Si genera grupos de informes virtuales para los sitios A y B, una visita que comenzó en el sitio A y terminó en el sitio B no mostrará una página de entrada en el grupo de informes virtuales B. La página de entrada para esta visita comenzó en el sitio A, que se segmenta fuera del grupo de informes virtuales.

### Conversión de moneda

Los grupos de informes virtuales no pueden crear informes en una moneda distinta a la del grupo de informes en el que están basados. Adobe Analytics le permite convertir divisas cuando se ejecutan informes, pero la tasa de cambio se basa en el día actual, incluso para los datos históricos.

Que su organización realiza los análisis en una sola moneda no causa ningún problema. Sin embargo, si tiene una necesidad comercial significativa para diferentes equipos regionales que necesitan ver los ingresos en su propia moneda local, considere la posibilidad de utilizar el etiquetado de grupos múltiples.

### Fuentes de datos

Las fuentes de datos no pueden utilizar grupos de informes virtuales. Sin embargo, puede recibir una fuente de datos de un grupo de informes globales y luego separarla.

Las fuentes de datos le permiten recibir una exportación diaria o por hora de todos sus datos de Adobe Analytics a nivel de visita individual. Las fuentes de datos no se pueden segmentar previamente antes de que se le entreguen, por lo que solo puede recibir una fuente de datos para su grupo de informes globales. Si su organización tiene una gran necesidad de fuentes de datos individuales en un nivel granular, de marca, propiedad, región u otro, considere la posibilidad de utilizar el etiquetado de grupos múltiples.

### Data Connectors con cuentas de socio

Ciertas integraciones de socios de Adobe en Adobe Analytics están limitadas a una cuenta de socio por grupo de informes. Algunas organizaciones podrían requerir varias cuentas de socios para la misma integración.

Por ejemplo, solo se permite un DCM de Google por grupo de informes. Muchas empresas tienen varias cuentas de DCM, lo que permite a diferentes marcas, unidades de negocio y regiones administrar sus anuncios en pantalla de forma independiente entre sí. Las integraciones no se pueden configurar en grupos de informes virtuales. Si tiene Data Connectors dependientes con varias cuentas, considere la posibilidad de utilizar el etiquetado de grupos múltiples.

### Fuentes de datos de resumen

Las fuentes de datos de resumen le permiten importar métricas agregadas a nivel de grupo de informes a Adobe Analytics. Como las cargas de fuentes de datos de resumen contienen métricas agregadas *sin un ID de visitante*, no se pueden segmentar en los contenedores [!UICONTROL Visita] y [!UICONTROL Visitante]. Dado que el grupo de informes virtuales funciona mediante la segmentación, los datos importados mediante fuentes de datos de resumen no estarán disponibles en los grupos de informes virtuales si el segmento se crea con un contenedor de visita o visitante.

Las fuentes de datos de resumen se muestran en el grupo de informes virtual si se utiliza un contenedor de visita individual y si este tiene reglas condicionadas para incluir la información de la fuente de datos.

>[!TIP]
>
>Las fuentes de datos de procesamiento completo admiten la segmentación y pueden utilizarse en grupos de informes virtuales.

## Pasos a seguir si ha decidido utilizar el grupo de informes virtuales

Si opta por eliminar llamadas secundarias al servidor en favor de los grupos de informes virtuales:

1. Cree grupos de informes virtuales de modo que coincidan con los datos en los grupos de informes secundarios. Segmente en una dimensión personalizada que distinga los sitios entre sí.
   * Si migra desde una implementación con etiquetado de grupos múltiples que ya existe, compare los segmentos del grupo de informes virtuales con los grupos de informes secundarios existentes. Antes de mover usuarios al grupo de informes virtuales, debe asegurarse de que los datos sean comparables.
   * Se recomienda utilizar el [apilamiento de segmentos](/help/components/segmentation/segmentation-workflow/seg-build.md) para poder editar un segmento en una ubicación y aplicarlo a todos los grupos de informes virtuales dependientes.
   * Utilice contenedores de visita si desea que los grupos de informes virtuales sean más excluyentes de manera mutua.
2. Después de confirmar que los grupos de informes virtuales están correctamente configurados, elimine los ID del grupo de informes secundario de la implementación. Para eliminar los grupos de informes secundarios:
   * En la extensión de Adobe Analytics dentro de la recopilación de datos de Adobe Experience Platform, haga clic en la &quot;x&quot; junto a los grupos de informes que ya no desee utilizar.
   * En implementaciones de JavaScript antiguas, ubique la variable `s.account` y elimine todos los ID de los grupos de informes que ya no desee usar.
   * En todos los casos, deje solo el ID del grupo de informes global/principal para recopilar datos para sus sitios y aplicaciones.
   * Vaya a Administración > Grupos de informes y oculte los grupos de informes secundarios que ya no se utilicen.
