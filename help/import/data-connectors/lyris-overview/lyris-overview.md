---
description: Describe las eficiencias de mercadotecnia logradas a través de la integración.
title: Conector de datos Lyris para Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

Describe las eficiencias de mercadotecnia logradas a través de la integración.

La integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Adobe Analytics con la mercadotecnia de correo electrónico de Lyris para redefinir la medición de éxito y las audiencias de destino con mensajes más relevantes.

El envío de mensajes de correo electrónico relevantes a estos segmentos de mercado puede generar oportunidades de ingresos completamente nuevas, lo que aumenta la conversión y los ingresos entre las campañas de correo electrónico nuevas y existentes. Por ejemplo: el envío de mensajes de correo electrónico relevantes basados en productos que se vieron durante una visita o productos que quedaron en un carro de compras abandonado ha demostrado tener un impacto dramático en los ingresos, con un impacto mínimo en el costo porque esto simplemente aprovecha los visitantes que el sitio ya está recibiendo.

Este aumento en la eficacia de la mercadotecnia es una de las ventajas clave de la integración de Adobe Analytics con Lyris. Además, esta integración sincronizará automáticamente las métricas de correo electrónico con los datos de Adobe Analytics con tanta frecuencia como cada hora para los informes de bucle cerrado.

## Ventajas y características principales{#key-benefits-and-features}

Describe las principales ventajas de integrar Lyris y Adobe Marketing Reports and Analytics.

La integración de Lyris y Adobe Analytics ofrece las siguientes ventajas clave:

* Consolidar los datos de análisis y mercadotecnia de correo electrónico en una interfaz de informes
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio
* Volver a comercializar a visitantes clave y segmentos de mercado según segmentos de mercadotecnia dinámicos

### Segmentos de marketing dinámico

La integración de correo electrónico admite segmentos de marketing dinámicos para ayudarle a dirigir su negocio. Esta integración incluye los siguientes segmentos de mercadotecnia predeterminados:

* **Perfil** de abandono del carro de compras: Ayudar a los visitantes a convertirse a clientes a través de campañas específicas diseñadas específicamente para aquellos que dudan en completar los carros
* **Perfiles** de compra: Aumentar los pedidos repetidos y el valor promedio de los pedidos a través de las campañas dirigidas por los patrones de compra de los visitantes
* **Perfil** de comportamiento de vista de contenido/producto: Llegar a los clientes potenciales a través de segmentos de mercadotecnia basados en vistas de productos y perfiles de acceso al contenido
* Los clientes también pueden crear y programar segmentos **de remercadotecnia** personalizados específicos para las necesidades de sus usuarios.

## Requisitos previos de integración{#integration-prerequisites}

Describe los requisitos previos para una integración correcta.

Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics y del software de correo electrónico.

Esto garantiza que las prácticas recomendadas y los requisitos previos adecuados estén implementados antes de la activación, lo que resultará en una integración óptima y exitosa.

### Requisitos previos de Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Grupo de informes específico**:Tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración
* **Variables** de Analytics disponibles y configuradas:Esta integración requiere eventos personalizados y eVars personalizadas, y, opcionalmente, eventos adicionales y eVars adicionales.

* **Representante** autorizado:Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa; y como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **Almacén** de datos de Adobe Analytics: Esta integración requiere que el almacén de datos de Adobe Analytics esté habilitado para generar segmentos de remarketing. Si no ha habilitado el almacén de datos, póngase en contacto con Adobe para obtener más información.
* **ID** del destinatario: La integración requiere que captemos y almacenemos un "ID de visitante" dentro de una variable de Analytics (eVar). La ID del visitante (conocida con frecuencia como "ID del destinatario") es una representación numérica o codificada de una dirección de correo electrónico del sistema Lyris. Esta "ID del destinatario" está asociada con el comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se introduce de nuevo en el sistema Lyris y se puede aprovechar para fines de remercadotecnia. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el Asistente le solicite.
* **Seguimiento** externo: Si actualmente no está siguiendo la práctica recomendada de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración exitosa. Consulte la sección Lyris para obtener más detalles
* **Cumplimiento** de la privacidad:Debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad, ya que requiere la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo notificar a los visitantes del sitio y obtener su consentimiento.

### Requisitos previos para Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Cuenta** Lyris válida: Para utilizar esta integración de Data Connector, debe tener una cuenta de Lyris válida.
* **Información** de la cuenta: Durante esta configuración de integración necesitará la siguiente información sobre su cuenta de Lyris:

   * *Clave* de API de Lyris: Se utiliza para la población de datos
   * *Parámetros* de cadena de consulta: Se anexan en la dirección URL de la página de aterrizaje para la ID del mensaje y la ID del destinatario (ID del visitante).
   * *Lyris Server/URL*: El valor de servidor que utiliza en el sistema Lyris
   * *ID* del sitio de Lyris: También conocido como "ID de cliente", este es el valor único para su instancia de Lyris HQ. Esto se encuentra en "Información del cliente" en la sección "Página principal de la cuenta" de EmailLabs.

## Configuración de variables de Adobe Analytics para Lyris{#configure-adobe-analytics-variables-for-lyris}

Describe las eVars y los eventos que se reservarán para cada implementación de grupo de informes.

Esta integración requiere que se reserven al menos 2 eVars para cada implementación de grupo de informes. Aparte de estas eVars, es posible que se reserven algunos eventos en función de los datos de Lyris que desee ver en Analytics. Estas eVars y eventos se describen en la siguiente tabla:

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variable </th> 
   <th colname="col2" class="entry"> Nombre de variable </th> 
   <th colname="col3" class="entry"> Cómo se utiliza la variable </th> 
   <th colname="col4" class="entry"> Configuración </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID del mensaje </td> 
   <td colname="col3"> Para capturar la identificación individual de campaña de mensajes de correo electrónico </td> 
   <td colname="col4"> <p>Estado: Habilitado </p> <p>Asignación: Más reciente </p> <p>Caduca después de: "Decisión comercial" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Para capturar la identificación anónima de su cliente que hizo clic en la campaña de correo electrónico </td> 
   <td colname="col4"> <p>Estado: Habilitado </p> <p>Asignación: Más reciente </p> <p>Caduca después de: "Decisión comercial" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Mensajes de correo electrónico enviados </td> 
   <td colname="col3"> Para almacenar no. de correos electrónicos enviados desde Lyris </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: correos electrónicos abiertos </td> 
   <td colname="col3"> Para almacenar no. de correos electrónicos que se abrieron </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris: correos electrónicos únicos abiertos </td> 
   <td colname="col3"> Para almacenar no. de correos electrónicos únicos que se abrieron </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Pulsaciones por correo electrónico </td> 
   <td colname="col3"> Para almacenar no. de veces que se hizo clic en un correo electrónico </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Devoluciones de correo electrónico </td> 
   <td colname="col3"> Para guardar el no. de correos electrónicos devueltos </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Cancelación de suscripciones a correo electrónico </td> 
   <td colname="col3"> Para guardar el no. de suscripciones de correo electrónico desactivadas </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
 </tbody> 
</table>
