## Definir las funciones y las reglas de Power BI Desktop

Puede definir funciones y reglas de Power BI Desktop. Al publicar en Power BI, publicará también las definiciones de roles.

Si desea aprovechar las ventajas de seguridad dinámica, debe habilitar el modificador de vista previa Habilitar filtrado cruzado en ambas direcciones para DirectQuery. Esto permitirá que la capacidad de cruzar el filtro y aplique el filtro de seguridad en ambas direcciones.

![](./media/rls-desktop-define-roles/powerbi-desktop-preview-bi-directional-directquery.png)

Para definir los roles de seguridad, puede hacer lo siguiente.

1.  Importar datos en su informe de Power BI Desktop o configurar una conexión de DirectQuery.

    > [AZURE.NOTE] No se puede definir funciones en Power BI Desktop para conexiones directas de Analysis Services. Debe hacerlo dentro del modelo de Analysis Services.

2.  Seleccione el **modelado** ficha.

3.  Seleccione **Administrar Roles**.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)

4.  Seleccione **crear**.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)

5.  Escriba un nombre para el rol. 
6.  Seleccione la tabla que desea aplicar una regla DAX.
7.  Escriba las expresiones DAX. Esta expresión debe devolver true o false. Por ejemplo: [Id. de entidad] = "Valor".

    > [AZURE.NOTE] Puede usar *username()* dentro de esta expresión. Tenga en cuenta que *username()* tendrá el formato de *dominio\nombre de usuario* en Power BI Desktop. Dentro del servicio Power BI, estará en el formato de UPN del usuario.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)

8.  Después de haber creado la expresión de DAX, puede seleccionar la comprobación por encima del cuadro de expresión para validar la expresión.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)

9.  Seleccione **Guardar**.

No se puede asignar a usuarios a un rol dentro de Power BI Desktop. Esto se realiza en el servicio Power BI. Puede habilitar la seguridad dinámica en Power BI Desktop haciendo uso de la *username()* funciones de DAX y tener las relaciones correctas configuradas.