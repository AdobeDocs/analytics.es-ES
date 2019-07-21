---
description: Cuando un informe tiene una gran cantidad de valores únicos, Adobe proporciona funcionalidad para garantizar que los valores más importantes aparezcan en el informe.
seo-description: Cuando un informe tiene una gran cantidad de valores únicos, Adobe proporciona funcionalidad para garantizar que los valores más importantes aparezcan en el informe.
seo-title: Valor de poco tráfico en Adobe Analytics
solution: Analytics
title: Valor de poco tráfico en Adobe Analytics
topic: Métricas
uuid: 56 f 723 f 8-94 e 8-478 f -8 ea 3-16 dad 21 dfa 1 f
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Valor de poco tráfico en Adobe Analytics

Cuando un informe tiene una gran cantidad de valores únicos, Adobe proporciona funcionalidad para garantizar que los valores más importantes aparezcan en el informe. Unique variable values collected after approximately 500,000 existing values are listed under a line item titled **(Low-Traffic)**.

## Funcionamiento de poco tráfico

* Los informes no se ven afectados si la variable no alcanza los 500 000 valores únicos en un mes determinado.
* Cuando una variable alcanza este primer umbral de 500.000, los datos empiezan a estar agrupados bajo poco tráfico. Cada valor más allá de este umbral lleva a través de la lógica siguiente:
   * Si ya hay un valor en los informes, agregue al valor como de costumbre.
   * Si un valor aún no está en los informes, compruebe si ese valor se ha visto más de diez veces hoy mismo. Si lo tiene, agregue este valor a los informes. Si no se cuenta más de diez veces, déjelo bajo poco tráfico.
* Si un grupo de informes alcanza más de 1000.000 valores únicos, se aplica un filtrado más agresivo:
   * Si ya hay un valor en los informes, agregue al valor como de costumbre.
   * Si un valor aún no está en los informes, compruebe si ese valor se ha visto más de 100 veces hoy mismo. Si lo tiene, agregue el valor a los informes. Si no lo tiene, déjelo bajo poco tráfico.

> [!NOTE] Si un valor de variable recibe tráfico suficiente para abandonar el contenedor de poco tráfico, los primeros valores recopilados no se moverán a su elemento de línea respectivo. Estas primeras 10-100 instancias permanecen bajo poco tráfico.

## Cambio de umbrales de límite únicos

De forma predeterminada, estos umbrales son 500 000 y 1 millón de valores únicos. Estos límites se pueden cambiar por variable. Póngase en contacto con el administrador de cuentas de su organización para solicitar este cambio. Al solicitar un cambio, incluya:

* La ID del grupo de informes
* La variable que desee incrementar el umbral de
* El primer y el segundo umbral deseado

Este cambio puede tener un costo adicional y depende del contrato. Los cambios en los umbrales también pueden afectar el rendimiento del informe. Adobe recomienda encarecidamente utilizar un buen juicio al solicitar un aumento de valores únicos en una variable.

Los umbrales de poco tráfico no son visibles en la interfaz de usuario de Analytics. Pida a un usuario de asistencia técnica de su organización que se ponga en contacto con el Servicio de atención al cliente si desea obtener más información sobre los umbrales existentes.

## Poco tráfico mediante componentes y otras funciones

Distintas funciones tratan los valores de poco tráfico de diferentes maneras.

* **Almacén de datos:** No hay límite en la cantidad de valores únicos en los informes del Almacén de datos. Su arquitectura única permite informar de cualquier cantidad de valores únicos.
   * En algunos escenarios limitados, los valores de poco tráfico todavía pueden aparecer. Algunos ejemplos son: vars de lista, props de lista, evars de comercialización y dimensiones de detalles de canal de mercadotecnia.
* **Segmentación:** Si los criterios de segmento incluyen una variable con un número elevado de valores únicos, no se incluyen los valores capturados bajo poco tráfico.
* **Clasificaciones:** Los informes de clasificación también están sujetos a límites únicos. Si el valor de la variable principal de una clasificación se incluye bajo poco tráfico, el valor no se clasifica.
   * Si clasifica valores antes de que se vean en los datos, esos valores se contabilizarán en el umbral único de ese mes.
