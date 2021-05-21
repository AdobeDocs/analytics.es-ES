---
title: Creación de una capa de datos
description: Descubra qué es una capa de datos en su implementación de Analytics y cómo se puede utilizar para asignar variables en Adobe Analytics.
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '479'
ht-degree: 100%

---

# Creación de una capa de datos

Una capa de datos es un marco de objetos de JavaScript del sitio que contiene todos los valores de variables utilizados en la implementación. Permite un mayor control y un mantenimiento más sencillo en la implementación.

## Requisitos previos

[Crear un documento de diseño de solución](solution-design.md): es importante que su organización se alinee en los requisitos de seguimiento. Asegúrese de estar listo con un documento de diseño de solución antes de ponerse en contacto con los equipos de desarrollo de su organización.

## Flujo de trabajo

La implementación de Adobe Analytics mediante una capa de datos suele seguir estos pasos:

1. **Trabaje con el equipo de desarrollo del sitio para implementar una capa de datos**: El equipo de desarrollo del sitio es el principal responsable de asegurarse de que el objeto de capa de datos se rellene con los valores correctos. Revise esta página con el equipo de desarrollo del sitio para asegurarse de que las expectativas estén alineadas entre los equipos.

   >[!NOTE]
   >
   >Seguir las especificaciones de capa de datos recomendadas por Adobe es opcional. Si ya dispone de una capa de datos o decide no seguir las especificaciones de Adobe, asegúrese de que su organización se ajuste a las siguientes especificaciones.
1. **Valide la capa de datos con una consola de explorador**: Una vez creada una capa de datos, puede validar que funcione con cualquier consola de desarrollador del explorador. Puede abrir la consola de desarrollador en la mayoría de los exploradores con la clave `F12`. Un valor de variable de ejemplo sería `digitalData.page.pageInfo.pageID`.
1. **Utilice Adobe Experience Platform Launch para asignar objetos de capa de datos a elementos de datos de Launch**: Cree elementos de datos en Launch y asígnelos a los atributos de JavaScript descritos en la capa de datos.
1. **Utilice la extensión de Adobe Analytics en Launch para asignar elementos de datos a variables de Analytics**: De acuerdo con el documento de diseño de la solución, asigne cada elemento de datos a la variable de Analytics correspondiente.

## Especificaciones

Adobe recomienda seguir la [capa de datos digitales de la experiencia del cliente](https://www.w3.org/2013/12/ceddl-201312.pdf) descrita por el [grupo de la comunidad de datos digitales de la experiencia del cliente](https://www.w3.org/community/custexpdata/). Utilice las siguientes secciones para comprender cómo interactúan los elementos de la capa de datos con Adobe Analytics.

El objeto de capa de datos que se recomienda usar es `digitalData`. En el ejemplo siguiente se muestra un objeto JSON de capa de datos bastante completo con valores de ejemplo:

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

Utilice el informe [Capa de datos digital de la experiencia del cliente](https://www.w3.org/2013/12/ceddl-201312.pdf) para obtener detalles sobre cada objeto y subobjeto. No todos los sitios utilizan todos los objetos; por ejemplo, si aloja un sitio de noticias, es poco probable que lo haya utilizado para la matriz de objetos `digitalData.product`.

Las capas de datos son extensibles; si tiene requisitos específicos de su organización, puede incluir objetos en su capa de datos para satisfacer esas necesidades.

## Configuración de los valores de la capa de datos

Las capas de datos se generan en el servidor, que hacen referencia a los mismos objetos utilizados para generar el contenido del sitio. Establezca la capa de datos del sitio en función de los requisitos de seguimiento establecidos en el [documento de diseño de la solución](solution-design.md) de su organización.

## Pasos siguientes

[Asignar objetos de capa de datos a elementos de datos](../launch/layer-to-elements.md): utilice la capa de datos del sitio en Adobe Experience Platform Launch.
