---
description: Utilice el conector de datos de Selligent con Adobe Analytics.
title: Data Connectors de Selligent para Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 97%

---


# Data Connectors de Selligent para Adobe Analytics {#selligent-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La vida útil de la tecnología de Adobe Data Connector finalizará el 1 de agosto de 2021. [Más información...](/help/import/data-connectors/data-connectors-eol.md)

Esta integración incluye las siguientes ventajas clave:

* Consolidar los datos de análisis y marketing por correo electrónico en una interfaz de informes.
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio.
* Volver a enviar marketing a visitantes clave y segmentos de mercado según segmentos de marketing dinámicos.

## Segmentos de marketing dinámico {#section-a2216f3339304636bd5417249bd635a4}

Esta integración de correo electrónico admite segmentos de marketing dinámicos para ayudarle a dirigir la empresa. Esta integración incluye los siguientes segmentos de marketing predeterminados:

| Segmento | Descripción |
|---|---|
| **Perfil de abandono del carro de compras** | Convierta a los visitantes en clientes a través de campañas específicas diseñadas para aquellos que dudan en completar la compra. |
| **Perfil de compras** | Aumente los pedidos repetidos y el valor promedio de los pedidos a través de campañas dirigidas por patrones de compra de visitantes. |
| **Perfil de comportamiento de vista de contenido/producto** | Llegue a los clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido. |
| **Segmentos de remarketing personalizados** | Los clientes también pueden crear y programar segmentos de remarketing personalizados específicos para las necesidades de sus usuarios. |

## Antes de activar esta integración {#before-you-activate-this-integration}

Antes de activar esta integración, revise las siguientes opciones en relación con las implementaciones de Adobe Analytics y del software de correo electrónico.

Al hacerlo, se asegura de que se siguen las prácticas recomendadas y los requisitos previos adecuados antes de la activación. De este modo, la integración será un éxito.

## Requisitos previos de Adobe Analytics {#prerequisites-for-adobe-analytics}

Enumera las acciones necesarias para realizar en Adobe Analytics antes de poder implementar la integración.

| Requisitos previos | Notas |
|---|---|
| Seleccionar grupo de informes | Tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración. |
| Configuración de variables de Analytics | Esta integración requiere eventos personalizados y eVars personalizadas, y, opcionalmente, eventos y eVars adicionales. Consulte Configuración de variables de Analytics para Selligent. |
| Representante autorizado | Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa y, como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente. |
| Habilitar Adobe Data Warehouse™ | Esta integración requiere que Data Warehouse esté habilitado para generar segmentos de remarketing. Si no ha habilitado Adobe Data Warehouse, póngase en contacto con Adobe para obtener más información. |
| Recipient ID (ID de destinatario) | La integración requiere que recopilemos y almacenemos un “ID de visitante” dentro de una variable de Analytics (eVar). El ID de visitante (denominada con frecuencia como “ID de destinatario”) es una representación numérica o codificada de una dirección de correo electrónico del sistema de Selligent. Este “ID de destinatario” está asociado al comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora de nuevo en el sistema de Selligent y se puede aprovechar para fines de remarketing. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el asistente lo solicite. |
| Seguimiento externo | Si actualmente no realiza las prácticas recomendadas de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración sin problemas. Consulte la sección Selligent más abajo para obtener más información. |
| Respeto de la privacidad | Debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento. |

## Configuración de variables de Analytics para Selligent {#configure-analytics-variables-for-selligent}

Esta integración requiere que se reserven 2 eVars para cada implementación de grupo de informes.

Aparte de estas eVars, es posible que algunos eventos se reserven en función de los datos de Selligent, que le gustaría ver en Analytics. Estos eVars y eventos se describen a continuación:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variable </th> 
   <th colname="col2" class="entry"> Nombre de variable </th> 
   <th colname="col3" class="entry"> Uso de la variable </th> 
   <th colname="col4" class="entry"> Configuración </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de mensaje </td> 
   <td colname="col3"> Para recopilar la identificación individual de la campaña de mensajes de correo electrónico. </td> 
   <td colname="col4"> <p><b>Estado</b>: Habilitado </p> <p><b>Asignación</b>: Más reciente </p> <p><b>Caduca después de</b>: “Decisión comercial” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID (ID de destinatario) </td> 
   <td colname="col3"> Para recopilar la identificación anónima del cliente que hizo clic en la campaña de correo electrónico. </td> 
   <td colname="col4"> <p><b>Estado</b>: Habilitado </p> <p><b>Asignación</b>: Más reciente </p> <p><b>Caduca después de</b>: “Decisión comercial” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Enviados </td> 
   <td colname="col3"> Para almacenar el número de mensajes de correo electrónico enviados desde Selligent. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Entregas </td> 
   <td colname="col3"> Para almacenar el número de correos electrónicos entregados. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Vistas </td> 
   <td colname="col3"> Para almacenar el número de correos electrónicos únicos que se vieron. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Para almacenar el número de veces que se hizo clic en un correo electrónico. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Devueltos </td> 
   <td colname="col3"> Para almacenar el número de correos electrónicos devueltos. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
 </tbody> 
</table>

## Requisitos previos de Selligent {#prerequisites-for-selligent}

Enumera la información necesaria que se debe proporcionar desde la cuenta de Selligent para poder implementar la integración.

**Cuenta válida de Selligent**

Para utilizar esta integración de Data Connectors, debe tener una cuenta de Selligent válida.

**Información de la cuenta**

Durante la configuración de esta integración necesita la siguiente información sobre su cuenta de Selligent:

* **URL del servicio de Adobe**:

   La dirección URL puede derivarse de la URL utilizada para iniciar sesión en la solución de Selligent Marketing. Cambie la parte “/simweb/login.aspx” de la dirección URL por “/automation/omniture.asmx”.

   Por ejemplo: `http://<client-specific install url>/automation/omniture.asmx`.

* **Parámetros de cadena de consulta**: se anexan en la dirección URL de la página de aterrizaje para el ID de mensaje y el ID de destinatario (ID de visitante). Siempre son MID y RID para ID de mensaje e ID de destinatario, respectivamente.

* **Token de integración** Inicie la herramienta Administrador desde Simweb y vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Configuración del sistema]** > pestaña **[!UICONTROL General]** > **[!UICONTROL Sistema]**. En **[!UICONTROL Seguridad]**, puede encontrar el token de integración.

   ![](assets/selligent-integration_token.png)
