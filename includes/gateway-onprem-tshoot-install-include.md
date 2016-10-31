## Actualice a la versión más reciente 
 
Muchos problemas pueden surgir cuando la versión de la puerta de enlace no está actualizada.  Es una buena práctica general para asegurarse de que se encuentra en la versión más reciente.  Si no ha actualizado la puerta de enlace durante un mes o más, puede considerar la instalación de la versión más reciente de la puerta de enlace y vea si puede reproducir el problema.

## Problemas comunes

Estos son algunos problemas comunes y soluciones que le hayan ayudado a un número de clientes en entornos que restringen el acceso a internet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### Autenticación de servidor proxy

El proxy puede rquire autenticación de una cuenta de usuario de dominio. De forma predeterminada, la puerta de enlace utiliza a un SID de servicio para el usuario de inicio de sesión del servicio windows. Cambiar de usuario de inicio de sesión a un usuario de dominio puede ayudarle. Para obtener más información, consulte [cambiar la cuenta de servicio de puerta de enlace a un usuario de dominio](powerbi-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user).

### El proxy sólo permite que los puertos 80 y 443 de tráfico

Algunos servidores proxy restringir el tráfico a sólo los puertos 80 y 443. De forma predeterminada, la comunicación al Bus de servicio de Azure tendrá lugar en puertos distinto de 443. 

Puede forzar la puerta de enlace para comunicarse con el Bus de servicio de Azure usando HTTPS en lugar de TCP directa. Aunque esto reducirá en gran medida el rendimiento. Debe modificar el *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* archivo. Cambie el valor de `AutoDetect` a `Https`. Este archivo se encuentra, de forma predeterminada, en *puerta de enlace de datos local de programa\Archivos C:\Program*.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## Instalación

### Error: No se pudo agregar el usuario al grupo.  (Usuarios del registro de rendimiento de-2147463168 PBIEgwService)

Puede recibir este error si intenta instalar la puerta de enlace en un controlador de dominio. No se admite la implementación de un controlador de dominio. Debe implementar la puerta de enlace en un equipo que no es un controlador de dominio.