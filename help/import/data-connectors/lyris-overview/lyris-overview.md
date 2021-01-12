---
description: Describe la eficiencia de marketing conseguida a través de la integración.
title: Data Connectors de Lyris para Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 98%

---


# Data Connectors de Lyris para Adobe Analytics {#lyris-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>El 1 de agosto de 2021 terminaremos de usar la tecnología del conector de datos de Adobe. [Más información...](/help/import/data-connectors/data-connectors-eol.md)

La integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Adobe Analytics con el marketing por correo electrónico de Lyris para redefinir la medición de éxito y las audiencias de destino con mensajes más relevantes.

El envío de mensajes de correo electrónico relevantes a estos segmentos de mercado puede generar oportunidades de ingresos completamente nuevas, lo que aumenta la conversión y los ingresos entre las campañas de correo electrónico nuevas y existentes. Por ejemplo: el envío de mensajes de correo electrónico relevantes basados en productos que se vieron durante una visita o productos que quedaron en un carro de compras abandonado ha demostrado tener un impacto significativo en los ingresos, con un impacto mínimo en los costes porque esto simplemente aprovecha los visitantes que el sitio ya está recibiendo.

Este aumento en la eficacia del marketing es una de las ventajas clave de la integración de Adobe Analytics con Lyris. Además, esta integración sincroniza automáticamente las métricas de correo electrónico con los datos de Adobe Analytics a cada hora para los informes de bucle cerrado.

## Ventajas y características principales {#key-benefits-and-features}

Describe las principales ventajas de integrar Lyris y Adobe Marketing Reports and Analytics.

La integración de Lyris y Adobe Analytics ofrece las siguientes ventajas clave:

* Consolidar los datos de análisis y marketing por correo electrónico en una interfaz de informes.
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio.
* Volver a enviar marketing a visitantes clave y segmentos de mercado según segmentos de marketing dinámico.

### Segmentos de marketing dinámico

La integración de correo electrónico admite segmentos de marketing dinámicos para ayudarle a dirigir la empresa. Esta integración incluye los siguientes segmentos de marketing predeterminados:

* **Perfil de abandono del carro de compras**: convierta a los visitantes en clientes a través de campañas específicas diseñadas para aquellos que dudan en completar la compra.
* **Perfiles de compra**: aumente los pedidos repetidos y el valor promedio de los pedidos a través de campañas dirigidas por patrones de compra de visitantes.
* **Perfil de comportamiento de vista de contenido/producto**: llegue a los clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido.
* Los clientes también pueden crear y programar **segmentos de remarketing personalizados** específicos para las necesidades de sus usuarios.

## Requisitos previos de integración {#integration-prerequisites}

Describe los requisitos previos para una integración correcta.

Antes de activar esta integración, revise las siguientes opciones en relación con las implementaciones de Adobe Analytics y del software de correo electrónico.

Esto garantiza que las prácticas recomendadas y los requisitos previos adecuados estén implementados antes de la activación, lo que supone una integración óptima y sin problemas.

### Requisitos previos de Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Específico del grupo de informes**: tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración.
* **Variables de Analytics disponibles y configuradas**: esta integración requiere eventos personalizados, además de eVars personalizadas. Opcionalmente, también eVars y eventos adicionales.

* **Representante autorizado**: tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa y, como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **Adobe Analytics Data Warehouse**: esta integración requiere que Adobe Analytics Data Warehouse esté habilitado para generar segmentos de remarketing. Si no ha habilitado Data Warehouse, póngase en contacto con Adobe para obtener más información.
* **ID de destinatario**: la integración requiere que recopilemos y almacenemos un “ID de visitante” dentro de una variable de Analytics (eVar). El ID de visitante (denominada con frecuencia como “ID de destinatario”) es una representación numérica o codificada de una dirección de correo electrónico del sistema de Lyris. Este “ID de destinatario” está asociado al comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora de nuevo en el sistema de Lyris y se puede aprovechar para fines de remarketing. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el asistente lo solicite.
* **Seguimiento externo**: si actualmente no realiza las prácticas recomendadas de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración sin problemas. Consulte la sección Lyris más abajo para obtener más información.
* **Respeto de la privacidad**: debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento.

### Requisitos previos para Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Cuenta válida de Lyris**: para utilizar esta integración de Data Connector, debe tener una cuenta de Lyris válida.
* **Información de la cuenta**: durante la configuración de esta integración necesita la siguiente información sobre su cuenta de Lyris:

   * *Clave de la API de Lyris*: se utiliza para la obtención de datos.
   * *Parámetros de cadena de consulta*: se anexan en la dirección URL de la página de aterrizaje para el ID de mensaje y el ID de destinatario (ID de visitante).
   * *URL y servidor de Lyris*: el valor de servidor que utiliza en el sistema de Lyris.
   * *ID del sitio Lyris*: también conocido como “ID de cliente”, este es el valor único para su instancia de Lyris HQ. Esto se encuentra en “Información del cliente” en la sección “Página principal de la cuenta” de EmailLabs.

## Configuración de variables de Adobe Analytics para Lyris {#configure-adobe-analytics-variables-for-lyris}

Describe las eVars y los eventos que se reservan para cada implementación de grupo de informes.

Esta integración requiere que se reserven al menos 2 eVars para cada implementación de grupo de informes. Aparte de estas eVars, es posible que se reserven algunos eventos en función de los datos de Lyris que desee ver en Analytics. Estas eVars y eventos se describen en la siguiente tabla:

<table id="table_43E32344E9E54FED8491F28047249329"> 
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
   <td colname="col3"> Para recopilar la identificación individual de campaña de mensajes de correo electrónico. </td> 
   <td colname="col4"> <p>Estado: Habilitado </p> <p>Asignación: Más reciente </p> <p>Caduca después de: “Decisión comercial” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de destinatario de correo electrónico </td> 
   <td colname="col3"> Para recopilar la identificación anónima del cliente que hizo clic en la campaña de correo electrónico. </td> 
   <td colname="col4"> <p>Estado: Habilitado </p> <p>Asignación: Más reciente </p> <p>Caduca después de: “Decisión comercial” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: mensajes de correo electrónico enviados </td> 
   <td colname="col3"> Para guardar el número de correos electrónicos enviados desde Lyris. </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: correos electrónicos abiertos </td> 
   <td colname="col3"> Para guardar el número de correos electrónicos que se han abierto. </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: correos electrónicos únicos abiertos </td> 
   <td colname="col3"> Para guardar el número de correos electrónicos únicos que se han abierto. </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: clics por correo electrónico </td> 
   <td colname="col3"> Para guardar el número de veces que se hizo clic en un correo electrónico. </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: devoluciones de correo electrónico </td> 
   <td colname="col3"> Para guardar el número de correos electrónicos devueltos. </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: cancelación de suscripciones a correo electrónico </td> 
   <td colname="col3"> Para guardar el número de suscripciones de correo electrónico desactivadas. </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
 </tbody> 
</table>
