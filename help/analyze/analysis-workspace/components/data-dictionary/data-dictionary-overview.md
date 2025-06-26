---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y realizar un seguimiento de los distintos componentes de Analysis Workspace, incluido su uso previsto, que se aprueba, que son duplicados, etc.
title: Información general del diccionario de datos
feature: Components
role: User, Admin
exl-id: ecc62287-dc20-41b3-9430-f14ea9fc05e6
source-git-commit: 74ef4e73b6ed1e2a4ad498e2314af704acb6d8cb
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 68%

---


# Información general del diccionario de datos {#data-dictionary-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="Diccionario de datos"
>abstract="El diccionario de datos ayuda tanto a los usuarios como a los administradores a realizar un seguimiento de los componentes de su entorno de Analytics y a comprenderlos mejor. <br/>Los administradores de Analytics son responsables de revisar la información sobre cada componente del diccionario de datos."

<!-- markdownlint-enable MD034 -->


El diccionario de datos de Analysis Workspace ayuda a los usuarios y administradores a seguir los componentes de su entorno de Analytics y a comprenderlos mejor.

Los administradores de Analytics son responsables de seleccionar la información sobre cada componente en el Diccionario de datos para ponerla a disposición de los usuarios.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Diccionario de datos para Analysis Workspace](https://video.tv.adobe.com/v/3418028/?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]



## Ventajas para los usuarios

El diccionario de datos ayuda a los usuarios a comprender mejor cada componente que tienen a su disposición.

La información disponible en el diccionario de datos incluye la siguiente:

* Función y uso previsto de un componente.

* Componentes que se utilizan normalmente con el que está viendo.

* Componentes que son similares al que está viendo.

* Indica si el administrador del sistema ha aprobado un componente.

Para obtener información sobre cómo acceder al diccionario de datos y para obtener detalles sobre la información que contiene, consulte [Ver información del componente en el diccionario de datos](view-data-dictionary.md).

## Ventajas para los administradores

El diccionario de datos ayuda a los administradores de sistemas a seguir los componentes de su entorno de Analytics y a seleccionarlos.

Los administradores de Analytics pueden utilizar el diccionario de datos para los siguientes fines:

* Identificar los componentes duplicados que deben consolidarse.

* Identificar los componentes que no recopilan datos para que se puedan actualizar o eliminar.

* Identificar los componentes que aún no se han aprobado.

* Actualizar las descripciones de los componentes directamente en Analysis Workspace. Las actualizaciones realizadas en las descripciones de los componentes del diccionario de datos se reflejan en la vista de datos.

  Del mismo modo, cualquier actualización realizada en las descripciones de los componentes de la vista de datos se reflejan en Analysis Workspace.

  Para obtener más información sobre la adición de descripciones de componentes en Analysis Workspace o en una vista de datos, consulte [Adición de descripciones de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Acceso al diccionario de datos

Puede acceder al diccionario de datos de cualquiera de las siguientes maneras en Analysis Workspace:

![Icono del diccionario de datos en el panel izquierdo](assets/data-dictionary-access.png)

* Desde el ![Marcador](/help/assets/icons/Bookmark.svg) en el panel de botones.



* Desde el ![Marcador](/help/assets/icons/Bookmark.svg) en la ventana emergente de información de un componente.


Para obtener información detallada sobre las distintas opciones disponibles en el diccionario de datos, consulte [Ver información del componente en el diccionario de datos](view-data-dictionary.md).

## Actualizar y depurar el diccionario de datos

Los administradores de Adobe Analytics son responsables de mantener un diccionario de datos correcto para su organización, tal como se describe en [Monitorizar el estado del diccionario de datos](monitor-data-dictionary-health.md).

Como parte de este proceso, los administradores de Adobe Analytics pueden editar la información sobre cada componente del diccionario de datos, tal como se describe en [Editar entradas de componente en el diccionario de datos](edit-entries-data-dictionary.md).

## Movimiento, minimización o cierre del diccionario de datos

Cuando abre el diccionario de datos (como se describe en [Acceso al diccionario de datos](#access-the-data-dictionary)), se muestra como una ventana en la parte superior de Analysis Workspace.

Puede manipular la ventana Diccionario de datos de cualquiera de estas formas:

* Arrastrarla a cualquier área dentro de Analysis Workspace

  Si cierra y vuelve a abrir Analysis Workspace, la ventana Diccionario de datos permanece en la ubicación donde la movió por última vez. <!--True?-->

* Minimice la ventana.

  Cuando se minimiza, el diccionario de datos aparece como una pestaña azul en la esquina inferior derecha de Analysis Workspace.

  Al seleccionar la pestaña azul, el diccionario de datos se abre con el componente que estaba viendo más recientemente.

* Cierre la ventana.


<!--
# Data Dictionary overview

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment.   

Analytics administrators are responsible for curating information about each component in the Data Dictionary to make it available to users.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data dictionary](https://video.tv.adobe.com/v/3418028?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Benefits for users

The Data Dictionary helps users gain a better understanding of each component that is available to them. 

Information available in the Data Dictionary includes: 

* A component's function and intended use

* Components typically used with the one you are viewing

* Components that are similar to the one you are viewing

* Whether a component is approved by the system administrator 

For information about how to access the Data Dictionary and for details about the information it contains, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Benefits for administrators

The Data Dictionary helps system administrators keep track of and curate the components in their Analytics environment. 

Following are some of the ways Analytics administrators can use the Data Dictionary: 

* Identify duplicate components that need to be consolidated.

* Identify components that aren't collecting any data so they can be either updated or deleted.

* Identify components that are not yet approved.

* Update component descriptions directly in Analysis Workspace. Any updates made to component descriptions in the Data Dictionary are reflected in the Report Suite.

  Similarly, any updates made to component descriptions in the Report Suite are reflected in Analysis Workspace.

  For more information about adding component descriptions in either Analysis Workspace or in a Report Suite, see [Add component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Access the Data Dictionary

You can access the Data Dictionary in any of the following ways within Analysis Workspace:

* From the **Data Dictionary** icon in the left rail.

  ![Data Dictionary icon in the left rail](assets/data-dictionary-access-icon.png)

* From the **Data Dictionary** icon within the info popover of a component. 

  ![Data Dictionary icon in info popover](assets/data-dictionary-access-infopopover.png)


For detailed information about the various options available in the Data Dictionary, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Update and curate the Data Dictionary

Analytics administrators are responsible for maintaining a healthy Data Dictionary for their organization, as described in [Monitor Data Dictionary Health](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).

As part of this process, Analytics administrators can edit information about each component in the data dictionary, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

## Move, minimize, or close the Data Dictionary

When you open the Data Dictionary (as described in [Access the Data Dictionary](#access-the-data-dictionary)), it displays as a window on top of Analysis Workspace. 

You can manipulate the Data Dictionary window in any of the following ways:

* Drag it to any area within Analysis Workspace 

  If you close and re-open Analysis Workspace, the Data Dictionary window remains in the location where you last moved it.

* Minimize it

  When minimized, the Data Dictionary appears as a blue tab in the lower-right corner of Analysis Workspace.

  When you select the blue tab, the Data Dictionary opens to the component you were most recently viewing. 

* Close it

-->