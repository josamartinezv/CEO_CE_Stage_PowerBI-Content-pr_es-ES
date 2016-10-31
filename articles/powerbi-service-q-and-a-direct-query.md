<properties
   pageTitle="Uso de preguntas y respuestas con Power BI Gateway - datos de la empresa (vista previa)"
   description="Documentación para usar Power BI Q & A consultas en lenguaje natural con datos de la consulta directa y puerta de enlace empresarial."
   services="powerbi"
   documentationCenter=""
   authors="mihart"
   manager="mblythe"
   backup="fetiye"
   editor=""
   tags=""
   qualityFocus="no"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="07/07/2016"
   ms.author="mihart"/>


# Habilitar preguntas y respuestas para la consulta directa (vista previa)

##  ¿Qué es la puerta de enlace de datos local?  ¿Qué es DirectQuery?

Conjuntos de datos en Power BI pueden importarse en Power BI o puede crear una conexión activa con ellos. Live conexión conjuntos de datos a menudo se conocen como "local". Las conexiones dinámicas se administran mediante un [puerta de enlace](powerbi-gateway-onprem.md) y datos y las consultas se envían y hacia atrás mediante DirectQuery.

##  Preguntas y respuestas para conjuntos de datos de puerta de enlace de datos local

Si desea usar preguntas y respuestas con acceso a través de una puerta de enlace de conjuntos de datos, debe habilitarlas primero.

Una vez habilitado, Power BI crea un índice de origen de datos y carga de un subconjunto de los datos en Power BI para habilitar formulando preguntas. Puede tardar varios minutos en crear el índice inicial y Power BI mantiene y actualiza el índice automáticamente como los cambios de datos. Uso de preguntas y respuestas con estos conjuntos de datos comporta del mismo modo con los datos publicados en Power BI. Se admite el conjunto completo de características disponibles en las preguntas y respuestas una experiencia en ambos casos, incluido el uso del origen de datos con Cortana.

Cuando formule preguntas en Power BI, preguntas y respuestas determina el mejor visual a la construcción o informe hoja que desea utilizar para responder su pregunta con un índice del conjunto de datos. Después de determinar la mejor respuesta posible, Q & A utiliza DirectQuery para capturar los datos en directo desde el origen de datos a través de la puerta de enlace de la empresa para rellenar gráficos y gráficos. Esto garantiza que Power BI Q & un resultados siempre muestran los datos más actualizados directamente desde el origen de datos subyacente.

Desde Power BI Q & A los valores de texto y el esquema del origen de datos utiliza para determinar cómo consultar el modelo subyacente para las respuestas, busca valores de texto nuevos o eliminados específico (por ejemplo, pedir un nombre de cliente relacionado con un registro de texto recién agregado) se basan en el índice está actualizado con los valores más recientes. Power BI mantiene automáticamente el índice de texto y el esquema actualizado en una ventana de 60 minutos de cambios.


Para obtener más información, vea:

- ¿Qué es el [puerta de enlace de datos local](powerbi-gateway-onprem.md)?

- [Introducción a Power BI Q & A](powerbi-service-q-and-a.md)


##  Habilitar preguntas y respuestas
Una vez que la puerta de enlace de empresa configurado, conectarse a los datos de Power BI.  Cree un panel con sus datos locales, o cargar un archivo .pbix que usa datos locales.  Además, ya puede tener datos locales en los paneles, informes y conjuntos de datos que se han compartido con usted.

1.  En la esquina superior derecha de Power BI, seleccione el icono de engranaje ![](media/powerbi-service-q-and-a-direct-query/power-bi-cog.png) y elija **configuración**.

    ![](media/powerbi-service-q-and-a-direct-query/powerbi-settings.png)

2.  Seleccione **conjuntos de datos** y elija el conjunto de datos para habilitar para preguntas y respuestas.

    ![](media/powerbi-service-q-and-a-direct-query/power-bi-q-and-a-settings.png)

3. Expanda **preguntas y respuestas y Cortana**, seleccione la casilla de verificación **Activar preguntas y respuestas para este conjunto de datos** y elija **aplicar**.

    ![](media/powerbi-service-q-and-a-direct-query/power-bi-q-and-a-directquery.png)



##  ¿Qué datos se almacenan en caché y cómo se protege la privacidad?

Al habilitar preguntas y respuestas para los datos locales, se almacena en caché un subconjunto de los datos en el servicio. Esto se hace para asegurarse de que Q & A funciona con un rendimiento aceptable. Valores de más de 24 caracteres se exclusión del almacenamiento en caché. La memoria caché se elimina en unas pocas horas, cuando deshabilite preguntas y respuestas desactivando **Activar preguntas y respuestas para este conjunto de datos**, o cuando se elimina el conjunto de datos.

##  Limitaciones durante la vista previa pública
Durante la fase de vista previa de esta característica, existen varias limitaciones:

- Inicialmente, la característica solo está disponible para orígenes de datos de Analysis Services de SQL Server 2016. La característica está optimizada para trabajar con datos tabulares. Alguna funcionalidad está disponible para orígenes de datos multidimensionales, pero la experiencia completa de preguntas y respuestas aún no se admite para este tipo de conjunto de datos. Orígenes de datos adicionales admitidos por la puerta de enlace de la empresa se implementarán durante la vista previa.

- Compatibilidad completa para la seguridad de nivel de fila definida en SQL Server Analysis Services no está disponible inicialmente en la vista previa. Al formular preguntas en preguntas y respuestas, el "Autocompletar" de preguntas mientras escribe puede mostrar valores de cadena de un usuario no tiene acceso a. Sin embargo, se respeta RLS definido en el modelo de informe y el gráfico de objetos visuales por lo que no se puede exponer ningún dato numérico subyacente. Opciones para controlar este comportamiento se lanzará en próximas actualizaciones.

- Preguntas y respuestas no funcionan con orígenes de datos de Power BI Personal Gateway.

## Consulte también

[Power BI rápida visión](powerbi-service-auto-insights.md)

[Optimizar los datos de visión rápida de Power BI](powerbi-service-auto-insights-optimize.md)

[Power BI: conceptos básicos](powerbi-service-basic-concepts.md)

[Paneles de Power BI](powerbi-service-dashboards.md)

¿Preguntas más frecuentes? [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
