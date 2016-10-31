<properties
   pageTitle="Sugerencias y trucos para la creación de informes en Power BI Desktop"
   description="Sugerencias y trucos para la creación de informes en Power BI Desktop"
   services="powerbi"
   documentationCenter=""
   authors="davidiseminger"
   manager="mblythe"
   backup=""
   editor=""
   tags=""
   qualityFocus="identified"
   qualityDate=""/>

<tags
   ms.service="powerbi"
   ms.devlang="NA"
   ms.topic="article"
   ms.tgt_pltfrm="NA"
   ms.workload="powerbi"
   ms.date="09/29/2016"
   ms.author="davidi"/>
# Sugerencias y trucos para la creación de informes en Power BI Desktop

Para obtener el máximo provecho de los datos, a veces es necesario un poco de ayuda adicional. Hemos reunido algunos consejos y trucos que puede utilizar al crear informes en Microsoft Power BI Desktop *y* en Microsoft Excel 2016 o ediciones de Excel 2013 Pro-Plus con Power Pivot complemento habilitado y Power Query instalado y habilitado. 


## Aprender a usar el Editor de consultas

Editor de consultas en Power BI Desktop es similar a la capacidad de agregar en Power Query en Excel 2013. Aunque existen varios artículos útiles en soporte técnico de Power BI, también puede consultar la documentación de Power Query en support.office.com para comenzar.

Puede obtener información adicional de la [Centro de recursos de energía consulta](https://support.office.com/article/Microsoft-Power-Query-for-Excel-Help-2b433a85-ddfb-420b-9cda-fe0e60b82a94).

También puede ver el [referencia de fórmula](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

## Tipos de datos en el Editor de consultas

Cuando se utiliza el Editor de consultas en Power BI Desktop para cargar datos, hacemos una mejor detección de tipo de datos de suposición.  Al utilizar las fórmulas, a veces la configuración de tipo de datos en columnas no se conserva. Debe comprobar el tipo de datos de columnas son correctos después de realizar las siguientes operaciones: cargar datos inicialmente en la ficha de consulta, la primera fila como encabezado de columna Add, agrupar por, combinación, anexar y antes de presionar la carga de los datos por primera vez.

Un punto clave que debe recordar: cursiva en la cuadrícula de datos no significa que los datos de tipo está correctamente configurado, simplemente significa que los datos no se consideran como texto.

## Consultas de referencia en el Editor de consultas

En el navegador del Editor de consultas, cuando haga una de las consultas, está disponible una opción para "Referencia".  Esto resulta útil por el siguiente motivo:

-   Cuando se utilizan archivos como el origen de datos para una consulta, la ruta de acceso absoluta al archivo se almacena en la consulta. Al compartir o mover el archivo de Power BI Desktop o un libro de Excel, ahorrará tiempo cuando actualice las rutas actualizándola sólo una vez, en lugar de las rutas de acceso.

De forma predeterminada todas las consultas se cargan en una hoja de cálculo de Excel o el modelo de datos (o ambos). Algunas consultas son pasos intermedios y no está diseñado para usuarios finales.  Cuando se hace referencia a las consultas como se mencionó anteriormente, suele ser el caso.  Puede controlar la consulta haciendo clic a la consulta en el explorador y alternar la opción "Habilitar carga" comportamiento de carga.  Cuando "Habilitar carga" no tiene una marca de verificación junto a ella, la consulta sigue siendo estén disponibles en la ficha consulta, se puede utilizar con otras consultas.  Es especialmente útil en combinación con la mezcla, anexar, y transforma de referencia.  Sin embargo ya que los resultados de la consulta no se cargan en el modelo de datos, la consulta abarroten la lista de campos de informes o el modelo de datos. 

## Necesario un identificador de punto de gráficos de dispersión

Se tomó teniendo un ejemplo de una tabla sencilla de las temperaturas y la hora de la lectura. Si traza directamente en un gráfico de dispersión, Power BI Desktop agrega todos los valores en un único punto. Para mostrar los puntos de datos individuales, tendrá para agregar un campo para el cubo de detalles en el campo bien.   Una manera sencilla de hacerlo es en la ficha consulta mediante la opción "Agregar la columna de índice" en la cinta de opciones "Add Column". 

## Líneas de referencia en el informe

Puede utilizar una columna calculada para definir una línea de referencia.  Identificar la tabla y columna en la que desea crear una línea de referencia.  Seleccione "Nueva columna" en la cinta de opciones y, en la barra de fórmulas, escriba la fórmula siguiente:

    Target Value = 100

Esto calcula la columna devolverá el valor 100 independientemente de donde se utiliza.  La nueva columna se mostrará en la lista de campos.  Agregar la columna calculada del valor de destino a un gráfico de líneas para mostrar cómo se relaciona cualquier serie a una línea de referencia específica.  

## Ordenar por otra columna

Cuando se utiliza un valor de categoría (cadena) en Power BI Desktop de los ejes del gráfico o en una segmentación de datos o un filtro, el orden predeterminado es alfabético. Si necesita cambiar este orden, por ejemplo para elementos como los días de la semana o meses, a continuación, se puede indicar Power BI Desktop para ordenar por una columna diferente. Para obtener más información, consulte [Ordenar por columna en Power BI Desktop](powerbi-desktop-sort-by-column.md).

## Crear mapas más fácilmente con sugerencias de Bing

Power BI se integra con Bing para proporcionar las coordenadas de la asignación predeterminada (es decir, un proceso denominado codificación geográfica) por lo que es más fácil para crear asignaciones.  Bing usa algunos algoritmos y sugerencias para intentar obtener la ubicación correcta, pero es una mejor aproximación.   Para aumentar la probabilidad de codificación de geográfica correcta, puede utilizar las siguientes sugerencias:

Cuando se crea un mapa, a menudo desea para trazar países, Estados y ciudades.  Si utiliza las columnas nombre después de la designación geográfica ayudará a Bing adivinar lo que necesita para mostrar. Por ejemplo, si tiene un campo de los nombres de estado de Estados Unidos como "California" y "Washington", Bing podría devolver la ubicación de Washington, DC, en lugar de Washington State de la palabra "Washington".  Nombre de la columna "Estado" mejorará las coordenadas geográficas.  El mismo es queda en columnas denominadas "Country", "State" y "Ciudad".   

Algunas designaciones son ambiguas Cuando se consideran en el contexto de varios países o regiones.  En algunos casos qué un país o región se considera un 'estado' se trata como un 'provincia' o una provincia' ' o alguna otra designación.  Puede aumentar la precisión de codificación geográfica mediante la creación de columnas que anexar varios campos juntos y utilizarlas para trazar las ubicaciones de los datos.  Un ejemplo sería en lugar de pasar sólo "Wiltshire", puede pasar "Wiltshire, Inglaterra" para obtener un resultado más preciso de codificación geográfica. 

Siempre puede proporcionar ubicaciones específicas de latitud y longitud.  Al hacerlo, también necesitará pasar un campo de ubicación, en caso contrario, los datos se agregan de forma predeterminada, por lo que la ubicación de la latitud y longitud no puede coincidir con lo que esperaba.

## Categorizar campos geográficos para obtener las coordenadas geográficas de Bing

En Power BI Desktop, puede asegurarse de campos de coordenadas geográficas correctamente estableciendo la categoría de datos en los campos de datos.   En Power BI Desktop, seleccione la tabla deseada, vaya a la cinta de opciones avanzada y, a continuación, Establece la categoría de datos en la dirección, ciudad, continente, país o región, país, código Postal, estado o provincia.  Estas categorías de datos ayudan a Bing para codificar correctamente la fecha. Para obtener más información, consulte [categorización de datos en Power BI Desktop](powerbi-desktop-data-categorization.md).

## Mejor codificación geográfica con ubicaciones más específicas

A veces, incluso al establecer las categorías de datos de asignación es insuficiente.  Puede crear una ubicación más específica como una dirección postal mediante el Editor de consultas en Power BI Desktop dentro de la consulta.  Use la característica Agregar columna para crear una columna personalizada.  A continuación cree la ubicación deseada como sigue: 

    = [Field1] & " " & [Field2]

A continuación, utilice este campo resultante en las visualizaciones de mapa. Esto es muy útil para la creación de direcciones de los campos de dirección de envío que son comunes en los conjuntos de datos.  Una nota es que la concatenación solo funciona con campos de texto.  Si es necesario, convierta al número de calle a un tipo de datos de texto antes de usarlo para generar una dirección.

## Histogramas en la fase de consulta

Hay varias maneras de crear histogramas, comenzaremos con la más sencilla y vaya a partir de ahí:

Histogramas más simples: determinar qué consulta tiene el campo que desea crear un histograma.  Utilice la opción de "Referencia" de la consulta para crear una consulta nueva y asígnele el nombre "FieldName histograma". Utilice la opción "Agrupar por" en la cinta de opciones de "Transformar" y seleccione el agregado "contar filas".  Asegúrese de que el tipo de datos es un número para la columna agregado resultante. A continuación, visualizar estos datos en la página informes.  Esto es rápido y fácil de crear, pero no funciona bien si tiene muchos puntos de datos y no permite roce en elementos visuales.

Definir cubos para crear un histograma: determinar qué consulta tiene el campo que desea crear un histograma en.  Utilice la opción de "Referencia" de la consulta para crear una nueva consulta y asígnele el nombre "FieldName".  Definir los cubos con una regla.  Use la opción de agregar columnas personalizadas en la cinta de opciones de Agregar columna y crear una regla personalizada.  Una regla de creación de depósitos sencilla podría tener este aspecto:

    if([FieldName] \< 2) then "\<2 min" else
    if([FieldName] \< 5) then "\<5 min" else
    if([FieldName] \< 10) then "\<10 min" else
    if([FieldName] \< 30) then "\<30 min" else
    "longer")

Asegúrese de que el tipo de datos es un número para la columna agregado resultante. Ahora puede usar el grupo mediante la técnica descrita en el histograma más sencilla para lograr el histograma.  Esta opción controla más puntos de datos, pero todavía no ayuda con roce.

Definir un histograma que admite roce: roce es cuando los elementos visuales se vinculan para que cuando un usuario selecciona un punto de datos en un objeto visual otros elementos visuales en la página informe de resaltan o filtrar los puntos de datos relacionados con el punto de datos seleccionado.  Dado que estamos manipular los datos en tiempo de consulta, necesitamos crear una relación entre tablas y asegúrese de que sabemos qué detalle de elemento se relaciona con el depósito en el histograma y viceversa.

Inicie el proceso mediante la opción "Referencia" en la consulta que tiene el campo que desea crear un histograma.  Nombre de la nueva consulta "Depósitos".  En este ejemplo vamos a llamar a la consulta original "Detalles".  A continuación, quite todas las columnas excepto la columna que se va a utilizar como el depósito del histograma.  Ahora utilice la característica "Quitar duplicados" en la consulta, es en el menú de clic cuando se selecciona la columna, por lo que los valores restantes son los valores únicos en la columna.   Si tiene números decimales se puede utilizar la sugerencia para definir cubos para crear un histograma para obtener un conjunto de depósitos administrable.  Ahora, compruebe los datos mostrados en la vista previa de la consulta.  Si ve valores en blanco o null debe corregirlas antes de crear una relación.  Consulte "Creación de una relación si Mis datos tienen valores nulos o en blanco".   Con este enfoque puede ser problemático debido a la necesidad de ordenar.  Para obtener los depósitos ordene correctamente, consulte "orden de clasificación: convertir las categorías aparecen en el orden deseado".  Nota: Es útil pensar en el criterio de ordenación antes de crear los elementos visuales.   

Siguiente paso del proceso es definir una relación entre las consultas "Empaqueta" y "Detalles" en la columna de depósitos.  En Power BI Desktop, haga clic en **Administrar relaciones** en la cinta de opciones.  Cree una relationsship que se encuentra en la tabla de la izquierda y los detalles de depósitos en la tabla derecha y seleccione el campo que utiliza para el histograma. 

Último paso es crear el histograma.  Arrastre el campo de depósitos de la tabla "Depósitos".  Quitar el campo predeterminado de un gráfico de columnas.  Ahora de la tabla "Detalles" Arrastre el campo de histograma en el mismo objeto visual.  En el depósito de campos, cambiar el agregado predeterminado para el recuento.  El resultado es el histograma. Si crea otro visual como un treemap desde la tabla de detalles, seleccione un punto de datos en treemap para ver el histograma resaltar y mostrar el histograma para el punto de datos seleccionado en relación con la tendencia de todo el conjunto de datos.

## Histogramas

Puede utilizar un campo calculado para definir un histograma.  Identificar la tabla y columna en la que desea crear un histograma.  En el área de cálculo, escriba la siguiente fórmula:
> Frecuencia: = COUNTROWS (\<nombre de columna\>)

Guarde los cambios y volver al informe.  Agregue el \<nombre de la columna\> y la frecuencia para una tabla, a continuación, convertir en un gráfico de barras.  Garantizar la \<nombre de columna\> está en el eje x y el campo calculado es de frecuencia en el eje y.

## Sugerencias y trucos para la creación de relaciones

A menudo al cargar conjuntos de datos de detalle de varios orígenes, problemas, como los valores nulos, valores en blanco o valores duplicados le impida la creación de relaciones. 

Veamos un ejemplo: 

Si se cargan los conjuntos de datos de cliente activo de solicitudes de soporte y otro conjunto de datos de elementos de trabajo que tienen esquemas como sigue:
> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, estado} elementos de trabajo: {WorkItemID, IncidentID, WorkItemName, OpenedDate, estado, NombreCliente} 

Cuando desea realizar un seguimiento de todos los incidentes y elementos de trabajo relacionados con un determinado un CustomerName, no podemos crear simplemente una relación entre estos dos conjuntos de datos.  Algunos elementos de trabajo pueden no estar relacionadas con un CustomerName, por lo que sería ese campo en blanco o NULL.  Puede haber varios registros de elementos de trabajo y CustomerIncidents para cualquier CustomerName determinado.  

### Crear relaciones cuando los datos tienen valores nulos o en blanco

A menudo los conjuntos de datos contienen columnas con valores nulas o en blanco.  Esto puede causar problemas al intentar usar las relaciones.  Tiene básicamente dos opciones para resolver los problemas.  Puede quitar las filas que tengan valores nulos o en blanco.  Puede hacer esto con una característica de filtro en la pestaña de la consulta o si va a combinar las consultas, seleccione la opción "mantener sólo las filas coincidentes". Como alternativa, puede reemplazar los valores nulos o en blanco con valores que funcionan en las relaciones, normalmente las cadenas como "NULL" y "(" en blanco").   No hay ningún método derecho aquí: filtrado de filas en la consulta fase quita filas y puede afectar a los cálculos y estadísticas de resumen.  El último enfoque conserva que las filas de datos puede pero filas no relacionadas aparecen relacionados en el modelo de cálculos erróneos.  Si adopta la última solución Asegúrese de utilizar filtros en el gráfico de la vista cuando sea necesario para asegurarse de que obtiene resultados precisos.  Lo más importante, evaluar las filas que se mantienen o eliminan y comprender el impacto global sobre el análisis...  

### Crear relaciones cuando los datos tienen valores duplicados

A menudo al cargar conjuntos de datos detallados de varios orígenes, valores de datos duplicados impiden la creación de relaciones.  Para solucionar este problema mediante la creación de una tabla de dimensiones con los valores únicos de ambos conjuntos de datos. 

Veamos un ejemplo: 

Si se cargan los conjuntos de datos de cliente activo de solicitudes de soporte y otro conjunto de datos de elementos de trabajo que tienen esquemas como sigue:
> CustomerInicdents: {IncidentID, CustomerName, IssueName, OpenedDate, estado} elementos de trabajo: {WorkItemID, IncidentID, WorkItemName, OpenedDate, estado, NombreCliente} 

Cuando desea realizar un seguimiento de todos los incidentes y elementos de trabajo relacionados con un CustomerName específico, no podemos crear simplemente una relación entre estos dos conjuntos de datos.  Algunos elementos de trabajo pueden no estar relacionadas con un CustomerName, por lo que sería ese campo en blanco o NULL.  Si tiene los valores en blanco o null en la tabla CustomerNames, aún no puede crear una relación - consulte Creación de relaciones si Mis datos tienen valores nulos o en blanco.  Puede haber varios elementos de trabajo y CustomerIncidents para una sola CustomerName.  

Para crear una relación en este caso, debemos crear un conjunto de datos lógico de todos los CustomerNames en los dos conjuntos de datos.  En la ficha consulta, puede utilizar la siguiente secuencia para crear el conjunto de datos lógico:

1.  Duplicar ambas consultas, la primera de nomenclatura **Temp** y el segundo **CustomerNames**.

2.  En cada consulta, quite todas las columnas *excepto* la columna CustomerName

3.  En cada consulta, use  **Quitar duplicados**.

4.  En el **CustomerNames** consulta, seleccione la **anexado** en la cinta de opciones, seleccione la consulta **Temp**.

5.  En el **CustomerNames** consulta, seleccione **Quitar duplicados**.

Ahora que tiene una tabla de dimensiones que puede utilizar para relacionar CustomerIndicents y elementos de trabajo que contiene todos los valores de cada uno.  

## Patrones para saltar iniciar el uso del Editor de consultas

Editor de consultas es muy eficaz en cómo puede manipular los datos a la forma y limpiar para que esté listo para visualizar o modelar. Existen algunos patrones que deben tenerse en cuenta.

### Se pueden eliminar columnas temporales después de calcular un resultado

A menudo necesitará crear un cálculo que transforma los datos de varias columnas en la nueva columna.  Esto puede ser compleja.  Una forma sencilla de solucionar el problema es hacer descomponer la operación en pasos.  Comience por duplicar las columnas iniciales. Después, compile los pasos en una columna temporal. A continuación, cree el una columna para el resultado final.  A continuación, puede eliminar las columnas temporales para que el conjunto de datos final no esté lleno. Esto es posible porque la ficha consulta ejecuta los pasos en orden. 

### Las consultas de referencia seguidas de mezcla a la consulta original o duplicados

A veces es útil calcular las estadísticas de resumen para un conjunto de datos.  Una manera fácil de hacerlo es duplicar o hacer referencia a la consulta en la ficha consulta. A continuación, utilice **Group by** para calcular las estadísticas de resumen.  Estadísticas de resumen le ayudarán a normalizar los datos en los datos originales para que sean más comparables como en.  Esto es especialmente útil para comparar los valores individuales con el todo.  Para ello, vaya a la consulta original y seleccione la opción de combinación.  A continuación, combinar los datos de la consulta de estadísticas de resumen que coincide con los identificadores adecuados.  Ahora está listo para normalizar los datos según sea necesario para su análisis.

## Usar DAX por primera vez

DAX es el lenguaje de fórmulas de cálculos en Power BI Desktop.  Está optimizado para el análisis de BI.  Es un poco diferente de lo que estará familiarizado con si ha usado solo una instancia de SQL como lenguaje de consulta. Hay muy buenos recursos en línea y en la documentación de aprendizaje de DAX. 

[Inicio rápido: Obtenga información acerca de los conceptos básicos DAX en Power BI Desktop](powerbi-desktop-quickstart-learn-dax-basics.md)

[Referencia DAX (expresiones) de análisis de datos](https://msdn.microsoft.com/library/gg413422.aspx)

[Centro de recursos de DAX](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx)
