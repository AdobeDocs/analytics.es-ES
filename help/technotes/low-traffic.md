---
description: Cuando un informe tiene una gran cantidad de valores únicos, Adobe proporciona funcionalidad para garantizar que los valores más importantes aparezcan en el informe.
seo-description: Cuando un informe tiene una gran cantidad de valores únicos, Adobe proporciona funcionalidad para garantizar que los valores más importantes aparezcan en el informe.
seo-title: Valor de poco tráfico en Adobe Analytics
solution: Analytics
title: Valor de poco tráfico en Adobe Analytics
topic: Métricas
uuid: 56f723f8-94e8-478f-8ea3-16dad21dfa1f
translation-type: tm+mt
source-git-commit: 22fc459dae1a57a387511560e7039c7085e30551

---


# Valor de poco tráfico en Adobe Analytics

Cuando un informe tiene una gran cantidad de valores únicos, Adobe proporciona funcionalidad para garantizar que los valores más importantes aparezcan en el informe. Los valores de variables únicas recopilados después de aproximadamente 500.000 valores existentes se enumeran bajo un elemento de línea titulado **(Poco tráfico)**.

## Funcionamiento de poco tráfico

* Los informes no se ven afectados si la variable no alcanza los 500.000 valores únicos en un mes determinado.
* Cuando una variable alcanza el primer umbral de 500.000, los datos comienzan a agruparse en bloques con poco tráfico. Cada valor que supera este umbral pasa por la siguiente lógica:
   * Si ya hay un valor en los informes, agréguelo como de costumbre.
   * Si todavía no hay un valor en los informes, compruebe si ese valor se ha visto más de diez veces en la actualidad. Si lo ha hecho, agregue este valor a los informes. Si no se ha contabilizado más de diez veces, déjelo bajo poco tráfico.
* Si un grupo de informes alcanza más de 1.000.000 valores únicos, se aplica un filtrado más agresivo:
   * Si ya hay un valor en los informes, agréguelo como de costumbre.
   * Si todavía no hay un valor en los informes, compruebe si ese valor se ha visto más de 100 veces en la actualidad. Si lo ha hecho, agregue el valor a los informes. Si no lo ha hecho, déjelo bajo poco tráfico.

> [!NOTE] Si un valor de variable recibe tráfico suficiente para dejar el bloque de poco tráfico, los primeros valores recopilados no se mueven a su elemento de línea correspondiente. Esas primeras 10-100 instancias permanecen bajo tráfico.

## Cambio de los umbrales de límite único

De forma predeterminada, estos umbrales son 500 000 y 1 millón de valores únicos. Estos límites se pueden cambiar por variable. Póngase en contacto con el administrador de cuentas de su organización para solicitar este cambio. Al solicitar un cambio, incluya:

* La ID del grupo de informes
* La variable para la que desee aumentar el umbral
* El primer y el segundo umbral deseado

Los cambios en los umbrales pueden afectar al rendimiento del informe. Adobe recomienda usar el buen criterio al solicitar un aumento de valores únicos en una variable.

Los umbrales de poco tráfico no están visibles en la interfaz de usuario de Analytics. Si desea obtener más información sobre los umbrales existentes, pida a un usuario de asistencia técnica de su organización que se ponga en contacto con el Servicio de atención al cliente de Adobe.

## Poco tráfico con componentes y otras capacidades

Las diferentes capacidades tratan los valores de poco tráfico de diferentes maneras.

* **** Almacén de datos: No hay límite en el número de valores únicos en los informes del almacén de datos. Su arquitectura única permite generar informes de cualquier cantidad de valores únicos.
   * En algunos escenarios limitados, aún pueden aparecer valores de poco tráfico. Algunos ejemplos son las variables de lista, las props de lista, las eVars de comercialización y las dimensiones de detalle del canal de mercadotecnia.
* **** Segmentación: Si los criterios del segmento incluyen una variable con un número elevado de valores únicos, no se incluyen los valores capturados en tráfico bajo.
* **** Clasificaciones: Los informes de clasificación también están sujetos a límites únicos. Si el valor de la variable principal de una clasificación se incluye en poco tráfico, el valor no se clasifica.
   * Si clasifica los valores antes de que se vean en los datos, dichos valores se contabilizan en el umbral único de ese mes.
