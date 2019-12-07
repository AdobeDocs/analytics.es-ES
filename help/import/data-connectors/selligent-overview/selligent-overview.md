---
description: 'null'
title: Conector de datos selectivo para Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Selligent Data Connector for Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

Esta integración incluye las siguientes ventajas clave:

* Consolide los datos de marketing y análisis de correo electrónico en una interfaz de informes.
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio.
* Volver a comercializar a visitantes clave y segmentos de mercado según segmentos de mercadotecnia dinámicos.

## Segmentos de marketing dinámico {#section-a2216f3339304636bd5417249bd635a4}

Esta integración de correo electrónico admite segmentos de marketing dinámicos para ayudarle a dirigir su negocio. Esta integración incluye los siguientes segmentos de mercadotecnia predeterminados:

| Segmento | Descripción |
|---|---|
| **Perfil de abandono del carro de compras** | Ayudar a los visitantes a convertirse a clientes a través de campañas específicas diseñadas específicamente para aquellos que dudan en completar los carros. |
| **Perfil de compras** | Aumentar los pedidos repetidos y el valor promedio de los pedidos a través de campañas dirigidas por patrones de compra de visitantes. |
| **Perfil de comportamiento de vista de contenido/producto** | Llegar a los clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido. |
| **Segmentos personalizados de remercadotecnia** | Los clientes también pueden crear y programar segmentos personalizados de remercadotecnia específicos de las necesidades de sus usuarios. |

## Antes de activar esta integración{#before-you-activate-this-integration}

Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics y del software de correo electrónico.

Al hacerlo, se asegurará de que se aplican las prácticas recomendadas y los requisitos previos adecuados antes de la activación. Esto resultará en una integración óptima y exitosa.

## Requisitos previos de Adobe Analytics{#prerequisites-for-adobe-analytics}

Enumera las acciones necesarias para realizar en Adobe Analytics antes de poder implementar la integración.

| Requisitos previos | Notas |
|---|---|
| Seleccionar grupo de informes | Tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración. |
| Configuración de variables de Analytics | Esta integración requiere eventos personalizados y eVars personalizadas, y, opcionalmente, eventos adicionales y eVars adicionales. Consulte Configuración de variables de Analytics para selección. |
| Representante autorizado | Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa; y como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente. |
| Habilitar Adobe Data Warehouse™ | Esta integración requiere que el almacén de datos esté habilitado para generar segmentos de remercadotecnia. Si no ha habilitado el almacén de datos de Adobe, póngase en contacto con Adobe para obtener más información. |
| Recipient ID | La integración requiere que captemos y almacenemos un "ID de visitante" dentro de una variable de Analytics (eVar). La ID del visitante (conocida a menudo como "ID del destinatario") es una representación numérica o codificada de una dirección de correo electrónico del sistema selecto. Esta "ID del destinatario" está asociada con el comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se introduce de nuevo en el sistema de ventas y se puede aprovechar para fines de remercadotecnia. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el Asistente le solicite. |
| Seguimiento externo | Si actualmente no está siguiendo la práctica recomendada de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración exitosa. Consulte la sección de selección para obtener más detalles. |
| Cumplimiento de normas de privacidad | Debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento. |

## Configuración de variables de Analytics para selectividad{#configure-analytics-variables-for-selligent}

Esta integración requiere que se reserven 2 eVars para cada implementación de grupo de informes.

Aparte de estas eVars, es posible que algunos eventos se reserven en función de los datos de Selplice, que le gustaría ver en Analytics. Estas eVars y eventos se describen a continuación:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variable </th> 
   <th colname="col2" class="entry"> Nombre de variable </th> 
   <th colname="col3" class="entry"> Cómo se utiliza </th> 
   <th colname="col4" class="entry"> Configuración </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID del mensaje </td> 
   <td colname="col3"> Para capturar la identificación individual de la campaña de mensajes de correo electrónico. </td> 
   <td colname="col4"> <p><b>Estado</b>: Habilitado </p> <p><b>Asignación</b>: Más reciente </p> <p><b>Caduca después</b>de: "Decisión comercial" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Para capturar la identificación anónima del cliente que hizo clic en la campaña de correo electrónico. </td> 
   <td colname="col4"> <p><b>Estado</b>: Habilitado </p> <p><b>Asignación</b>: Más reciente </p> <p><b>Caduca después</b>de: "Decisión comercial" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> Para almacenar el número de mensajes de correo electrónico enviados desde Selplice. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Enviado </td> 
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
   <td colname="col2"> Devuelto </td> 
   <td colname="col3"> Para almacenar el número de correos electrónicos devueltos. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
 </tbody> 
</table>

## Requisitos previos para la selección{#prerequisites-for-selligent}

Enumera la información necesaria que se debe proporcionar desde la cuenta de Seleccionar para poder implementar la integración.

**Cuenta de selección válida**

Para poder utilizar esta integración de Data Connectors, debe tener una cuenta válida de Selplice.

**Información de la cuenta**

Durante esta configuración de integración, necesitará la siguiente información sobre su cuenta de Selplice:

* **Dirección URL** del servicio de Adobe:

   La dirección URL puede derivarse de la dirección URL utilizada para iniciar sesión en la solución de marketing inteligente. Reemplazar la parte "/simweb/login.aspx" de la dirección URL con "/automation/omniture.asmx"

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** Parámetros de cadena de consulta: Se anexan en la dirección URL de la página de aterrizaje para la ID del mensaje y la ID del destinatario (ID del visitante). Siempre son MID y RID para ID de mensaje e ID de destinatario, respectivamente.

* **Token** de integración Inicie la herramienta Administrador desde Simweb y vaya a **[!UICONTROL Configuración]** &gt; Configuración **[!UICONTROL del sistema]** &gt; ficha **[!UICONTROL General]** &gt; **[!UICONTROL Sistema]**. En **[!UICONTROL Seguridad]**, puede encontrar el token de integración.

   ![](assets/selligent-integration_token.png)
