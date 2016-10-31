## Validar la función Power BI Desktop

Después de haber creado el rol, puede probar el resultado de la función en Power BI Desktop. Para ello, seleccione **vista como funciones**.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)
 
El **vista como funciones** cuadro de diálogo permite cambiar la vista de lo que ve para ese rol o usuario específico. Verá los roles que ha creado.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)
 
Seleccione el rol que creó y, a continuación, seleccione **Aceptar** aplicar dicha función a lo que está viendo. Los informes sólo representarán los datos relevantes para ese rol.

También puede seleccionar otro usuario y proporcionar un usuario determinado. Es mejor proporcionar el nombre Principal de usuario (UPN), ya que es lo que va a utilizar el servicio Power BI. Seleccione **Aceptar** y los informes se representarán según lo que puede ver dicho usuario. 

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)
 
> [AZURE.NOTE] En Power BI Desktop, esto sólo mostrará resultados diferentes si usa la seguridad dinámica basándose en sus expresiones de DAX.

