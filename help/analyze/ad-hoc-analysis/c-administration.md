---
description: Configuración de usuarios e información acerca del muestreo de datos.
title: Administración
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 98%

---


# Administración

>[!IMPORTANT]
>
>Adobe está moviendo Ad Hoc Analysis al estado de fin de vida el 1 de marzo de 2021. [Más información...](https://adobe.ly/discoverworkspace).

Configuración de usuarios e información acerca del muestreo de datos.

Para obtener ayuda sobre [!DNL Admin Console], consulte la [Documentación de Analytics](https://docs.adobe.com/content/help/es-ES/analytics/landing/home.html).

## Licencias de usuario {#concept_C1440741C77C471EB38A243B013EA620}

Para que un usuario pueda iniciar sesión, se le debe otorgar una licencia de usuario. Las licencias de usuario de son de uso concurrente. Los usuarios pueden compartir sus licencias, pero la cantidad de usuarios simultáneos en un momento dado no puede superar la cantidad de licencias adquiridas.

<!-- 

c_user_license.html

 -->

Si el número de usuarios que iniciaron sesión excede el número de licencias disponibles, aparecerá un cuadro de diálogo para informar al usuario que ya se están usando todas las licencias disponibles. El sistema mostrará al usuario su ubicación en la cola de espera, junto con un vínculo que permite volver a comprobar la posición para ver si cambió. Cuando hay una licencia disponible, se notifica al usuario por correo electrónico y mediante un diálogo emergente para indicarle que puede acceder a Ad Hoc Analysis. A partir de ese momento, el usuario tiene 15 minutos para responder antes de perder la posición en la cola.

## Otorgar licencias a usuarios {#task_22AE669703EC48BA9685414538D8B1FA}

Instrucciones sobre cómo los administradores locales de Reports and Analytics pueden otorgar licencias de usuario a través del sistema de permisos.

<!-- 

t_user_licenses.xml

 -->

1. Inicie sesión en [!DNL Experience Cloud].
1.  Haga clic en **[!UICONTROL Admin]** > **[!UICONTROL Administración de usuarios]**. 
1. Haga clic en **[!UICONTROL Editar grupos]**.

   Si su empresa ha adquirido licencias de usuario, aparecerá el grupo [!UICONTROL Usuarios con licencias de Ad Hoc Analysis] en la columna [!UICONTROL Nombre del grupo]. También se muestra el número de licencias disponibles para los inicios de sesión de los usuarios.

1. Haga clic en **[!UICONTROL Editar]**.
1. En [!UICONTROL Asignar inicios de sesión a usuarios], seleccione los usuarios que desee añadir al grupo y haga clic en **[!UICONTROL Añadir.]**
1. Haga clic en **[!UICONTROL Guardar grupo]**.

   El sistema de licencias no limita la cantidad de usuarios que se pueden agregar a un grupo. El uso simultáneo del número de licencias compradas es limitado.

## Administración de sesiones de usuario {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Instrucciones sobre cómo finalizar sesiones de usuario (para administradores). Esta función no impide que un usuario cuya sesión finalizó de este modo vuelva a iniciar otra sesión.

<!-- 

t_managing_users.xml

 -->

1. Haga clic en **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Administración de usuarios]** y, a continuación, haga clic en **[!UICONTROL Administrar usuarios]**.
1. Ubique el usuario y haga clic en **[!UICONTROL Finalizar.]** 

   En la página [!UICONTROL Sesiones activas de Ad Hoc Analysis], aparecen primero los usuarios que han estado más tiempo inactivos.

## Permisos {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

El acceso a los grupos de informes se configura en la [!DNL Administration Console]. Puede configurar los permisos en el nivel de grupo de informes. Por ejemplo, si tiene varios grupos de informes habilitados, pero no desea otorgar a todos los usuarios acceso a todos los grupos de informes, puede crear grupos correspondientes a grupos de informes concretos y luego asignar los usuarios al grupo que corresponda.

## Agregar usuarios al grupo Acceso a todos los informes {#task_E821BF3B4FDB434D844A98AAB15487A9}

Instrucciones sobre cómo otorgar acceso a usuarios que no sean administradores a todos los grupos de informes.

<!-- 

t_permissions.xml

 -->

1. Inicie sesión desde **[!UICONTROL Experience Cloud]**. 
1. Haga clic en **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL Administración de usuarios]** > **[!UICONTROL Editar grupos]**.
1. Haga clic en **[!UICONTROL Acceso a todos los informes]**.
1. En [!UICONTROL Usuarios disponibles], seleccione el usuario y haga clic en **[!UICONTROL Agregar]**. 
1. Haga clic en **[!UICONTROL Guardar grupo]**.

## Crear grupos de permisos {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Creación de grupos de permisos para usuarios no administrativos a grupos de informes específicos.

<!-- 

t_permission_groups.xml

 -->

1. Inicie sesión desde **[!UICONTROL Experience Cloud]**. 
1. Haga clic en **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL Administración de usuarios]** > **[!UICONTROL Editar grupos]**.
1. Cree un grupo de permisos para usuarios no administrativos que incluya los grupos de informes activados con Ad Hoc Analysis que desea poner a disposición de los usuarios.

   Los grupos de informes disponibles para el usuario se muestran en el menú [!UICONTROL Informe Cloud] al crear un nuevo proyecto.

## Configuración de directivas de proxy en Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Instrucciones sobre cómo configurar las políticas de proxy si se produce un error de conexión del servidor.

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis usa HTTP para comunicarse con el servidor. y está sujeto a las mismas directivas de proxy que cualquier otro tráfico HTTP.

1. En el [!DNL Windows Control Panel], inicie el [!UICONTROL Panel de control de Java].
1. En la ficha **[!UICONTROL General]**, haga clic en **[!UICONTROL Configuración de red]**.
1. Seleccione **[!UICONTROL Usar configuración de navegador]** o configure manualmente las opciones de proxy.
1. Haga clic en **[!UICONTROL Aceptar]** y vuelva a hacer clic en **[!UICONTROL Aceptar]** en el [!UICONTROL Panel de control de Java].

## Cómo se muestran los datos {#concept_8433CFD38E0243849E92DF4F1E743AC3}

Se toman muestran de datos de visitantes para producir informes significativos y precisos. El intervalo de fechas se usa como fracción de datos para un proyecto cargado. Por lo general, la fracción representa el mes en curso más los dos meses anteriores.

<!-- 

c_overview_data_sampling.xml

 -->

Para asegurar un procesamiento óptimo, Ad Hoc Analysis utiliza alrededor de 750 millones como valor máximo de visitas por fracción. (Visitas = vistas de página + eventos).

Para llegar a la frecuencia de muestreo prevista, se calculan las visitas previstas por cada conjunto de datos y luego se dividen entre 750 millones. Por ejemplo:

* (Promedio de visitas diarias x número de días en la fracción) / 750 millones

Por ejemplo, si recibe 10 millones de visitas por día, con una fracción de datos de 90 días:

* (10.000.000 x 90) / 750.000.000 = 1,2

Así que para mantener la cantidad de visitas de la fracción de 90 días por debajo de 750 000 000, se puede tomar una muestra de datos con una frecuencia de 1,2:1; pero debido a que se toman muestras en números enteros, la frecuencia de muestreo será de 2:1.

Otro ejemplo sería que si recibe 10 millones de visitas por día, con una fracción de datos de 365 días:

* (10.000.000 x 365) / 750.000.000 = 4,8

Así que para mantener la cantidad de visitas de la fracción de 365 días por debajo de 750.000.000, se puede tomar una muestra de datos con una frecuencia de 4,8:1. Con números enteros, la frecuencia de muestreo es de 5:1.
