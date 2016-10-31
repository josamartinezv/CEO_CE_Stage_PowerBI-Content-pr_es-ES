<properties
   pageTitle="Introducción a Cortana de Power BI"
   description="Usar Cortana con Power BI para obtener respuestas de los datos. Activar Cortana para cada conjunto de datos de Power BI y, a continuación, habilite Cortana tener acceso a los conjuntos de datos desde dispositivos móviles."
   services="powerbi"
   documentationCenter=""
   authors="mihart"  
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
   ms.date="09/19/2016"
   ms.author="mihart"/>


# <a name="introduction-to-cortana-for-power-bi"></a>Introducción a Cortana de Power BI

Formule preguntas en lenguaje natural en Cortana y encuentre respuestas de datos almacenados en Power BI.

>[AZURE.NOTE]  Cortana para Power BI solo está disponible en inglés. Cortana no está actualmente disponible en dispositivos móviles.

## <a name="how-do-cortana-and-power-bi-work-together?"></a>¿Cómo funcionan conjuntamente Cortana y Power BI?

Con la actualización de noviembre de 2015 de Windows 10, Cortana ahora puede encontrar respuestas de datos almacenados en Power BI a través de la integración entre Cortana y Power BI.

Similar a Power BI Q & A formular o escriba sus preguntas con lenguaje natural. Cortana buscará los conjuntos de datos habilitada para Cortana de Power BI respuestas y mostrar los resultados directamente en el dispositivo de Windows 10.   

Cortana puede encontrar respuestas directamente desde los conjuntos de datos en Power BI o de páginas del informe publicado en Power BI y diseñado específicamente para Cortana (llamado *páginas de respuesta*).  Interactuar con las visualizaciones como lo haría en Power BI o, para explorar más de una respuesta, simplemente abra un resultado en Power BI.

>[AZURE.NOTE]  Cortana ahora funciona con datos locales que se ha [habilitado para preguntas y respuestas](powerbi-service-q-and-a-direct-query.md).

Cortana clasifica las respuestas de Power BI, ofrecerle a las mejores coincidencias de uno o más si se produce un resultado es una buena respuesta de alta confianza. Otros posibles respuestas de Power BI se muestran en una sección de Power BI debajo de las mejores coincidencias. Si es propietario de un conjunto de datos, puede ayudar a Cortana devuelven las mejores respuestas de [crear informes especializados (llamado *páginas de respuesta*) de Cortana](powerbi-service-cortana-desktop-entity-cards.md) en Power BI para responder a las preguntas más comunes y optimizar el modelo para Power BI Q & A.

## <a name="how-do-i-get-started?"></a>¿Cómo puedo empezar?

- Cortana busca respuestas en conjuntos de datos de Power BI que tienen acceso a. Si es propietario de un conjunto de datos, [Habilitar Cortana tener acceso el conjunto de datos (y sus informes)](powerbi-service-cortana-enable.md).  

- Si es propietario de un conjunto de datos, [crear páginas de respuesta diseñado específicamente para Cortana](powerbi-service-cortana-desktop-entity-cards.md).

## <a name="tips-for-using-power-bi-with-cortana"></a>Sugerencias para usar Power BI con Cortana

### <a name="before-you-begin"></a>Antes de comenzar

En Power BI, puede trabajar con conjuntos de datos que posee o que se han compartido con usted. Para obtener acceso a los mismos conjuntos de datos en Cortana, el propietario de un conjunto de datos debe [habilitar cada conjunto de datos para Cortana](powerbi-service-cortana-enable.md).  

### <a name="asking-questions"></a>Formular preguntas

Cualquier usuario de Power BI puede usar Cortana para formular preguntas acerca de los conjuntos de datos de Power BI.  Los propietarios del conjunto de datos pueden [mejorar respuestas mediante la creación de páginas de respuesta en Power BI](powerbi-service-cortana-desktop-entity-cards.md).  

1. Con Cortana, pida o escriba una pregunta.  Por ejemplo, pedir "nuevos almacenes de cuántos abierto de marzo?"

2. Cortana busca respuestas en los informes de Power BI y conjuntos de datos disponibles para usted y los muestra en el encabezado **Power BI** y marcados con el icono de Power BI.

3. Power BI primero busca respuestas en [páginas de respuesta](powerbi-service-cortana-desktop-entity-cards.md) y, a continuación, busca en los conjuntos de datos e informes de otras respuestas y los muestra en el formulario de visualizaciones.  Los resultados de puntuación más alta muestran primero como *mejor coincide con*, seguido de vínculos a otras aplicaciones y las respuestas posibles. Informes de Power BI o mejores coincidencias proceden de páginas de respuesta de Power BI.
  >[AZURE.NOTE] Si habla su pregunta, Cortana solo mostrará **Power BI** responde si se encuentra una coincidencia mejor.  

4. Para abrir una respuesta en Power BI, seleccione el vínculo.


### <a name="other-tips"></a>Otras sugerencias

-  Si el informe tiene un filtro, Cortana comprenderá preguntas que especifican los elementos de la lista de filtros y aplican el filtro de forma instantánea.

- Cortana solo busca respuestas en Power BI si la pregunta tiene 2 o más palabras.

- Si agrega la palabra "Mi" a su pregunta, Cortana busca conjuntos de datos disponibles para las respuestas que contienen información que se encuentra en el perfil de Windows 10 (la información que se ve al hacer clic en la imagen).

## <a name="see-also"></a>Consulte también

            [Habilitar Cortana para Power BI](powerbi-service-cortana-enable.md)


            [Introducción a Power BI Q & A](powerbi-service-q-and-a.md)


            [Conceptos básicos de Power BI](powerbi-service-basic-concepts.md)

¿Preguntas más frecuentes? 
            [Pruebe la Comunidad de Power BI](http://community.powerbi.com/)
