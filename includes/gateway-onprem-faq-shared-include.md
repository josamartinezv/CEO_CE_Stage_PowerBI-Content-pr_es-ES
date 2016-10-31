## General


            **Pregunta:** lo que se denomina el servicio de Windows real?  

            **Respuesta:** la puerta de enlace se denomina servicio de puerta de enlace de datos local de servicios


            **Pregunta:** Cuáles son los requisitos para la puerta de enlace?  

            **Respuesta:** Eche un vistazo a la sección de requisitos de los principales [artículo de puerta de enlace](powerbi-gateway-onprem.md).


            **Pregunta:** qué orígenes de datos son compatibles con la puerta de enlace?  

            **Respuesta:** vea la tabla de orígenes de datos en la ventana principal [artículo de puerta de enlace](powerbi-gateway-onprem.md).


            **Pregunta:** es necesario una puerta de enlace para los orígenes de datos de nube como base de datos de SQL Azure?  

            **Respuesta:** n! El servicio podrá conectarse a ese origen de datos sin una puerta de enlace.


            **Pregunta:** hay cualquier conexión entrante a la puerta de enlace de la nube?  

            **Respuesta:** no. La puerta de enlace usa conexiones de salida al Bus de servicio de Azure.


            **Pregunta:** ¿Qué ocurre si bloquear conexiones salientes? ¿Qué es necesario abrir?  

            **Respuesta:** consulte la [lista de puertos](powerbi-gateway-onprem.md#ports) y los hosts que utiliza la puerta de enlace.


            **Pregunta:** la puerta de enlace debe estar instalados en el mismo equipo que el origen de datos?  

            **Respuesta:** no. Se conectará la puerta de enlace al origen de datos con la información de conexión que se proporcionó. Considere la puerta de enlace como una aplicación de cliente en este sentido. Solo tendrá que ser capaz de conectar con el nombre del servidor que se proporcionó.


            **Pregunta:** ¿Qué es la latencia para ejecutar consultas para un origen de datos de la puerta de enlace? ¿Cuál es la mejor arquitectura?  

            **Respuesta:** se recomienda que la puerta de enlace como cerca del origen de datos como sea posible para evitar la latencia de red. Si se puede instalar la puerta de enlace en el origen de datos real, minimizará la latencia que presenta. Considere la posibilidad de centros de datos. Por ejemplo, si el servicio usa del Oeste NOS centro de datos y tener SQL Server hospedado en una máquina Virtual de Azure, deseará tener también de la máquina Virtual de Azure en el oeste de Estados Unidos. Esto minimizará la latencia y evitar los cargos de salida en la máquina Virtual de Azure.


            **Pregunta:** ¿existen requisitos de ancho de banda de red?  

            **Respuesta:** se recomienda tener un buen rendimiento para la conexión de red. Cada entorno es diferente y también esto depende de la cantidad de datos que se envían. Usar ExpressRoute puede ayudar a garantizar un nivel de rendimiento entre local y los centros de datos de Azure.

Puede utilizar la parte 3ª [aplicación de prueba de velocidad de Azure](http://azurespeedtest.azurewebsites.net/) para evaluar qué es el rendimiento. 


            **Pregunta:** puede ejecutar la puerta de enlace de servicio de Windows con una cuenta de Azure Active Directory?  

            **Respuesta:** no. El servicio de Windows debe tener una cuenta de Windows válida. De forma predeterminada, se ejecutará con el SID de servicio *SERVICE\PBIEgwService NT*.


            **Pregunta:** cómo se envían resultados a la nube?  

            **Respuesta:** Esto se consigue mediante el Bus de servicio de Azure. Para obtener más información, vea [cómo funciona](powerbi-gateway-onprem.md#how-the-gateway-works).


            **Pregunta:** donde se almacenan las credenciales?  

            **Respuesta:** las credenciales que especifique para un origen de datos se almacenan cifradas en el servicio de nube de puerta de enlace. Las credenciales se descifran en la puerta de enlace local.


            **Pregunta:** puedo colocar la puerta de enlace en una red perimetral (también conocida como DMZ, zona desmilitarizada y subred filtrada)?  

            **Respuesta:** la puerta de enlace requiere conectividad con el origen de datos. Si el origen de datos no es accesible en la red perimetral, es posible que la puerta de enlace no pueda conectarse a ella. Por ejemplo, SQL Server no estén en la red perimetral. Y no se puede conectar a SQL Server desde la red perimetral. Si coloca la puerta de enlace de la red perimetral, no sería capaz de ponerse en contacto con el servidor SQL Server.


            **Pregunta:** es posible forzar la puerta de enlace para usar tráfico HTTPS con el Bus de servicio de Azure en lugar de TCP?  

            **Respuesta:** Sí. Aunque esto reducirá en gran medida el rendimiento. Va a modificar el *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* archivo. Desea cambiar el valor de `AutoDetect` a `Https`. Este archivo se encuentra, de forma predeterminada, en *puerta de enlace de datos local de programa\Archivos C:\Program*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## Alta disponibilidad/recuperación ante desastres


            **Pregunta:** ¿existen planes para habilitar escenarios de alta disponibilidad con la puerta de enlace?  

            **Respuesta:** Sí. Se trata de la guía, pero aún no tenemos una escala de tiempo.


            **Pregunta:** qué opciones están disponibles para recuperación ante desastres?  

            **Respuesta:** puede usar la clave de recuperación para restaurar o mover una puerta de enlace. Al instalar la puerta de enlace, proporcione la clave de recuperación.


            **Pregunta:** Cuál es el beneficio de la clave de recuperación?  

            **Respuesta:** proporciona una manera de migrar o recuperar la configuración de puerta de enlace. También se utiliza para la recuperación ante desastres.

## Solucionar problemas


            **Pregunta:** donde están ubicados los registros de puerta de enlace?  

            **Respuesta:** consulte la sección de herramientas de la [artículo de solución de problemas](powerbi-gateway-onprem-tshoot.md#tools).


            **Pregunta:** ¿cómo se puede ver lo que las consultas que se envían al origen de datos local?  

            **Respuesta:** puede habilitar el seguimiento de la consulta.  Esto incluye las consultas que se envían. No olvide cambiar el valor original cuando finalizado la solución de problemas. Tener habilitado el seguimiento de consulta hará que los registros sean mayores.

También puede mirar herramientas que tiene su origen de datos para las consultas de seguimiento. Por ejemplo, para SQL Server y Analysis Services puede utilizar eventos extendidos o el analizador de SQL.