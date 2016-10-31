## Inicie sesión en la cuenta

Los usuarios iniciar sesión con un trabajo o escuela cuenta. Se trata de la cuenta de la organización. Si registró para una oferta de Office 365 y no ha proporcionado el correo electrónico de trabajo real, podría parecer nancy@contoso.onmicrosoft.com. La cuenta en un servicio de nube, se almacena en un inquilino de Azure Active Directory (AAD). En la mayoría de los casos, los UPN de la cuenta AAD coincidirá con la dirección de correo electrónico.

## Cuenta de servicio de Windows

La puerta de enlace de datos local está configurado para usar *SERVICE\PBIEgwService NT* para las credenciales de inicio de sesión de servicio de windows. De forma predeterminada, tiene el derecho de registro como un servicio. Se trata en el contexto de la máquina que va a instalar la puerta de enlace. 

> [AZURE.NOTE]  Si ha seleccionado el modo personal, configurar la cuenta de servicio de windows por separado.

No es la cuenta usada para conectarse a orígenes de datos locales.  Tampoco es su trabajo o servicios de cuenta organizativa que inicie sesión en la nube con.

Si tiene problemas con el servidor proxy, debido a la autenticación, puede cambiar la cuenta de servicio de Windows a un usuario de dominio o cuenta de servicio administrada. Puede aprender a cambiar la cuenta en [configuración proxy](powerbi-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

## Puertos

La puerta de enlace crea una conexión de salida al Bus de servicio de Azure. Se comunica en puertos de salida: TCP 443 (valor predeterminado), 5671, 5672, 9350 a 9354.  La puerta de enlace no requiere los puertos de entrada. [Obtener más información](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/)

Se recomienda que lista blanca, las direcciones IP, de la región de datos en el servidor de seguridad. Puede descargar el [lista de direcciones IP del centro de datos de Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653). Esta lista se actualiza semanalmente. 

> [AZURE.NOTE]  Son las direcciones IP mostradas en la lista de direcciones IP del centro de datos de Azure en la notación CIDR. Por ejemplo, 10.0.0.0/24 no significa 10.0.0.0 a través de 10.0.0.24. Obtenga más información sobre la [la notación CIDR](http://whatismyipaddress.com/cidr).

Aquí se muestra una lista de los nombres de dominio completo utilizada la puerta de enlace.

|Nombres de dominio|Puertos de salida|Descripción|
|---|---|---|
|*. powerbi.com|80|HTTP que se utiliza para descargar al instalador.|
|*. powerbi.com|443|HTTPS|
|*. analysis.windows.net|443|HTTPS|
|*. login.windows.net|443|HTTPS|
|*.servicebus.windows.net|5671-5672|Avanzadas Message Queuing Protocol (AMQP)|
|*.servicebus.windows.net|443, 9350-9354|Agentes de escucha de retransmisión de Bus de servicio sobre TCP (requiere 443 para la adquisición del token de Control de acceso)|
|*. frontend.clouddatahub.net|443|HTTPS|
|*. core.windows.net|443|HTTPS|
|Login.microsoftonline.com|443|HTTPS|
|*. msftncsi.com|443|Se utiliza para probar la conectividad a internet si la puerta de enlace no está accesible para el servicio Power BI.|
|*.microsoftonline-p.com|443|Se utiliza para la autenticación dependiendo de la configuración.|

> [AZURE.NOTE] El tráfico que va a visualstudio.com o visualstudioonline.com de detalles de la aplicación y no es necesario para la puerta de enlace de función.

### Forzar la comunicación HTTPS con el Bus de servicio de Azure

Puede forzar la puerta de enlace para comunicarse con el Bus de servicio de Azure usando HTTPS en lugar de TCP directa. Aunque esto reducirá en gran medida el rendimiento. Debe modificar el *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* archivo. Cambie el valor de `AutoDetect` a `Https`. Este archivo se encuentra, de forma predeterminada, en *puerta de enlace de datos local de programa\Archivos C:\Program*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## ante desastres

Opciones de alta disponibilidad se encuentran en el plan para la puerta de enlace. Permanezca atento para más actualizaciones.

## Cómo reiniciar la puerta de enlace

La puerta de enlace se ejecuta como un servicio de windows. Puede iniciar y detener como cualquier servicio de windows. Hay varias maneras de hacerlo. Aquí es cómo puede hacerlo desde el símbolo del sistema.

1.  En el equipo donde se ejecuta la puerta de enlace, inicie un símbolo del sistema de administración.

2.  Utilice el siguiente comando para detener el servicio.

    net stop PBIEgwService 

3.  Utilice el siguiente comando para iniciar el servicio.

    Net start PBIEgwService