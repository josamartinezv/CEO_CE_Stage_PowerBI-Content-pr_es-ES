<properties pageTitle="Ejemplo de documentación - tablas HTML" description="Esto es un ejemplo de documento" title="Documentation Example - HTML Tables" services="" documentationCenter="" metaKeywords="" solutions="" authors="" videoId="" scriptId="" />


# Por ejemplo, tablas HTML
Se trata de un artículo de la documentación de ejemplo que se usa para probar y validar el sistema de publicación para azure.microsoft.com.  

El contenido entre las líneas siguientes se muestra que el uso de HTML con formato de tablas.  Observe que cada cierre de la etiqueta de tabla es seguido por `<br />`. Esto es necesario (a partir de 2014-01-01) por azure.microsoft.com y también por GitHub para evitar errores en el formato de descuento.  

---

## ¿Es la versión de Hadoop en HDInsight de Microsoft Azure?

HDInsight admite varias versiones de clústeres que se pueden implementar en cualquier momento. Cada versión aprovisiona una versión específica de la distribución de HortonWorks Data Platform (HDP) y un conjunto de componentes que están incluidos en esa distribución.

## Versiones de HDInsight

### Versión 2.1 del clúster

La versión de clúster predeterminada utilizada por [Microsoft Azure HDInsight](http://go.microsoft.com/fwlink/?LinkID=285601) es la 2.1. Se basa en la versión 1.3.0 de Hortonworks Data Platform y proporciona servicios de Hadoop con las versiones de los componentes incluidas en la tabla siguiente:

<table border="1">
<tr><th>Componente</th><th>Version</th></tr>
<tr><td>Apache Hadoop</td><td>1.2.0</td></tr>
<tr><td>Apache Hive</td><td>0.11.0</td></tr>
<tr><td>Apache Pig</td><td>0.11</td></tr>
<tr><td>Apache Sqoop</td><td>1.4.3</td></tr>
<tr><td>Oozie de Apache</td><td>3.2.2</td></tr>
<tr><td>Apache HCatalog</td><td>Fusionado con Hive</td></tr>
<tr><td>Apache Templeton</td><td>Fusionado con Hive</td></tr>
<tr><td>Ambari</td><td>La API v1.0</td></tr>
</table><br/>


### Versión 1.6 del clúster


            [Microsoft Azure HDInsight](http://go.microsoft.com/fwlink/?LinkID=285601) también está disponible la versión 1.6 del clúster. Se basa en la versión 1.1.0 de Hortonworks Data Platform y proporciona servicios de Hadoop con las versiones de los componentes incluidas en la tabla siguiente:

<table border="1">
<tr><th>Componente</th><th>Version</th></tr>
<tr><td>Apache Hadoop</td><td>1.0.3</td></tr>
<tr><td>Apache Hive</td><td>0.9.0</td></tr>
<tr><td>Apache Pig</td><td>0.9.3</td></tr>
<tr><td>Apache Sqoop</td><td>1.4.2</td></tr>
<tr><td>Oozie de Apache</td><td>3.2.0</td></tr>
<tr><td>Apache HCatalog</td><td>0.4.1</td></tr>
<tr><td>Apache Templeton</td><td>0.1.4</td></tr>
<tr><td>Controlador JDBC de SQL Server</td><td>3.0</td></tr>
</table><br/>


## Seleccione una versión al aprovisionar un clúster de HDInsight

Al crear un clúster mediante los Cmdlets de PowerShell de HDInsight o el SDK de .NET de HDInsight, puede elegir una versión mediante el parámetro "Versión".

Si utiliza el **creación rápida** opción, obtendrá la versión 2.1. Si utiliza el **creación personalizada** opción desde el Portal de Microsoft Azure, puede elegir la versión del clúster que implementará desde la lista desplegable en la HDInsight versión la **Detalles del clúster** página.

## Versiones compatibles
En la tabla siguiente se enumera las versiones de HDInsight está disponible, las versiones correspondientes de Hortonworks Data Platform (HDP) que utilizan y sus fechas de lanzamiento. Si se conocen, también se proporcionará la fecha de degradación.

<table border="1">
<tr><th>Versión de HDInsight</th>
<th><a href="http://go.microsoft.com/fwlink/?LinkID=286746">Versión de HDP</a></th>
<th>Fecha de lanzamiento</th></tr>
<tr><td>HDI 1.6</td><td>HDP 1.1</td><td>10/28/2013</td></tr>
<tr><td>HDI 2.1</td><td>HDP 1.3</td><td>10/28/2013</td></tr>
</table><br/>

---

[Connect-excel-with-hive-ODBC]: /manage/services/hdinsight/connect-excel-with-hive-ODBC/

[HDP-1-3-0]: http://docs.hortonworks.com/HDPDocuments/HDP1/HDP-1.3.0/bk_releasenotes_hdp_1.x/content/ch_relnotes-hdp1.3.0_1.html

[HDP-1-1-0]: http://docs.hortonworks.com/HDPDocuments/HDP1/HDP-Win-1.1/bk_releasenotes_HDP-Win/content/ch_relnotes-hdp-win-1.1.0_1.html

