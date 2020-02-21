## <a name="product-category-assignments-to-msdyn_productcategoryassignments"></a>Atribuições de categoria de produto para msdyn_productcategoryassignments

Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Common Data Service.

Campo do Finance and Operations | Tipo de mapa | Outro campo Dynamics 365 | Valor padrão
---|---|---|---
PRODUCTNUMBER | = | msdyn_globalproduct.msdyn_productnumber | 
PRODUCTCATEGORYNAME | = | msdyn_productcategory.msdyn_name | 
PRODUCTCATEGORYHIERARCHYNAME | = | msdyn_productcategory.msdyn_hierarchy.msdyn_name | 
PRODUCTNUMBER | >> | msdyn_name | 
