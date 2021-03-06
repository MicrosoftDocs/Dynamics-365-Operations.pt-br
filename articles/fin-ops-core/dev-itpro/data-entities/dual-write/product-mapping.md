---
title: Experiência unificada do produto
description: Este tópico descreve a integração de dados do produto entre aplicativos do Finance and Operations e o Dataverse.
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 6941a38e96520befd3bdba65956d45a6bbaee4be
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306380"
---
# <a name="unified-product-experience"></a>Experiência unificada de produto

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Quando um ecossistema comercial é formado por aplicativos do Dynamics 365, como Finance, Supply Chain Management e Sales, muitas vezes as empresas usam esses aplicativos para obter dados do produto. Isso ocorre porque esses aplicativos fornecem uma infraestrutura de produto robusta, complementada por conceitos sofisticados de preços e dados de estoque disponível precisos. As empresas que usam um sistema externo de gerenciamento do ciclo de vida do produto (PLM) para obter dados do produto podem canalizar produtos de aplicativos do Finance and Operations para outros aplicativos do Dynamics 365. A experiência unificada de produto leva o modelo de dados do produto integrado para o Dataverse, para que todos os usuários do aplicativo, inclusive usuários do Power Platform, possam aproveitar os valiosos dados do produto obtidos de aplicativos do Finance and Operations.

Este é o modelo de dados do produto do Sales.

![Modelo de dados de produtos no CE](media/dual-write-product-4.jpg)

Este é o modelo de dados do produto de aplicativos do Finance and Operations.

![Modelo de dados de produtos no Finance and Operations](media/dual-write-products-5.jpg)

Esses dois modelos de dados de produtos foram integrados no Dataverse conforme mostrado a seguir.

![Modelo de dados de produtos em aplicativos do Dynamics 365](media/dual-write-products-6.jpg)

Os mapas de tabelas de gravação dupla de produtos foram desenvolvidos para transmitir dados somente em uma direção, quase que em tempo real, de aplicativos do Finance and Operations para o Dataverse. Entretanto, a infraestrutura do produto foi aberta para torná-la bidirecional, se necessário. Embora você possa personalizá-los, o que é feito por sua conta e risco, a Microsoft não recomenda essa abordagem.

## <a name="templates"></a>Modelos

As informações do produto contêm todos os dados relacionados ao produto e sua definição, como as dimensões do produto ou as dimensões de rastreamento e armazenamento. Como mostrado na tabela a seguir, é criada uma coleção de mapas de tabelas para sincronizar produtos e as informações relacionadas.

Aplicativos Finance and Operations | Outros aplicativos do Dynamics 365 | Descrição
-----------------------|--------------------------------|---
Produtos liberados V2 | msdyn\_sharedproductdetails | A tabela **msdyn\_sharedproductdetails** contém as colunas de aplicativos do Finance and Operations que definem o produto e que contêm as informações de gerenciamento e financeiras dele. 
Produtos distintos liberados pelo Dataverse | Produto | A tabela **Produto** contém as colunas que definem o produto. Ela inclui produtos individuais (produto com o subtipo produto) e as grades de produtos. A tabela a seguir mostra os mapeamentos.
Código de barras identificado pelo número de produto | msdyn\_productbarcodes | Os códigos de barras do produto são usados para identificar produtos de forma exclusiva.
Configurações Padrão da Ordem | msdyn\_productdefaultordersettings
Configurações de ordem padrão específicas ao produto | msdyn_productdefaultordersettings
Grupos de dimensões de produto | msdyn\_productdimensiongroups | O grupo de dimensões do produto definiu quais dimensões do produto definem o produto. 
Grupos de dimensões de armazenamento | msdyn\_productstoragedimensiongroups | O grupo de dimensões de armazenamento do produto representa o método usado para definir o posicionamento do produto no depósito.
Grupos de dimensões de rastreamento | msdyn\_producttrackingdimensiongroups | O grupo de dimensões de rastreamento do produto representa o método usado para controlar o produto no estoque.
Cores | msdyn\_productcolors
Tamanhos | msdyn\_productsizes
Estilos | msdyn\_productsytles
Configurações | msdyn\_productconfigurations
Cores do produto mestre | msdyn_sharedproductcolors | A tabela **Cor do produto compartilhada** indica as cores que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
Tamanhos do produto mestre | msdyn_sharedproductsizes | A tabela **Tamanho do produto compartilhado** indica os tamanhos que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
Estilos do produto mestre | msdyn_sharedproductstyles | A tabela **Estilo do produto compartilhado** indica os estilos que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
Configuração do produto mestre | msdyn_sharedproductconfigurations | A tabela **Configuração do produto compartilhada** indica as configurações que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
Todos os produtos | msdyn_globalproducts | A tabela com todos os produtos contém todos os produtos disponíveis em aplicativos do Finance and Operations, tanto os produtos lançados quanto os produtos não lançados.
Unidade | uoms
Conversões de unidades | msdyn_ unitofmeasureconversions
Conversão de unidades de medida específica ao produto | msdyn_productspecificunitofmeasureconversion
Categorias de produto | msdyn_productcategories | Cada uma das categorias de produtos e as informações sobre sua estrutura e características estão contidas na tabela de categorias de produtos. 
Hierarquias de categorias de produtos | msdyn_productcategoryhierarhies | Use as hierarquias de produtos para categorizar ou agrupar produtos. As hierarquias de categorias estão disponíveis no Dataverse usando a tabela Hierarquia de categorias de produtos. 
Funções de hierarquia de categorias de produtos | msdyn_productcategoryhierarchies | As hierarquias de produtos podem ser usadas em diferentes funções no D365 Finance and Operations. Elas especificam qual categoria é usada em cada função na qual a tabela de funções de categorias de produtos é usada. 
Atribuições de categoria de produtos | msdyn_productcategoryassignments | Para atribuir um produto a uma categoria, é possível usar a tabela de atribuições de categorias de produtos.

## <a name="integration-of-products"></a>Integração de produtos

Neste modelo, o produto é representado pela combinação de duas tabelas do Dataverse: **Produto** e **msdyn\_sharedproductdetails**. Enquanto a primeira tabela contém a definição de um produto (o identificador exclusivo do produto, o nome do produto e a descrição), a segunda contém as colunas armazenadas no nível do produto. A combinação dessas duas tabelas é usada para definir o produto de acordo com o conceito da unidade de manutenção de estoque (SKU). Cada produto lançado terá suas informações nas tabelas mencionadas (Produto e Detalhes Compartilhados do Produto). Para manter o controle de todos os produtos (lançados e não lançados), é usada a tabela **Produtos globais**. 

Como o produto é representados como uma SKU, os conceitos de produtos distintos, produtos mestres e grades de produtos podem ser capturados no Dataverse da seguinte maneira:

- **Produtos com o subtipo produto** são produtos definidos por si só. Não é preciso definir nenhuma dimensão. Um exemplo é um livro específico. Para esses produtos, é criada uma linha na tabela **Produto** e outra linha na tabela **msdyn\_sharedproductdetails**. Não é criada nenhuma linha da família de produtos.
- **Produtos mestres** são usados como produtos genéricos que detêm a definição e as regras que determinam o comportamento em processos comerciais. Com base nessas definições, é possível gerar produtos distintos que são conhecidos como grades de produtos. Por exemplo, Camiseta é o produto mestre, que pode ter as dimensões Cor e Tamanho. Podem ser liberadas variações com diferentes combinações dessas dimensões, como uma camiseta azul pequena ou uma camiseta verde média. Na integração, é criada uma linha por grade na tabela de produtos. Essa linha contém informações específicas da grade, como as diferentes dimensões. As informações genéricas do produto são armazenadas na tabela **msdyn\_sharedproductdetails**. (Estas informações genéricas são mantidas no produto mestre.) As informações do produto mestre são sincronizadas com o Dataverse assim que o produto mestre liberado é criado (mas antes da liberação das variações).
- **Produtos distintos** refere-se a todos os produtos com o subtipo produto e todas as grades de produtos. 

![Modelo de dados de produtos](media/dual-write-product.png)

Com a funcionalidade de gravação dupla habilitada, os produtos do Finance and Operations serão sincronizados em outros produtos do Dynamics 365 no estado **Rascunho**. Eles são adicionados à primeira lista de preços com a mesma moeda. Ou seja, eles são adicionados à primeira lista de preços em um aplicativo do Dynamics 365 que corresponda à moeda da tabela legal em que o produto é lançado em um aplicativo do Finance and Operations. Se não houver uma lista de preços para a moeda especificada, uma lista de preços será criada automaticamente e o produto será atribuído a ela. 

A implementação atual dos plug-ins de gravação dupla que associam a lista de preços padrão à unidade faz a pesquisa da moeda associada ao aplicativo Finance and Operations e localiza a primeira lista de preços no aplicativo de engajamento do cliente, usando classificação alfabética no nome da lista de preços. Para definir uma lista de preços padrão para uma moeda específica na qual você tem várias listas de preços para essa moeda, você deve atualizar o nome da lista de preços para um nome mais antigo em ordem alfabética do que qualquer outra lista de preços para aquela mesma moeda.

Por padrão, os produtos de aplicativos do Finance and Operations são sincronizados com outros aplicativos do Dynamics 365 no estado **Rascunho**. Para sincronizar o produto com estado **Ativo** para poder usá-lo diretamente em cotações de ordens de venda, por exemplo, é necessário escolher a seguinte configuração: **Sistema > Administração > Administração do sistema > Configurações do sistema > guia Vendas** e selecione **Criar produtos em estado ativo = sim**. 

Quando os produtos são sincronizados, você deve inserir um valor para o campo **Unidade de vendas** no aplicativo do Finance and Operations, pois ele é um campo obrigatório no Sales.

A criação de famílias de produtos do Dynamics 365 Sales não é suportada com a sincronização de gravação dupla de produtos.

A sincronização de produtos ocorre no aplicativo do Finance and Operations com o Dataverse. Isso significa que os valores das colunas da tabela de produtos podem ser alterados no Dataverse, mas, quando a sincronização for acionada (quando uma coluna de produto for modificada em um aplicativo do Finance and Operations), isso substituirá os valores no Dataverse. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [products](includes/EcoResReleasedDistinctProductCDSEntity-products.md)]

[!include [product details](includes/EcoResReleasedProductV2-msdyn-sharedproductdetails.md)]

[!include [global products](includes/EcoResEveryProductEntity-msdyn-globalproducts.md)]

## <a name="product-dimensions"></a>Dimensões do produto 

As dimensões do produto são características que identificam uma grade de produto. As quatro dimensões do produto (Cor, Tamanho, Estilo e Configuração) também são mapeadas para o Dataverse para definir as grades de produtos. A ilustração a seguir mostra o modelo de dados para a dimensão do produto Cor. O mesmo modelo é aplicado a Tamanhos, Estilos e Configurações. 

![Modelo de dados para dimensões de produto](media/dual-write-product-two.png)

[!include [product colors](includes/EcoResProductColorEntity-msdyn-productcolor.md)]

[!include [product sizes](includes/EcoResProductSizeEntity-msdyn-productsizes.md)]

[!include [product sizes](includes/EcoResProductStyleEntity-msdyn-productstyles.md)]

[!include [product sizes](includes/EcoResProductConfigurationsEntity-msdyn-productconfigurations.md)]

Quando um produto têm dimensões do produto diferentes (por exemplo, um produto mestre têm Tamanho e Cor como dimensões do produto), cada produto distinto (ou seja, cada grade de produto) é definido como uma combinação dessas dimensões do produto. Por exemplo, o número do produto B0001 é uma camiseta extra pequena, e o número do produto B0002 é uma camiseta preta pequena. Nesse caso, as combinações existentes de dimensões do produto são definidas. Por exemplo, a camiseta do exemplo anterior pode ser extra pequena e preta, pequena e preta, média e preta ou grande e preta, mas não pode ser extra grande e preta. Ou seja, as dimensões do produto que produto mestre pode tomar são especificadas, e é possível liberar variações com base nesses valores.

Para controlar as dimensões do produto que um produto mestre podem tomar, as tabelas a seguir são criadas e mapeadas no Dataverse para cada dimensão do produto. Para obter mais informações, consulte [Visão geral das informações do produto](../../../../supply-chain/pim/product-information.md). 

[!include [product colors](includes/EcoResProductMasterColorEntity-msdyn-sharedproductcolors.md)]

[!include [product sizes](includes/EcoResProductMasterSize-msdyn-sharedproductsizes.md)]

[!include [product styles](includes/EcoResProductMasterStyleEntity-msdyn-sharedproductstyles.md)]

[!include [product configurations](includes/EcoResProductMasterConfigurationEntity-msdyn-sharedproductconfigurations.md)]

[!include [product bar codes](includes/EcoResProductNumberIdentifiedBarcode-msdyn-productbarcodes.md)]

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Configurações de ordem padrão e configurações de ordem padrão específicas ao produto

As configurações de ordem padrão definem o local e o depósito de onde os itens serão originários ou armazenados, as quantidades mínima, máxima, múltiplas e padrão que serão usadas para a comercialização ou o gerenciamento de estoque, os prazos de entrega, o sinalizador de parada e o método de promessa de ordens. Essas informações estão disponíveis no Dataverse usando as configurações de ordem padrão e a entidade de configurações de ordem padrão específica do produto. Você pode ler mais informações sobre a funcionalidade no [tópico Configurações de ordem padrão](../../../../supply-chain/production-control/default-order-settings.md).

[!include [product sizes](includes/InventProductDefaultOrderSettingsEntity-msdyn-productdefaultordersetting.md)]

[!include [product sizes](includes/InventProductSpecificOrderSettingsV2Entity-msdyn-productspecificdefaultordersetting.md)]

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unidade de medida e conversões de unidade de medida

As unidades de medida e sua respectiva conversão estão disponíveis no Dataverse seguindo o modelo de dados exibido no diagrama.

![Modelo de dados para unidade de medida](media/dual-write-product-three.png)

O conceito de unidade de medida é integrado entre os aplicativos do Finance and Operations e outros aplicativos do Dynamics 365. Para cada classe de unidade em um aplicativo do Finance and Operations, é criado um grupo de unidades em um aplicativo do Dynamics 365, que contém as unidades que pertencem à classe de unidade. Uma unidade base padrão também é criada para cada grupo de unidades. 

[!include [unit of measure](includes/UnitOfMeasureEntity-uom.md)]

[!include [unit of measure conversions](includes/UnitOfMeasureConversionEntity-msdyn-unitofmeasureconversions.md)]

[!include [product-specific unit of measure conversions](includes/EcoResProductSpecificUnitConversionEntity-msdyn-productspecificunitofmeasureconversions.md)]

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Sincronização inicial de dados de unidade correspondentes entre o Finance and Operations e o Dataverse

### <a name="initial-synchronization-of-units"></a>Sincronização inicial de unidades

Quando a gravação dupla está habilitada, unidades de aplicativos do Finance and Operations são sincronizadas com outros aplicativos do Dynamics 365. Os grupos de unidades sincronizados de aplicativos do Finance and Operations no Dataverse têm um sinalizador que indica que eles são "Mantidos externamente".

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Unidades compatíveis e classes de unidade/grupos de dados do Finance and Operations e outros aplicativos do Dynamics 365

Primeiramente, é importante observar que a chave de integração para unidade é msdyn_symbol. Portanto, esse valor deve ser exclusivo no Dataverse ou em outros aplicativos do Dynamics 365. Como em outros aplicativos do Dynamics 365 é o par "ID de grupo de unidades" e "Nome" que define a exclusividade de uma unidade, você precisa considerar cenários diferentes para combinar dados de unidades entre aplicativos do Finance and Operations e o Dataverse.

Para unidades correspondentes/sobrepostas em aplicativos do Finance and Operations e em outros aplicativos do Dynamics 365:

+ **A unidade pertence a um grupo de unidades em outros aplicativos do Dynamics 365 que corresponde à classe de unidade associada em aplicativos do Finance and Operations**. Neste caso, a coluna msdyn_symbol em outros aplicativos do Dynamics 365 deve ser preenchida com o símbolo de unidade de aplicativos do Finance and Operations. Portanto, quando os dados forem combinados e o grupo de unidades for definido como "Mantido externamente" em outros aplicativos do Dynamics 365.
+ **A unidade pertence a um grupo de unidades em outros aplicativos do Dynamics 365 que não corresponde à classe de unidade associada em aplicativos do Finance and Operations (nenhuma classe de unidade existente em aplicativos do Finance and Operations para a classe de unidade em outros aplicativos do Dynamics 365).** Nesse caso, msdyn_symbol deve ser preenchido com uma cadeia de caracteres aleatória. Observe que esse valor deve ser exclusivo em outros aplicativos do Dynamics 365.

Para unidades e classes de unidade no Finance and Operations não existentes em outros aplicativos do Dynamics 365:

Como parte da gravação dupla, os grupos de unidades de aplicativos do Finance and Operations e suas unidades correspondentes são criados e sincronizados em outros aplicativos do Dynamics 365 e no Dataverse, e o grupo de unidades será definido como "Mantido externamente". Nenhum trabalho extra de bootstrapping é necessário.

Para unidades em outros aplicativos do Dynamics 365 que não existem em aplicativos do Finance and Operations:

A coluna msdyn_symbol deve ser preenchida para todas as unidades. As unidades sempre podem ser criadas em aplicativos do Finance and Operations na classe de unidade correspondente (se houver). Se a classe de unidade não existe, primeiro ela deve ser criada (não é possível criar uma classe de unidade em aplicativos do Finance and Operations, exceto por meio de extensões, caso você esteja estendendo o enum) correspondendo ao outro grupo de unidades de aplicativos do Dynamics 365. Depois, você poderá criar a unidade. Observe que o símbolo de unidade em aplicativos do Finance and Operations deve ser o msdyn_symbol especificado anteriormente em outros aplicativos do Dynamics 365 para a unidade.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Políticas de produtos: grupos de dimensões, rastreamento e armazenamento

As políticas de produtos são conjuntos de políticas usados para definir produtos e suas características no estoque. O grupo de dimensões do produto, o grupo de dimensões de rastreamento do produto e grupo de dimensões de armazenamento podem ser encontrados com políticas de produtos. 

[!include [product dimension group](includes/EcoResProductDimensionGroup-msdyn-productdimensiongroups.md)]

[!include [product tracking dimension group](includes/EcoResTrackingDimensionGroup-msdyn-producttrackingdimensiongroups.md)]

[!include [product storage dimension group](includes/EcoResStorageDimensionGroup-msdyn-productstoragedimensiongroups.md)]

## <a name="product-hierarchies"></a>Hierarquias de produtos

[!include [product category hierarchy](includes/EcoResProductCategoryHierarchyEntity-msdyn-productcategoryhierarchy.md)]

[!include [product category](includes/EcoResProductCategoryEntity-msdyn-productcategory.md)]

[!include [product category assignments](includes/EcoResProductCategoryAssignmentEntity-msdyn-productcategoryassignment.md)]

[!include [product category role](includes/EcoResProductCategoryHierarchyRoleEntity-msdyn-productcategoryhierarchyrole.md)]


## <a name="integration-key-for-products"></a>Chave de integração para produtos 

Para identificar com exclusividade produtos entre o Dynamics 365 for Finance and Operations e produtos no Dataverse, são utilizadas chaves de integração. Para produtos, **(productnumber)** é a chave exclusiva que identifica um produto no Dataverse. Ela é composta pela concatenação de: **(empresa, msdyn_productnumber)**. A **empresa** indica a entidade legal no Finance and Operations e **msdyn_productnumber** indica o número do produto no caso do produto específico no Finance and Operations. 

Para usuários de outros aplicativos do Dynamics 365, o produto é identificado na interface de usuário com **msdyn_productnumber** (observe que o rótulo da coluna é **Número do produto**). No formulário do produto são mostrados tanto a empresa quanto msydn_productnumber. Entretanto, a coluna (productnumber), a chave exclusiva de um produto, não é exibida. 

Se você criar aplicativos em Dataverse, deverá prestar atenção ao uso do **productnumber** (a ID do produto exclusiva) como a chave de integração. Não use **msdyn_productnumber**, pois ela não é exclusiva. 

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Sincronização inicial de produtos e migração de dados do Dataverse para o Finance and Operations

### <a name="initial-synchronization-of-products"></a>Sincronização inicial de produtos 

Quando a gravação dupla é habilitada, os produtos de aplicativos do Finance and Operations são sincronizados com o Dataverse e aplicativos de participação do cliente. Produtos criados no Dataverse e em outros aplicativos do Dynamics 365 antes da gravação dupla ser lançada não serão atualizados ou combinados com dados de produtos do Finance and Operations apps.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Correspondência de dados de produtos do Finance and Operations e de outros aplicativos do Dynamics 365

Se os mesmos produtos forem mantidos (com sobreposição/correspondência) no Finance and Operations e no Dataverse e em outro aplicativos do Dynamics 365, ao habilitar a gravação dupla, ocorrerá a sincronização de produtos do Finance and Operations e linhas duplicadas do mesmo produto serão exibidas no Dataverse.
Para evitar a situação anterior, se outros aplicativos do Dynamics 365 tiverem produtos com sobreposição/correspondência com o Finance and Operations, o administrador que habilitará a gravação dupla deverá fazer bootstrap das colunas **Empresa** (exemplo: “USMF”) e **msdyn_productnumber** (exemplo: "1234: Black:S") antes da sincronização de produtos. Ou seja, essas duas colunas no produto no Dataverse devem ser preenchidas com a respectiva empresa no Finance and Operations à qual o produto deve corresponder e com o seu número de produto. 

Desse modo, a sincronização é habilitada e acontece, os produtos do Finance and Operations serão sincronizados com os produtos correspondentes no Dataverse e em outros aplicativos do Dynamics 365. Isso é aplicável para produtos distintos e grades de produto. 


### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migração de dados de produtos de outros aplicativos do Dynamics 365 para o Finance and Operations

Se outros aplicativos do Dynamics 365 têm produtos que não estão presentes no Finance and Operations, primeiro o administrador pode usar **EcoResReleasedProductCreationV2Entity** para importar esses produtos no Finance and Operations. Depois, ele pode corresponder os dados de produtos do Finance and Operations e de outros aplicativos do Dynamics 365, conforme descrito acima. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
