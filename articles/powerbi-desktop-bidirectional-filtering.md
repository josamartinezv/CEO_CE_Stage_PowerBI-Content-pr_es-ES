<properties
   pageTitle="Bidireccional entre filtrado en Power BI Desktop (vista previa)"
   description="Habilitar filtrado entre usar DirectQuery en Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
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
   ms.date="09/29/2016"
   ms.author="davidi"/>

# Bidireccional entre filtrado mediante DirectQuery en Power BI Desktop (vista previa)

Al filtrar tablas para crear la vista de datos adecuada, creadores de informes (y modelado de datos) se enfrenta a desafíos al determinar cómo se aplica el filtro a un informe; el contexto de filtro de una tabla se mantiene en un lado de la relación, pero no el otro, que a menudo requieren complejas fórmulas DAX para obtener los resultados deseados.

Con bidireccional filtro cruzado, creadores de informes (y modelado de datos) ahora tiene más control sobre cómo se aplican los filtros al trabajar con tablas relacionadas, habilitar los filtros se apliquen en *ambos* lados de una relación de tabla. Esto se consigue haciendo que el contexto de filtro que se propagan a una segunda tabla relacionada en el otro lado de una relación de tabla.

Un [notas del producto detalladas](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) está disponible que explica bidireccional entre filtrado en Power BI Desktop (las notas del producto también cubre 2016 de SQL Server Analysis Services, ambos tienen el mismo comportamiento).

-   Descargue el [bidireccional entre filtrado para Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) notas del producto

### Habilitar bidireccional entre filtrado para DirectQuery

Para poder utilizar el filtrado cruzado para DirectQuery, primero debe habilitarlo. Se trata de características de vista previa, lo que significa que su disponibilidad y comportamiento está sujeta a cambios en futuras versiones de Power BI Desktop.

Para habilitar el filtrado cruzado para DirectQuery en Power BI Desktop, seleccione **archivo > Opciones y configuración > opciones**, a continuación, active la casilla junto a **Habilitar filtrado cruzado en ambas direcciones para DirectQuery**, como se muestra en la siguiente imagen.

![](media/powerbi-desktop-bidirectional-filtering/bidirectional-filtering_1.png)

> 
            **Nota:** al crear fórmulas DAX en Power BI Desktop de filtrado cruzado, use *UserPrincipalName* (que suele ser el mismo que el inicio de sesión de un usuario, como *joe@contoso.com*) en lugar de *nombre de usuario*. Por lo tanto, puede que necesite crear una tabla relacionada que asigna *nombre de usuario* (o identificador de empleado, por ejemplo) a *UserPrincipleName*.

Para habilitar el filtrado de cruzados, en la **Editar relación** se debe seleccionar el cuadro de diálogo para una relación, la siguiente:

-   El **entre la dirección del filtro** debe establecerse en **ambos**
-   El **aplicar el filtro de seguridad en ambas direcciones** también debe estar activada

    ![](media/powerbi-desktop-bidirectional-filtering/bidirectional-filtering_2.png)

Para obtener más información y ejemplos de cómo funciona el filtro cruzado bidireccional, consulte el [notas del producto](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) mencionado anteriormente en este artículo.
