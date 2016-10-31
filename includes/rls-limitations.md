## Limitaciones

Aquí es una lista de las limitaciones actuales para la seguridad de nivel de fila en modelos de nube.

- Si anteriormente tenía funciones o las reglas definidas en el servicio Power BI, debe volver a crearlos en Power BI Desktop.
- Puede definir RLS sólo en los conjuntos de datos creados con Power BI Desktop client. Si desea habilitar RLS para conjuntos de datos creados con Excel, debe convertir primero los archivos en archivos PBIX. [Obtener más información](powerbi-desktop-import-excel-workbooks.md)
- Sólo ETL, y se admiten conexiones de DirectQuery. Administra las conexiones en directo a Analysis Services en el modelo en local.
- Preguntas y respuestas y Cortana no es compatible con RLS en este momento. No verá las preguntas y un cuadro de entrada para los paneles si todos los modelos tienen RLS configurado. Se trata de la guía, pero una escala de tiempo no está disponible.
- Actualmente no se admite el uso compartido externo con conjuntos de datos que utilice RLS.

## Problemas conocidos

Hay un problema conocido que recibirá un mensaje de error al intentar publicar desde Power BI Desktop si anteriormente se publicó. El escenario es como sigue.

1. Ana tiene un conjunto de datos publised al servicio Power BI y ha configurado RLS.

2. Ana actualiza el informe en Power BI Desktop y vuelva a publica.

3. Ana producirá un error.


            **Solución alternativa:** volver a publicar el archivo de Power BI Desktop desde el servicio Power BI hasta que se solucione este problema. Para ello, seleccione **obtener datos** > **archivos**. 