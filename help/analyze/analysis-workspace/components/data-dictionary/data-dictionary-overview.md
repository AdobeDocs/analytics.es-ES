---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y realizar un seguimiento de los distintos componentes de Analysis Workspace, incluido el uso deseado, que se aprueban, que son duplicados, etc.
title: Resumen del diccionario de datos
feature: Components
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: d8442f1ec8f35fbcda98b35070936677813ce330
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Resumen del diccionario de datos

{{release-limited-testing}}

El diccionario de datos de Analysis Workspace ayuda a los usuarios y administradores a realizar un seguimiento de los componentes de su entorno de Analytics y a comprenderlos mejor.

Los administradores de Analytics son responsables de conservar la información sobre cada componente en el diccionario de datos para que esté disponible para los usuarios.

## Ventajas para los usuarios

El diccionario de datos ayuda a los usuarios a comprender mejor cada componente que tienen a su disposición.

La información disponible en el diccionario de datos incluye:

* Función de un componente y uso previsto

* Componentes que se utilizan normalmente con el que está viendo

* Componentes similares al que está viendo

* Si el administrador del sistema aprueba un componente

Para obtener información sobre cómo acceder al diccionario de datos y para obtener detalles sobre la información que contiene, consulte [Ver información de componentes en el diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Ventajas para los administradores

El diccionario de datos ayuda a los administradores de sistemas a realizar un seguimiento de los componentes de su entorno de Analytics y a depurarlos.

A continuación se indican algunas de las formas en que los administradores de Analytics pueden utilizar el diccionario de datos:

* Identifique los componentes duplicados que deben consolidarse.

* Identifique los componentes que no recopilan datos para que se puedan actualizar o eliminar.

* Identificar los componentes que aún no se han aprobado.

* Actualice las descripciones de los componentes directamente en Analysis Workspace. Las actualizaciones realizadas en las descripciones de los componentes del diccionario de datos se reflejan en el grupo de informes.

   Del mismo modo, cualquier actualización realizada en las descripciones de los componentes del grupo de informes se refleja en Analysis Workspace.

   Para obtener más información sobre la adición de descripciones de componentes en Analysis Workspace o en un grupo de informes, consulte [Agregar descripciones de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Acceso al diccionario de datos

Puede acceder al diccionario de datos de cualquiera de las siguientes maneras en Analysis Workspace:

* En el **Diccionario de datos** en el carril izquierdo.

   ![Icono del diccionario de datos en el carril izquierdo](assets/data-dictionary-access-icon.png)

* En el **Diccionario de datos** dentro de la ventana emergente de información de un componente.

   ![Icono del diccionario de datos en la ventana emergente de información](assets/data-dictionary-access-infopopover.png)
<!--update screenshot; this was taken from a mock-->

* Desde el menú: [!UICONTROL **Ayuda**] > [!UICONTROL **Diccionario de datos**].

Para obtener información detallada sobre las distintas opciones disponibles en el diccionario de datos, consulte [Ver información de componentes en el diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Actualizar y depurar el diccionario de datos

Los administradores de Analytics son responsables de mantener un diccionario de datos correcto para su organización, tal como se describe en [Monitorizar el estado del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).

Como parte de este proceso, los administradores de Analytics pueden editar información sobre cada componente en el diccionario de datos, tal como se describe en [Editar entradas de componentes en el diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

## Mover, minimizar o cerrar el diccionario de datos

Cuando abra el diccionario de datos (como se describe en [Acceso al diccionario de datos](#access-the-data-dictionary)), se muestra como una ventana en la parte superior de Analysis Workspace.

Puede manipular la ventana Diccionario de datos de cualquiera de estas formas:

* Arrástrela a cualquier área dentro de Analysis Workspace

   Si cierra y vuelve a abrir Analysis Workspace, la ventana Diccionario de datos permanece en la ubicación donde la movió por última vez. <!--True?-->

* Minimizar

   Cuando se minimiza, el diccionario de datos aparece como una ficha azul en la esquina inferior derecha de Analysis Workspace.

   Al seleccionar la ficha azul, el diccionario de datos se abre con el componente que estaba viendo más recientemente.

* Cierra
