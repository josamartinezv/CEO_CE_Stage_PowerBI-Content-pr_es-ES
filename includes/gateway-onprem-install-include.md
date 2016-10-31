## Instale la puerta de enlace de datos local

La puerta de enlace de datos se instala y se ejecuta en el equipo. Es mejor instalar la puerta de enlace en un equipo que puede dejarse en ejecución todo el tiempo.

> [AZURE.NOTE] La puerta de enlace sólo se admite en sistemas operativos de Windows de 64 bits.

Para Power BI, la primera opción que debe realizar es el modo de la puerta de enlace.

-   
            **Puerta de enlace de datos local:** varios usuarios pueden compartir y reutilizar una puerta de enlace en este modo. Esta puerta de enlace puede utilizarse por Power BI, PowerApps, flujo o aplicaciones lógicas. Para Power BI, esto incluye compatibilidad con programación de actualización y DirectQuery

-   
            **Personal:** Esto es sólo para Power BI y puede utilizarse como una persona sin ninguna configuración de administrador. Sólo puede utilizarse para la actualización de programación y de actualización a petición. Se iniciará la instalación de la puerta de enlace personal.

> [AZURE.NOTE] Si instala la puerta de enlace en modo personal, no podrá instalar otra puerta de enlace en el mismo equipo. 

![on-PREM-Data-Gateway-Install-powerbi](./media/gateway-onprem-install-include/on-prem-data-gateway-install-powerbi.png)

Estas son algunas cosas a tener en cuenta antes de instalar la puerta de enlace.

-   Si va a instalar en un equipo portátil y el portátil está apagado, no conectado a internet o suspensión no funcionará la puerta de enlace y los datos en el servicio de nube no se sincronizarán con los datos locales.

-   Si el equipo está conectado a una red inalámbrica, la puerta de enlace puede funcionar más despacio que hará que se tardará más tiempo para sincronizar los datos en el servicio de nube con los datos locales.

Una vez instalada la puerta de enlace, debe iniciar sesión con su cuenta profesional o educativa.

![on-PREM-Data-Gateway-Install-SignIn](./media/gateway-onprem-install-include/on-prem-data-gateway-install-signin.png)

Después de que ha iniciado sesión, tendrá la opción de configurar una puerta de enlace, o migrar, restaurar o asumir una puerta de enlace existente.

![on-PREM-Data-Gateway-Install-Register-Recovery](./media/gateway-onprem-install-include/on-prem-data-gateway-install-register-recovery.png)

## Configurar una puerta de enlace

1.  Escriba un **nombre** la puerta de enlace

2.  Escriba un **clave de recuperación**. Esto tiene que ser un mínimo de 8 caracteres.

3.  Seleccione **configurar**.

> [AZURE.NOTE] Si alguna vez necesita migrar, restaurar o asumir una puerta de enlace, se necesitará la clave de recuperación. Asegúrese de conservar esta clave en un lugar seguro.

![on-PREM-Data-Gateway-Install-Recovery](./media/gateway-onprem-install-include/on-prem-data-gateway-install-recovery.png)

### Migrar, restaurar o asumir una puerta de enlace existente

Debe seleccionar la puerta de enlace que desea recuperar y proporcionar la clave de recuperación que se usó para crear la puerta de enlace. 

### Puerta de enlace de datos local conectado

Una vez configurada la puerta de enlace, podrá hacer uso de ella para conectarse a orígenes de datos locales. 

Si la puerta de enlace es para Power BI, debe agregar los orígenes de datos a la puerta de enlace en el servicio Power BI. Para PowerApps, debe seleccionar una puerta de enlace para una conexión definida para orígenes de datos admitidos.

Lógica de aplicaciones y flujo de esta puerta de enlace está listo para usarse con las conexiones locales 