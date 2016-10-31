<properties
   pageTitle="Título de la página que se muestra en el explorador ficha y resultados de búsqueda"
   description="Descripción del artículo que se mostrarán en las páginas de inicio y en la mayoría de los resultados de búsqueda"
   services="service-name"
   documentationCenter="dev-center-name"
   authors="GitHub-alias-of-only-one-author"
   manager="manager-alias"
   editor=""/>

<tags
   ms.service="required"
   ms.devlang="may be required"
   ms.topic="article"
   ms.tgt_pltfrm="may be required"
   ms.workload="required"
   ms.date="mm/dd/yyyy"
   ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

# Plantilla de descuento (artículo título 1 o H1): título en la parte superior del artículo

Para copiar el descuento de esta plantilla, copie el artículo en el repositorio local, o haga clic en el botón sin procesar en la UI de GitHub y copie el descuento.

  ![Texto alternativo; No deje en blanco. Describir la imagen.][8]

Párrafo introductorio: Lorem dolor amet, adipiscing elit. Phasellus interdum nulla risus, lacinia PuertoA Suspendisse imperdiet archivo SED. Mauris dolor mauris, tempus sed lacinia nec, euismod no felis. NUNC semper portal ultrices. Maecenas neque nulla, condimentum vitae ipsum sit amet, aliquet dignissim nisi.

## Título 2 (H2)

Aenean sit amet leo nec purus AC fermentum CA gravida odio. Aenean tellus lectus, faucibus en rhoncus en faucibus sed urna.  volutpat mi identificador purus ultrices iaculis nec no neque. 
            [Texto de vínculo fuera de azure.microsoft.com del vínculo](http://weblogs.asp.net/scottgu). Dolor de dictum Nullam a pharetra aliquam. Vivamus CA hendrerit mauris [texto de vínculo de ejemplo de vínculo a un artículo en una carpeta del servicio](../articles/expressroute/expressroute-bandwidth-upgrade.md).

Obtener más de 10 veces el tráfico de [Google] [gog] que desde [Yahoo] [yah] o [MSN] [msn].

> [AZURE.NOTE] Texto con sangría.  La palabra «nota» se agregará durante la publicación. Ut eu pretium lacus. Nullam purus est iaculis sed est ficar, euismod vehicula odio. Curabitur lacinia, erat tristique iaculis rutrum, erat sem sodales nisi, eu condimentum turpis nisi un purus.

1. Aenean sit amet leo nec **Purus** AC fermentum CA gravida odio.

2. Tellus Aenean lectus, faucius en **Rhoncus** en faucibus sed urna. Suspendisse volutpat mi identificador purus ultrices iaculis nec no neque.

    ![Texto alternativo; No deje en blanco. Vehículo de selector en rojo de carreras.][5]

3. Dolor de dictum Nullam a pharetra aliquam. Vivamus CA hendrerit mauris. Dolor sed dui, condimentum et varius un vehicula en Suspendisse.

    ![Texto alternativo; No deje en blanco][6]


Suspendisse volutpat mi identificador purus ultrices iaculis nec no neque. Dolor de dictum Nullam a pharetra aliquam. Vivamus CA hendrerit mauris. Otrus informatus: [vínculo 1 a otro tema de documentación de azure.microsoft.com](virtual-machines-windows-tutorial.md)

## Título (H2)

Ut eu pretium lacus. Nullam purus est iaculis sed est ficar, euismod vehicula odio.

1. Curabitur lacinia, erat tristique iaculis rutrum, erat sem sodales nisi, eu condimentum turpis nisi un purus.

        - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:
        (NSDictionary *)launchOptions
        {
            // Register for remote notifications
            [[UIApplication sharedApplication] registerForRemoteNotificationTypes:
            UIRemoteNotificationTypeAlert | UIRemoteNotificationTypeBadge | UIRemoteNotificationTypeSound];
            return YES;
        }

2. Vestibulum ante ipsum primis en faucibus orci luctus et ultrices posuere cubilia.

        // Because toast alerts don't work when the app is running, the app handles them.
        // This uses the userInfo in the payload to display a UIAlertView.
        - (void)application:(UIApplication *)application didReceiveRemoteNotification:
        (NSDictionary *)userInfo {
            NSLog(@"%@", userInfo);
            UIAlertView *alert = [[UIAlertView alloc] initWithTitle:@"Notification" message:
            [userInfo objectForKey:@"inAppMessage"] delegate:nil cancelButtonTitle:
            @"OK" otherButtonTitles:nil, nil];
            [alert show];
        }


    > [AZURE.NOTE] Duis sed diam no <i>Suspendisse molestie</i> pharetra eget un est. [Vínculo 2 a otro tema de documentación de azure.microsoft.com](web-sites-custom-domain-name.md)


Quisque commodo eros ficar lectus euismod auctor eget sit amet leo. Proin faucibus suscipit tellus dignissim ultrices.

## Título 2 (H2)

1. Sed de Maecenas condimentum nisi. Suspendisse potenti.

  + Fusce
  + Malesuada
  + SEM

2. Nullam en massa eu tellus tempus hendrerit.

    ![Texto alternativo; No deje en blanco. Ejemplo de un vídeo de Channel 9.][7]

3. Felis Quisque enim, fermentum ut aliquam nec, pellentesque pulvinar magna.




<!--Every topic should have next steps and links to the next logical set of content to keep the customer engaged-->
## Pasos siguientes

Vestibul ante ipsum primis en faucibus orci luctus et ultrices posuere cubilia Curae; Nullam ultricies, ipsum vitae volutpat hendrerit, eros de purus diam pretium, vitae tincidunt nulla lorem sed turpis: [vínculo 3 a otro tema de documentación de azure.microsoft.com](storage-whatis-account.md).

<!--Image references-->
[5]: ./media/_markdown-template/octocats.png
[6]: ./media/_markdown-template/pretty49.png
[7]: ./media/_markdown-template/channel-9.png
[8]: ./media/_markdown-template/copytemplate.png

<!--Reference style links - using these makes the source content way more readable than using inline links-->
[gog]: http://google.com/
[yah]: http://search.yahoo.com/
[MSN]: http://search.msn.com/
