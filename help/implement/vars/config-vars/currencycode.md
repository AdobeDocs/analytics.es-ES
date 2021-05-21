---
title: ¿Qué es la variable currencyCode y cómo se usa?
description: Para los sitios de comercio electrónico, establece la moneda que usa la página.
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '830'
ht-degree: 100%

---

# currencyCode

Para los sitios comerciales, los ingresos y la moneda son una parte importante de Analytics. Muchos sitios, especialmente los que abarcan varios países, utilizan distintas monedas. Utilice la variable `currencyCode` para asegurarse de que los atributos de ingresos corresponden a la moneda correcta.

Si `currencyCode` no está definida, los valores monetarios definidos por la variable [`products`](../page-vars/products.md) y los eventos de moneda se tratan como si fueran iguales a la moneda del grupo de informes. Consulte [Configuración general de cuenta](/help/admin/admin/general-acct-settings-admin.md) en la guía del usuario de administración para ver la moneda del grupo de informes.

Si `currencyCode` está definida y coincide con la moneda del grupo de informes, no se aplica ninguna conversión de moneda.

Si `currencyCode` está definida y es diferente a la moneda del grupo de informes, Adobe aplica una conversión de moneda basada en el tipo de cambio del día actual. Adobe se asocia con [XE](https://xe.com) para convertir moneda cada día. Todos los valores almacenados en los servidores de recopilación de datos se almacenan finalmente en la moneda del grupo de informes.

>[!IMPORTANT]
>
>Si `currencyCode` contiene un valor no válido, se descarta toda la visita, lo que provoca la pérdida de datos. Asegúrese de que esta variable esté correctamente definida si la utiliza en la implementación.

Esta variable no persiste entre visitas. Asegúrese de que esta variable esté definida en todas las páginas que involucren eventos de ingresos o de moneda.

## Código de moneda en Adobe Experience Platform Launch

Código de moneda es un campo en el acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Código de moneda].

Puede utilizar un código de moneda preestablecido o un código de moneda personalizado. Si utiliza un código de moneda personalizado, asegúrese de que el código sea válido.

## Código de moneda en Adobe Experience Platform Mobile SDK

El código de moneda se pasa a los SDK de Adobe Experience Platform Mobile a través de variables de datos de contexto en la extensión de Adobe Analytics.

1. Configure el código de moneda en una variable de datos de contexto durante `trackState` o `trackAction`.
2. Cree una regla de procesamiento en admin console de Adobe Analytics para el grupo de informes. Configure la regla para sobrescribir la variable Código de moneda.
3. Pase el código de moneda a la variable `products` en su llamada para `trackState` o `trackAction`.

Puede utilizar un código de moneda preestablecido o un código de moneda personalizado. Si utiliza un código de moneda personalizado, asegúrese de que el código sea válido.

## s.currencyCode en el editor de código personalizado de AppMeasurement y Launch

La variable `s.currencyCode` es una cadena que contiene un código en mayúsculas de 3 letras que representa la moneda de la página.

```js
s.currencyCode = "USD";
```

Los siguientes códigos de moneda son válidos:

| Código de moneda | Descripción de moneda |
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
| `BRL` | Real |
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
| `DJF` | Franco de Djibouti |
| `DKK` | Corona danesa |
| `DOP` | Peso dominicano |
| `DZD` | Dinar argelino |
| `EEK` | Corona estonia |
| `EGP` | Libra egipcia |
| `ERN` | Nakfa de Eritrea |
| `ETB` | Birr de Etiopía |
| `EUR` | Euro |
| `FJD` | Dólar fijiano |
| `FKP` | Libra malvinense |
| `GBP` | Libra esterlina |
| `GEL` | Lari georgiano |
| `GGP` | Libra de Guernesey |
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
| `KZT` | Tenge de Kazajstán |
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
