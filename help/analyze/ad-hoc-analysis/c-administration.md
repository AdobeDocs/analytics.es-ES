---
description: Configuración de usuarios e información acerca del muestreo de datos.
title: Administración
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Administración

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
1. Haga clic **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Haga clic en **[!UICONTROL Edit Groups]**.

   Si la compañía ha adquirido licencias de usuario, el [!UICONTROL Ad Hoc Analysis License Users] grupo aparece en la [!UICONTROL Group Name] columna. También se muestra el número de licencias disponibles para los inicios de sesión de los usuarios.

1. Haga clic en **[!UICONTROL Edit]**.
1. Under [!UICONTROL Assign User Logins], select the users you want to add to the group, then click **[!UICONTROL Add.]**
1. Haga clic en **[!UICONTROL Save Group]**.

   El sistema de licencias no limita la cantidad de usuarios que se pueden agregar a un grupo. El uso simultáneo del número de licencias compradas es limitado.

## Administración de sesiones de usuario {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Instrucciones sobre cómo finalizar sesiones de usuario (para administradores). Esta función no impide que un usuario cuya sesión finalizó de este modo vuelva a iniciar otra sesión.

<!-- 

t_managing_users.xml

 -->

1. Haga clic en **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** y, a continuación, haga clic en **[!UICONTROL Manage Users]**.
1. Locate the user, then click **[!UICONTROL Terminate.]**

   On the [!UICONTROL Active Ad Hoc Analysis Sessions] page, the user who has been idle the longest displays at the top of list.

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

1. Inicie sesión en **[!UICONTROL Experience Cloud]**.
1. Haga clic **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Haga clic en **[!UICONTROL All Report Access]**.
1. En [!UICONTROL Available Users], seleccione el usuario y haga clic en **[!UICONTROL Add.]**
1. Haga clic en **[!UICONTROL Save Group]**.

## Crear grupos de permisos {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Creación de grupos de permisos para usuarios no administrativos a grupos de informes específicos.

<!-- 

t_permission_groups.xml

 -->

1. Inicie sesión en **[!UICONTROL Experience Cloud]**.
1. Haga clic **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Cree un grupo de permisos para usuarios no administrativos que incluya los grupos de informes activados con Ad Hoc Analysis que desea poner a disposición de los usuarios.

   The report suites available to the user are displayed in the [!UICONTROL Report Cloud] menu when you create a new project.

## Configuración de directivas de proxy en Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Instrucciones sobre cómo configurar las políticas de proxy si se produce un error de conexión del servidor.

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis usa HTTP para comunicarse con el servidor. y está sujeto a las mismas directivas de proxy que cualquier otro tráfico HTTP.

1. En la [!DNL Windows Control Panel], inicie la [!UICONTROL Java Control Panel].
1. En la **[!UICONTROL General]** ficha, haga clic en **[!UICONTROL Network Settings]**.
1. Seleccione **[!UICONTROL Use browser settings]** o configure manualmente la configuración del proxy.
1. Haga clic en **[!UICONTROL OK]**, luego haga clic **[!UICONTROL OK]** en la [!UICONTROL Java Control Panel].

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
