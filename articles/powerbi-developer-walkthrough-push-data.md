<properties
   pageTitle="Insertar datos en un panel"
   description="Insertar datos en un panel de Power BI"
   services="powerbi"
   documentationCenter=""
   authors="guyinacube"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="monitoring"
   qualityDate="04/15/2016"/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="08/23/2016"
   ms.author="asaxton"/>

# Insertar datos en un panel de Power BI

Con la API de Power BI, puede insertar datos en un panel de Power BI. Por ejemplo, desea ampliar un flujo de trabajo existente para insertar datos de la clave en el panel. En este caso, desea insertar un conjunto de datos de Marketing de ventas que tiene una tabla de productos en un panel.

Antes de empezar a insertar datos en un panel, necesita un Azure Active Directory (Azure AD) y un [cuenta de Power BI](powerbi-admin-free-with-custom-azure-directory.md).

Para obtener información sobre cómo insertar un conjunto de datos en un panel, siga estos pasos. En el ejemplo, inserte un conjunto de datos de Marketing de ventas con una tabla de productos en un panel.

## Pasos para insertar un conjunto de datos en un panel

- Paso 1: [registrar una aplicación con Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)
- Paso 2: [obtener un acceso de autenticación token](powerbi-developer-walkthrough-push-data-get-token.md)
- Paso 3: [crear un conjunto de datos en un panel de Power BI](powerbi-developer-walkthrough-push-data-create-dataset.md)
- Paso 4: [obtener un conjunto de datos para agregar filas a una tabla de Power BI](powerbi-developer-walkthrough-push-data-get-datasets.md)
- Paso 5: [Agregar filas a una tabla de Power BI](powerbi-developer-walkthrough-push-data-add-rows.md)

La siguiente sección es una discusión general de las operaciones de API de Power BI que insertar los datos.

## Operaciones de API de BI de energía para insertar datos

Con la API de REST de Power BI, puede insertar los orígenes de datos a Power BI. Cuando una aplicación agrega filas a un conjunto de datos, los iconos del panel se actualizan automáticamente con los datos actualizados. Para insertar datos, utiliza la [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx) operación junto con el [Agregar filas](https://msdn.microsoft.com/library/mt203561.aspx) operación. Para buscar un conjunto de datos, puede utilizar el [obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx) operación. Para cualquiera de estas operaciones, puede pasar un identificador de grupo para trabajar con un grupo. Utilice la [obtener grupos](https://msdn.microsoft.com/library/mt243842.aspx) operación para obtener una lista de identificadores de grupo

Estas son las operaciones para insertar datos en un panel:

- [Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx)
- [Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx)
- [Agregar filas](https://msdn.microsoft.com/library/mt203561.aspx)
- [Obtener grupos](https://msdn.microsoft.com/library/mt243842.aspx)

Crear un conjunto de datos en Power BI pasando una cadena de JavaScript Object Notation (JSON) para el servicio Power BI. Para obtener más información sobre JSON, vea [Introducing JSON](http://json.org/).

La cadena JSON para un conjunto de datos tiene el formato siguiente:

**Objeto JSON del conjunto de datos de BI de energía**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

Por lo tanto, en nuestro ejemplo de conjunto de datos de Marketing de ventas, deberá pasar una cadena JSON como en el ejemplo siguiente. En este ejemplo, **SalesMarketing** es el nombre del conjunto de datos, y **producto** es el nombre de la tabla. Después de definir la tabla, definir el esquema de tabla. Para el **SalesMarketing** conjunto de datos, el esquema de tabla tiene las siguientes columnas: ProductID, fabricante, categoría, segmento, producto y IsCompete.

**Objeto de conjunto de datos de ejemplo JSON**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Para un esquema de tabla Power BI, puede usar los siguientes tipos de datos.

## Tipos de datos de tabla de Power BI

|**Tipo de datos**|**Restricciones**
|---|---
|Int64|Int64.MaxValue e Int64.MinValue no están permitidos.
|Double|Double.MaxValue y Double.MinValue no permitido. NaN no se admite. + Infinity y - Infinity no se admiten en algunas funciones (por ejemplo, Min, Max).
|Boolean|Ninguno
|Datetime|Durante la carga de datos se cuantifican valores con fracciones de día a múltiplos enteros de 1/300 segundos (3,33 ms).
|String|Actualmente permite hasta 128 K caracteres.


## Más información acerca de cómo insertar datos en Power BI

Para comenzar a insertar datos en un panel, consulte [paso 1: registrar una aplicación con Azure AD](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md) en el panel de navegación izquierdo.

[Siguiente paso >](powerbi-developer-walkthrough-push-data-register-app-with-azure-ad.md)

## Consulte también

[Registrarse para Power BI](powerbi-admin-free-with-custom-azure-directory.md)  
[Crear conjunto de datos](https://msdn.microsoft.com/library/mt203562.aspx)  
[Obtener conjuntos de datos](https://msdn.microsoft.com/library/mt203567.aspx)  
[Agregar filas](https://msdn.microsoft.com/library/mt203561.aspx)  
[Obtener grupos](https://msdn.microsoft.com/library/mt243842.aspx)  
[Introducción a JSON](http://json.org/)  
[Información general sobre la API de REST de Power BI](powerbi-developer-overview-of-power-bi-rest-api.md)  
¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)