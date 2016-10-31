## Firewall o Proxy

Para obtener información acerca de proporcionar información de proxy de la puerta de enlace, vea [configuración de proxy para las puertas de enlace de Power BI](powerbi-gateway-proxy.md).

Puede probar para ver si el firewall o proxy, puede estar bloqueando hay conexión ejecutando el comando siguiente desde un símbolo del sistema de PowerShell. Esto probará la conectividad con el Bus de servicio de Azure. Esto sólo prueba la conectividad de red y no tiene nada que ver con el servicio de servidor de nube o la puerta de enlace. Ayuda a determinar si el equipo puede obtener realmente a internet.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

El resultado debería ser similar al siguiente. La diferencia será con TcpTestSucceeded. Si **TcpTestSucceeded** no *true*, a continuación, puede estar bloqueado por un firewall.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Si desea ser exhaustiva, sustituya la **nombreDeEquipo** y **puerto** valores con los que se enumeran para [puertos](powerbi-gateway-onprem.md#ports)

El firewall también puede estar bloqueando las conexiones que hace que el Bus de servicio de Azure a los centros de datos de Azure. Si ese es el caso, le interesará a la lista blanca (desbloquear) las direcciones IP de su región para esos centros de datos. Puede obtener una lista de direcciones IP de Azure [aquí](https://www.microsoft.com/download/details.aspx?id=41653).