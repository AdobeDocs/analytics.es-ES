---
description: Cuando un informe contiene una gran cantidad de valores únicos, una funcionalidad incluida en Adobe permite asegurar que los valores más importantes aparezcan en el informe.
title: Valor de poco tráfico en Adobe Analytics
feature: Métricas
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
translation-type: tm+mt
source-git-commit: 65190776da25437e854e0226cd349e3ba13fc8c9
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 48%

---

# Valor de poco tráfico en Adobe Analytics

Cuando un informe tiene muchos valores únicos, Adobe proporciona funcionalidad para garantizar que los valores más importantes aparezcan en el informe. Los valores de variables únicas recopilados después de aproximadamente 500 000 valores existentes se enumeran en un elemento de línea titulado **[!UICONTROL Poco tráfico]**.

## Funcionamiento de [!UICONTROL Low-Traffic]

* La creación de informes no se ve afectada si la variable no alcanza los 500 000 valores únicos en un mes determinado.
* Cuando una variable alcanza el primer umbral de 500 000, los datos comienzan a agruparse en bloques de poco tráfico. Todos los valores que superan este umbral se rigen por la siguiente lógica:
   * Si ya se ve un valor en los informes, agréguelo como de costumbre.
   * Si un valor aún no aparece en los informes, aparecerá en el elemento de línea [!UICONTROL Poco tráfico]. Si un valor que se ha incluido en el elemento de línea [!UICONTROL Tráfico bajo] se ve un número significativo de veces en un corto tiempo, empezará a reconocerse como su propio elemento de línea. El número significativo de veces que se debe ver un elemento tiene muchas dependencias, como el número de servidores de procesamiento y demonios que están procesando datos para ese grupo de informes en particular.
* Si un grupo de informes alcanza más de 1 000 000 de valores únicos, se aplica un filtrado más intenso:
   * Si ya se ve un valor en los informes, agréguelo como de costumbre.
   * Si un valor aún no aparece en los informes, aparecerá en el elemento de línea [!UICONTROL Poco tráfico]. Si un valor que se ha incluido en el elemento de línea [!UICONTROL Tráfico bajo] se ve un número significativo de veces en un corto tiempo, empezará a reconocerse como su propio elemento de línea. El número significativo de veces que se debe ver un elemento tiene muchas dependencias, como el número de servidores de procesamiento y demonios que están procesando datos para ese grupo de informes en particular.

¿Por qué el Adobe mueve un elemento de la línea [!UICONTROL Tráfico bajo] a su propio elemento de línea? Por ejemplo, este movimiento podría reconocer una página nueva o elemento nuevo popular que se agregó más adelante en el mes (después de superar los valores exclusivos) y que recibe muchas visitas o vistas. El movimiento no pretende capturar todo lo que recibe un determinado número de visitas/visitas al día o al mes.

## Cambio de los umbrales de límite único

De forma predeterminada, estos umbrales son 500 000 y 1 millón de valores únicos. Estos límites se pueden cambiar según la variable. Póngase en contacto con el administrador de cuentas de su organización para solicitar este cambio. Al solicitar un cambio, indique:

* El ID del grupo de informes
* La variable para la que solicita aumentar el umbral
* El primer y el segundo umbral deseado

Los cambios en los umbrales pueden afectar al rendimiento del informe. Adobe recomienda usar el buen criterio al solicitar un aumento de valores únicos en una variable.

Los umbrales de poco tráfico no son visibles en la interfaz de usuario de Analytics. Si desea obtener más información sobre los umbrales existentes, pida a un usuario de asistencia técnica de su organización que se ponga en contacto con el Servicio de atención al cliente de Adobe.

## Poco tráfico con componentes y otras funciones

Las diferentes funciones tratan los valores de poco tráfico de diferentes maneras.

* **Data Warehouse:** no hay límite para la cantidad de valores únicos que pueden aparecer en los informes de Data Warehouse. Su arquitectura única permite generar informes de cualquier cantidad de valores únicos.
   * Pueden seguir apareciendo valores de poco tráfico en situaciones limitadas. Por ejemplo: las variables de lista, las props de lista, las eVars de comercialización y las dimensiones de detalle del canal de marketing.
* **Segmentación:** si los criterios del segmento contienen una variable con un número elevado de valores únicos, no se incluyen los valores capturados en tráfico bajo.
* **Clasificaciones:** los informes de clasificación también están sujetos a límites únicos. Si el valor de la variable principal de una clasificación se encuentra en poco tráfico, el valor no se clasifica.
   * Los valores de clasificación de poco tráfico obtenidos mediante el importador se pueden ver en la Data Warehouse. <!-- AN-115871 -->
   * Los valores de clasificación de poco tráfico obtenidos a través del generador de reglas *no se pueden ver en la Data Warehouse. <!-- AN-122872 -->*
