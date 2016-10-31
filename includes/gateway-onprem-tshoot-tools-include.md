## Herramientas para la solución de problemas

<a name="logs" />
### Recopilación de registros desde el Configurador de puerta de enlace

Hay varios registros, puede recopilar la puerta de enlace. Iniciar siempre con los registros.

**Registros de instalador**

    %localappdata%\Temp\On-premises_data_gateway_*.log

**Registros de configuración**

    %localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log

**Registros del servicio de puerta de enlace de datos local**

    C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log

### Registros de eventos  
El **servicio de puerta de enlace de datos local** registros de eventos están presentes en **registros de aplicaciones y servicios**.

![on-PREM-Data-Gateway-Event-Logs](./media/gateway-onprem-tshoot-tools-include/on-prem-data-gateway-event-logs.png)

<a name="fiddler" />
### Seguimiento de Fiddler  

            [Fiddler](http://www.telerik.com/fiddler) es una herramienta gratuita de Telerik que supervisa el tráfico HTTP.  Puede ver la parte posterior y hacia delante con Power BI de servicio desde el equipo cliente. Esto puede mostrar errores y otra información relacionada.

![](media/gateway-onprem-tshoot-tools-include/fiddler.png)