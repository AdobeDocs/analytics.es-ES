---
title: ¿Qué es la variable currencyCode y cómo se usa?
description: Para los sitios de comercio electrónico, establece la moneda que usa la página.
feature: Variables
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 98%

---

# currencyCode

Para los sitios comerciales, los ingresos y la moneda son una parte importante de Analytics. Muchos sitios, especialmente los que abarcan varios países, utilizan distintas monedas. Utilice la variable `currencyCode` para asegurarse de que los atributos de ingresos corresponden a la moneda correcta.

La conversión de moneda utiliza la siguiente lógica en cada visita. Estos pasos se aplican a los valores de ingresos establecidos en la variable [`products`](../page-vars/products.md) y a todos los eventos enumerados como «Moneda» en [Eventos de éxito](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) en Configuración del grupo de informes.

* Si `currencyCode` no está definida, Adobe supone que todos los valores de moneda son la moneda del grupo de informes. Consulte [Configuración general de la cuenta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) en Configuración del grupo de informes para ver la moneda del grupo de informes.
* Si `currencyCode` está definida y coincide con la moneda del grupo de informes, no se aplica ninguna conversión de moneda.
* Si `currencyCode` está definida y es diferente a la moneda del grupo de informes, Adobe aplica una conversión de moneda basada en el tipo de cambio del día actual. Adobe se asocia con [XE](https://xe.com) para convertir moneda cada día. Todos los valores almacenados en el grupo de informes tienen la moneda del grupo de informes.
* Si `currencyCode` se establece en un valor no válido, **se descarta toda la visita, lo que provoca la pérdida de datos.** Asegúrese de que esta variable esté correctamente definida cuando se utilice.

Esta variable no persiste entre visitas. Asegúrese de que esta variable esté definida en todas las páginas que tengan eventos de ingresos o de moneda que no coincidan con la moneda predeterminada del grupo de informes.

>[!NOTE]
>
>Aunque los códigos de moneda pueden cambiar entre páginas, todas las métricas de moneda de una sola visita deben utilizar la misma moneda.

Es **obligatorio** usar un punto como separador decimal en moneda para todas las monedas al implementar esta variable. Por ejemplo, la corona sueca, que normalmente usa la coma como separador, debe modificarse para que utilice un punto en la variable `products` y en todos los eventos de moneda. Adobe muestra el separador decimal en moneda correcto en la creación de informes.

## Código de moneda mediante el SDK web

El código de moneda se asigna a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.currencyCode`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.currencyCode` o `data.__adobe.analytics.cc`

## Código de moneda con la extensión Adobe Analytics

Código de moneda es un campo en el acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Código de moneda].

Puede utilizar un código de moneda preestablecido o un código de moneda personalizado. Si utiliza un código de moneda personalizado, asegúrese de que el código sea válido.

## Código de moneda en Adobe Experience Platform Mobile SDK

El código de moneda se pasa a los SDK de Adobe Experience Platform Mobile a través de variables de datos de contexto en la extensión de Adobe Analytics.

1. Configure el código de moneda en una variable de datos de contexto durante `trackState` o `trackAction`.
1. Cree una regla de procesamiento en las herramientas de administración de Adobe Analytics para el grupo de informes. Configure la regla para sobrescribir la variable Código de moneda.
1. Pase el código de moneda a la variable `products` en su llamada para `trackState` o `trackAction`.

Puede utilizar un código de moneda preestablecido o un código de moneda personalizado. Si utiliza un código de moneda personalizado, asegúrese de que el código sea válido.

## s.currencyCode en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.currencyCode` es una cadena que contiene un código en mayúsculas de 3 letras que representa la moneda de la página. Los valores distinguen entre mayúsculas y minúsculas.

```js
s.currencyCode = "USD";
```

Los siguientes códigos de moneda son válidos:

| Código de moneda | Etiqueta |
| --- | --- |
| `AED` | Dirham de Emiratos Árabes Unidos |
| `AFA` | Afgani de Afganistán |
| `ALL` | Leke albanés |
| `AMD` | Dram armenio |
| `ANG` | Florín antillano neerlandés |
| `AOA` | Kwanza angolano |
| `ARS` | Peso argentino |
| `AUD` | Dólar australiano |
| `AWG` | Florín arubeño |
| `AZM` | Manat azerí de Azerbayán |
| `BAM` | Marco convertible de Bosnia y Herzegovina |
| `BBD` | Dólar de Barbados |
| `BDT` | Taka de Bangladesh |
| `BGN` | Lev búlgaro |
| `BHD` | Dinar bahrainí |
| `BIF` | Franco de Burundi |
| `BMD` | Dólar bermudeño |
| `BND` | Dólar de Brunei |
| `BOB` | Boliviano |
| `BRL` | Real de Brasil |
| `BSD` | Dólar bahameño |
| `BTN` | Ngultrum butanés |
| `BWP` | Pula de Botsuana |
| `BYR` | Rublo bielorruso |
| `BZD` | Dólar beliceño |
| `CAD` | Dólar canadiense |
| `CDF` | Franco congoleño |
| `CHF` | Franco suizo |
| `CLP` | Peso chileno |
| `CNY` | Yuan renminbi chino |
| `COP` | Peso colombiano |
| `CRC` | Colón costarricense |
| `CSD` | Dinar serbio |
| `CUP` | Peso cubano |
| `CVE` | Escudo caboverdiano |
| `CYP` | Libra chipriota |
| `CZK` | Corona checa |
| `DJF` | Franco de Yibuti |
| `DKK` | Corona danesa |
| `DOP` | Peso dominicano |
| `DZD` | Dinar argelino |
| `EEK` | Corona estonia |
| `EGP` | Libra egipcia |
| `ERN` | Nakfa de Eritrea |
| `ETB` | Birr de Etiopía |
| `EUR` | Euro |
| `FJD` | Dólar fiyiano |
| `FKP` | Libra malvinense |
| `GBP` | Libra esterlina |
| `GEL` | Lari georgiano |
| `GGP` | Libra de Guernsey |
| `GHC` | Cedi ghanés |
| `GIP` | Libra gibraltareña |
| `GMD` | Dalasi de Gambia |
| `GNF` | Franco guineano |
| `GTQ` | Quetzal |
| `GYD` | Dólar guyanés |
| `HKD` | Dólar de Hong Kong |
| `HNL` | Lempira |
| `HRK` | Kuna croata |
| `HTG` | Gourde haitiano |
| `HUF` | Florín húngaro |
| `IDR` | Rupia indonesia |
| `ILS` | Nuevo shéquel israelí |
| `IMP` | Libra manesa |
| `INR` | Rupia india |
| `IQD` | Dinar iraquí |
| `IRR` | Rial iraní |
| `ISK` | Corona islandesa |
| `JEP` | Libra de Jersey |
| `JMD` | Dólar jamaiquino |
| `JOD` | Dinar jordano |
| `JPY` | Yen japonés |
| `KES` | Chelín keniata |
| `KGS` | Som kirguís |
| `KHR` | Riel camboyano |
| `KMF` | Franco comorense |
| `KPW` | Won norcoreano |
| `KRW` | Won surcoreano |
| `KWD` | Dinar kuwaití |
| `KYD` | Dólar de las Islas Caimán |
| `KZT` | Tenge de Kazajistán |
| `LAK` | Kip laosiano |
| `LBP` | Libra libanesa |
| `LKR` | Rupia esrilanquesa |
| `LRD` | Dólar liberiano |
| `LSL` | Loti de Lesoto |
| `LTL` | Litas lituana |
| `LVL` | Lats letón |
| `LYD` | Dinar libio |
| `MAD` | Dirham marroquí |
| `MDL` | Leu moldavo |
| `MGA` | Ariary malgache |
| `MKD` | Dinar macedonio |
| `MMK` | Kyat myanmaro |
| `MNT` | Tugrik mongol |
| `MOP` | Pataca de Macao |
| `MRO` | Uquiya mauritana |
| `MTL` | Libra maltesa |
| `MUR` | Rupia mauritana |
| `MVR` | Rupia de Maldivas |
| `MWK` | Kwacha malauiano |
| `MXN` | Peso mexicano |
| `MYR` | Ringgit malayo |
| `MZM` | Metical mozambiqueño |
| `NAD` | Dólar namibio |
| `NGN` | Naira nigeriana |
| `NIO` | Córdoba nicaragüense |
| `NOK` | Corona noruega |
| `NPR` | Rupia nepalesa |
| `NZD` | Dólar neozelandés |
| `OMR` | Rial omaní |
| `PAB` | Balboa panameño |
| `PEN` | Nuevo sol peruano |
| `PGK` | Kina de Papúa Nueva Guinea |
| `PHP` | Peso filipino |
| `PKR` | Rupia pakistaní |
| `PLN` | Zloty polaco |
| `PYG` | Guaraní paraguayo |
| `QAR` | Rial qatarí |
| `ROL` | Leu rumano |
| `RUR` | Rublo ruso |
| `RWF` | Franco ruandés |
| `SAR` | Riyal saudí |
| `SBD` | Dólar de las Islas Salomón |
| `SCR` | Rupia de Seychelles |
| `SDD` | Dinar sudanés |
| `SEK` | Corona sueca |
| `SGD` | Dólar de Singapur |
| `SHP` | Libra de Santa Helena |
| `SIT` | Tólar esloveno |
| `SKK` | Corona eslovaca |
| `SLL` | Leone de Sierra Leona |
| `SOS` | Chelín somalí |
| `SPL` | Luigino de Seborga |
| `SRD` | Dólar surinamés |
| `SRG` | Florín surinamés |
| `STD` | Doblón santotomense |
| `SVC` | Colón salvadoreño |
| `SYP` | Libra siria |
| `SZL` | Lilangeni de Suazilandia |
| `THB` | Baht tailandés |
| `TJS` | Somoni de Tayikistán |
| `TMM` | Manat turcomano |
| `TND` | Dinar tunecino |
| `TOP` | Pa&#39;anga tongano |
| `TRL` | Lira turca |
| `TTD` | Dólar de Trinidad y Tobago |
| `TVD` | Dólar tuvaluano |
| `TWD` | Nuevo dólar taiwanés |
| `TZS` | Chelín tanzano |
| `UAH` | Hryvnia ucraniana |
| `UGX` | Chelín ugandés |
| `USD` | Dólar estadounidense |
| `UYU` | Peso uruguayo |
| `UZS` | Som uzbeco |
| `VEB` | Bolívar venezolano |
| `VND` | Dong vietnamita |
| `VUV` | Vatu vanuatense |
| `WST` | Tala samoano |
| `XAF` | Franco de la Comunidad Financiera de África (CFA). |
| `XAG` | Onzas de plata |
| `XAU` | Onzas de oro |
| `XCD` | Dólar del Caribe Oriental |
| `XDR` | Giro Especial del Fondo Monetario Internacional |
| `XOF` | Franco de la Comunidad Financiera de África (CFA). |
| `XPD` | Onzas de paladio |
| `XPF` | Francos de Acuerdos financieros Francia-Pacífico |
| `XPT` | Onzas de platino |
| `YER` | Rial yemení |
| `ZAR` | Rand sudafricano |
| `ZMK` | Kwacha zambiano |
| `ZWD` | Dólar zimbabuense |
