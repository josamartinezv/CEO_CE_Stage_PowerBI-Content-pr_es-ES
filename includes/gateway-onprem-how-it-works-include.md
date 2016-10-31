## Cómo funciona la puerta de enlace 

![on-PREM-Data-Gateway-How-IT-Works](./media/gateway-onprem-how-it-works-include/on-prem-data-gateway-how-it-works.png)

Echemos primero un vistazo a lo que sucede cuando un usuario interactúa con un elemento conectado a un origen de datos local. 

> [AZURE.NOTE] Para Power BI, debe configurar un origen de datos para la puerta de enlace.

1.  Una consulta se crea el servicio de nube, junto con las credenciales cifradas para el origen de datos local y se enviará a la cola de la puerta de enlace procesar.

2.  El servicio de puerta de enlace de nube analizará la consulta y envía la solicitud a la [Bus de servicio de Azure](https://azure.microsoft.com/documentation/services/service-bus/).

3.  Los sondeos de puerta de enlace de datos local la [Bus de servicio de Azure](https://azure.microsoft.com/documentation/services/service-bus/) para las solicitudes pendientes.

4.  La puerta de enlace obtiene la consulta, descifra las credenciales y se conecta a los orígenes de datos con esas credenciales.

5.  La puerta de enlace, envía la consulta al origen de datos para su ejecución.

6.  Los resultados se envían desde el origen de datos a la puerta de enlace y, a continuación, en el servicio de nube. El servicio usa los resultados.