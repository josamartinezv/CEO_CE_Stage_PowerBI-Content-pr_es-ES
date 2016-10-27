## How the gateway works 

![on-prem-data-gateway-how-it-works](./media/gateway-onprem-how-it-works-include/on-prem-data-gateway-how-it-works.png)

Let’s first look at what happens when a user interacts with an element connected to an on-premises data source. 

> [AZURE.NOTE] For Power BI, you will need to configure a data source for the gateway.

1.  A query will be created by the cloud service, along with the encrypted credentials for the on-premises data source, and sent to the queue for the gateway to process.

2.  The gateway cloud service will analyze the query and will push the request to the <bpt id="p1">[</bpt>Azure Service Bus<ept id="p1">](https://azure.microsoft.com/documentation/services/service-bus/)</ept>.

3.  The on-premises data gateway polls the <bpt id="p1">[</bpt>Azure Service Bus<ept id="p1">](https://azure.microsoft.com/documentation/services/service-bus/)</ept> for pending requests.

4.  The gateway gets the query, decrypts the credentials and connects to the data source(s) with those credentials.

5.  The gateway sends the query to the data source for execution.

6.  The results are sent from the data source, back to the gateway, and then onto the cloud service. The service then uses the results.