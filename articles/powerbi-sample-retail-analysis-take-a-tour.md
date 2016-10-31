<properties
   pageTitle="Ejemplo de análisis de venta directa para Power BI: un paseo"
   description="Ejemplo de análisis de venta directa para Power BI: un paseo"
   services="powerbi"
   documentationCenter=""
   authors="amandacofsky"
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
   ms.date="07/18/2016"
   ms.author="amac"/>

# <a name="retail-analysis-sample-for-power-bi:-take-a-tour"></a>Ejemplo de análisis de venta directa para Power BI: un paseo

##  <a name="about-the-retail-analysis-sample"></a>Acerca del ejemplo de análisis de venta directa

Este panel de ejemplo del sector y el informe subyacente analizan minoristas datos de ventas de artículos vendidos en varios almacenes y distritos. Las métricas comparan el rendimiento de este año a año anterior en estas áreas: ventas, unidades, margen bruto y Varianza, así como las nuevas tiendas analysis. Se trata de datos reales de obviEnce ([www.obvience.com](http://www.obvience.com)) que se han anonimizado.

También puede [Descargar sólo el conjunto de datos (libro de Excel) para este ejemplo](http://go.microsoft.com/fwlink/?LinkId=528592).

![](media/powerbi-sample-retail-analysis-take-a-tour/retail1.png)

##  <a name="start-on-the-dashboard-and-open-the-report"></a>Iniciar en el panel y abra el informe

1.  En el panel, seleccione el icono "Tiendas Total":

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail-analysis-7.png)  

    Esto le lleva a la página "Información general de ventas de la tienda" en el informe. Verá que tenemos 104 almacenes total, 10 de las nuevas. Tenemos dos cadenas, modas directa y Lindseys. Almacenes directa de moda en promedio son más grandes.

2.  En el gráfico circular, seleccione **modas directa**.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail3.png)  

    Observe el resultado en el gráfico de burbujas:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlBubbles.png)  

    FD-01 distrito tiene el mayor promedio de ventas por pie cuadrado, FD-02 tiene la varianza más bajo en ventas en comparación con el año pasado, FD-03 y 04 FD son peor ejecutantes general.

3.  Seleccione las burbujas individuales u otros gráficos para ver cross resaltado, revelar el impacto de las selecciones.

4.  Seleccione Power BI en la barra de navegación superior para volver al panel.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail-analysis.png)

5.  En el panel, seleccione el icono con "Ventas de este año."

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlThisYrSales.png)

    Esto equivale a escribir "ventas de este año" en el cuadro de pregunta.

    Ver esta pantalla:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail7.png)

##  <a name="review-a-tile-created-with-power-bi-q&a"></a>Revise un mosaico creado con Power BI Q & A

Vamos a obtener más específica.

1.  Agregar "ventas este año **por distrito**" a la pregunta. Observe el resultado: coloca la respuesta en un gráfico de barras y sugiere otras frases automáticamente:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail8.png)

2.  Ahora, cambie la pregunta "ventas este año **zip y cadena**".

    Observe cómo responde a la pregunta a medida que escribe con los gráficos adecuados.

3.  Jugar con más preguntas y ver qué tipo de resultados obtiene.

4.  Cuando esté listo, vuelva al panel seleccionando Power BI en la esquina superior izquierda.

##  <a name="dive-deeper-into-the-data"></a>Profundice en los datos

Ahora vamos a explorar en un nivel más detallado, examinando las prestaciones de los distritos.

1.  En el panel, seleccione el icono de comparar las ventas de este año a año pasado.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlAreaCht.png)

    Observe la gran variabilidad en variación % para el año pasado, con enero, abril y especialmente mal meses de julio.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/PBI_Sample_RetAnlSalesVarCol.png)

    Veamos si reducir donde pueden ser los problemas.

2.  Seleccione el gráfico de burbujas y elija **020 hombres**.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail11.png)  

    Observe la categoría de los hombres no fue como gravemente afectados en abril como el negocio global, pero enero y julio seguían siendo meses del problema.

3.  Ahora, seleccione la **burbujas 010-Womens**.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail12.png)

    Aviso de categoría de la mujer realiza mucho peor que el negocio global para todos los meses y mucho peor en casi todos los meses en comparación con el año anterior.

4.  Seleccione la burbuja de nuevo para borrar el filtro.

##  <a name="try-out-the-slicer"></a>Pruebe la segmentación de datos

Echemos un vistazo hacen en los distritos de forma específicos.

1.  Seleccione Allan Guinot en la segmentación de datos en la parte superior izquierda.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail13.png)

    Tenga en cuenta que el distrito Allan superaba el año pasado en marzo y junio.

2.  Ahora, mientras sigue seleccionado Allan, seleccione burbujas de la mujer.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail14.png)

    Tenga en cuenta que para la categoría de la mujer, su distrito nunca cumple volumen del año pasado.

3.  ¿3. explorar los demás administradores de distrito y categorías: qué otra información puede buscar?

4.  Cuando esté listo, vuelva al panel.

## <a name="what-is-our-data-telling-us-about-sales-growth-this-year?"></a>¿Qué es nuestros datos contarnos sobre el crecimiento de ventas este año?

La última área que deseamos explorar es nuestro crecimiento: nuevos almacenes abierto este año.

1.  Seleccione el icono 'Almacenes abierto este año'.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/retail15.png)

    Como evidentes desde el icono – más directa de moda almacena de almacenes de Lindseys abre este año.

2.  Tenga en cuenta las ventas por Sq Ft gráfico de nombre:

    ![](media/powerbi-sample-retail-analysis-take-a-tour/15.png)

     Hay gran cantidad de diferencia de promedio de ventas por SQF entre las nuevas tiendas.

3.  Haga clic en el elemento de leyenda modas directa en el gráfico superior derecho. Aviso, incluso para la misma cadena, el mejor almacén (Winchester modas directo) significativamente supera el peor vs $21.22 de almacén (Cincinnati 2 modas directo) $12.86 respectivamente.

    ![](media/powerbi-sample-retail-analysis-take-a-tour/17b.png)

4.  Haga clic en Winchester modas directa en la segmentación de datos y observe el gráfico de líneas. Las cifras de ventas primeras se han informado en febrero y es un almacén líder en términos de volumen para casi todos los meses.

5.  Haga clic en Cincinnati 2 modas directa en la segmentación de datos y aparecerá en el gráfico de líneas que se ha abierto en junio y parece ser el almacén de peor rendimiento.

6.  Como antes, explore haciendo clic en otras barras, líneas y burbujas a lo largo de los gráficos y vea qué información puede detectar.

Se trata de un entorno seguro para reproducir en. Siempre puede elegir no guardar los cambios. Pero si guardarlos, siempre puede ir para obtener datos de una copia nueva de este ejemplo.

## <a name="next-steps:-connect-to-your-data"></a>Pasos siguientes: conectarse a los datos

Esperamos que este paseo le ha mostrado cómo paneles de Power BI, preguntas y respuestas, y los informes pueden proporcionar información sobre los datos de venta directa. Ahora es su turno, conectarse a sus propios datos. Con Power BI puede conectarse a una gran variedad de orígenes de datos. Obtenga más información sobre [Introducción a Power BI](https://support.office.com/article/Get-Started-with-Power-BI-Preview-0f0237e2-f74f-49ab-82ea-1990c3c3deb8).

## <a name="see-also"></a>Consulte también

-   
            [Descargar el paquete de contenido de ejemplo de análisis de venta directa](powerbi-sample-tutorial-connect-to-the-samples.md)
-   
            [Descargue el libro de Excel para este ejemplo de Power BI](http://go.microsoft.com/fwlink/?LinkId=528592)
-   
            [Obtener datos (Power BI)](powerbi-service-get-data.md)
-   
            [Power BI: conceptos básicos](powerbi-service-basic-concepts.md)
-  ¿Preguntas más frecuentes? 
            [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
