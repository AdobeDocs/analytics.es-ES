---
description: Cuando un informe contiene una gran cantidad de valores únicos, una funcionalidad incluida en Adobe permite asegurar que los valores más importantes aparezcan en el informe.
title: Valor de poco tráfico en Adobe Analytics
topic: Metrics
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '508'
ht-degree: 100%

---


# Valor de poco tráfico en Adobe Analytics

Cuando un informe contiene una gran cantidad de valores únicos, una funcionalidad incluida en Adobe permite asegurar que los valores más importantes aparezcan en el informe. Los valores de variables únicas recopilados después de aproximadamente 500 000 valores existentes se enumeran con un elemento de línea titulado **(Poco tráfico)**.

## Funcionamiento de poco tráfico

* La creación de informes no se ve afectada si la variable no alcanza los 500 000 valores únicos en un mes determinado.
* Cuando una variable alcanza el primer umbral de 500 000, los datos comienzan a agruparse en bloques de poco tráfico. Todos los valores que superan este umbral se rigen por la siguiente lógica:
   * Si un valor ya figura en los informes, agréguelo como de costumbre.
   * Si un valor todavía no está en los informes, compruebe si ese valor se ha visto más de unas diez veces en la fecha actual. En caso afirmativo, agregue este valor al sistema de informes. Si no se ha contabilizado más de diez veces aproximadamente, déjelo clasificado como poco tráfico.
* Si un grupo de informes alcanza más de 1 000 000 de valores únicos, se aplica un filtrado más intenso:
   * Si un valor ya figura en los informes, agréguelo como de costumbre.
   * Si un valor todavía no está en los informes, compruebe si se ha visto más de unas cien veces en la fecha actual. En caso afirmativo, agregue este valor al sistema de informes. En caso negativo, déjelo clasificado como poco tráfico.

>[!NOTE]
>
>Si un valor de variable recibe tráfico suficiente para dejar el bloque de poco tráfico, los primeros valores recopilados no se mueven a su elemento de línea correspondiente. Estas primeras diez a cien correspondencias permanecen como poco tráfico.

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
   * Si se clasifican los valores antes de que se vean en los datos, estos valores se contabilizan en el umbral único de ese mes.
