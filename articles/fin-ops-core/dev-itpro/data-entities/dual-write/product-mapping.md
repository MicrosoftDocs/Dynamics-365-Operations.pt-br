---
title: Experiência unificada do produto
description: Este artigo descreve a integração de dados do produto entre aplicativos de finanças e operações e o Dataverse.
author: t-benebo
ms.date: 06/23/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 89ef56510ec971ef97fc9eb5c80768527abf5f88
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288912"
---
# <a name="unified-product-experience"></a>Experiência unificada do produto

[!include [banner](../../includes/banner.md)]



Quando um ecossistema comercial é formado por aplicativos do Dynamics 365, como Finance, Supply Chain Management e Sales, muitas vezes as empresas usam esses aplicativos para obter dados do produto. Isso ocorre porque esses aplicativos fornecem uma infraestrutura de produto robusta, complementada por conceitos sofisticados de preços e dados de estoque disponível precisos. As empresas que usam um sistema externo de Gerenciamento do Ciclo de Vida do Produto (PLM) para obter dados do produto podem canalizar produtos de aplicativos de finanças e operações para outros aplicativos do Dynamics 365. A experiência unificada do produto leva o modelo de dados integrado do produto para o Dataverse, para que todos os usuários do aplicativo, inclusive usuários da Power Platform, possam aproveitar os valiosos dados do produto provenientes de aplicativos de finanças e operações.

Este é o modelo de dados do produto do Sales.

![Modelo de dados de produtos no CE.](media/dual-write-product-4.jpg)

Este é o modelo de dados do produto de aplicativos de finanças e operações.

![Modelo de dados de produtos no aplicativo de finanças e operações.](media/dual-write-products-5.jpg)

Esses dois modelos de dados de produtos foram integrados no Dataverse conforme mostrado a seguir.

![Modelo de dados de produtos em aplicativos do Dynamics 365.](media/dual-write-products-6.jpg)

Os mapas de entidade de gravação dupla de produtos foram desenvolvidos para transmitir dados somente em uma direção, quase que em tempo real, de aplicativos de finanças e operações para o Dataverse. Entretanto, a infraestrutura do produto foi aberta para torná-la bidirecional, se necessário. Embora você possa personalizá-los, o que é feito por sua conta e risco, a Microsoft não recomenda essa abordagem.

## <a name="templates"></a>Modelos

As informações do produto contêm todos os dados relacionados ao produto e sua definição, como as dimensões do produto ou as dimensões de rastreamento e armazenamento. Como mostrado na tabela a seguir, é criada uma coleção de mapas de tabelas para sincronizar produtos e as informações relacionadas.

Aplicativos do Finance and Operations | Outros aplicativos do Dynamics 365 | Descrição
-----------------------|--------------------------------|---
[Todos os produtos](mapping-reference.md#138) | msdyn_globalproducts | A tabela de todos os produtos contém todos os produtos disponíveis em aplicativos de finanças e operações, tanto os produtos lançados quanto os produtos não lançados.
[Produtos distintos liberados pelo CDS](mapping-reference.md#213) | Produto | A tabela **Produto** contém as colunas que definem o produto. Ela inclui produtos individuais (produto com o subtipo produto) e as grades de produtos. A tabela a seguir mostra os mapeamentos.
[Cores](mapping-reference.md#170) | msdyn\_productcolors
[Configurações](mapping-reference.md#171) | msdyn\_productconfigurations
[Configurações Padrão da Ordem](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Categorias de produto](mapping-reference.md#166) | msdyn_productcategories | Cada uma das categorias de produtos e as informações sobre sua estrutura e características estão contidas na tabela de categorias de produtos.
[Atribuições de categoria de produtos](mapping-reference.md#167) | msdyn_productcategoryassignments | Para atribuir um produto a uma categoria, é possível usar a tabela de atribuições de categorias de produtos.
[Hierarquias de categorias de produtos](mapping-reference.md#168) | msdyn_productcategoryhierarchies | Use as hierarquias de produtos para categorizar ou agrupar produtos. As hierarquias de categorias estão disponíveis no Dataverse usando a tabela Hierarquia de categorias de produtos.
[Funções de hierarquia de categorias de produtos](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | As hierarquias de produto podem ser usadas para diferentes funções no aplicativo de finanças e operações do D365. Elas especificam qual categoria é usada em cada função na qual a tabela de funções de categorias de produtos é usada.
[Configurações de ordem padrão de produto V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[Grupos de dimensões de produto](mapping-reference.md#173) | msdyn\_productdimensiongroups | O grupo de dimensões do produto definiu quais dimensões do produto definem o produto.
[Cores do produto mestre](mapping-reference.md#187) | msdyn_sharedproductcolors | A tabela **Cor do produto compartilhada** indica as cores que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
[Configuração do produto mestre](mapping-reference.md#188) | msdyn_sharedproductconfigurations | A tabela **Configuração do produto compartilhada** indica as configurações que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
[Tamanhos do produto mestre](mapping-reference.md#190) | msdyn_sharedproductsizes | A tabela **Tamanho do produto compartilhado** indica os tamanhos que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
[Estilos do produto mestre](mapping-reference.md#191) | msdyn_sharedproductstyles | A tabela **Estilo do produto compartilhado** indica os estilos que um determinado produto mestre pode ter. O conceito é migrado para o Dataverse para manter os dados consistentes.
[Código de barras identificado por número de produto](mapping-reference.md#164) | msdyn\_productbarcodes | Os códigos de barras do produto são usados para identificar produtos de forma exclusiva.
[Conversões de unidade específicas do produto](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Produtos liberados V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | A tabela **msdyn\_sharedproductdetails** contém as colunas de aplicativos de finanças e operações que definem o produto e contém as informações de gerenciamento e financeiras do produto.
[Tamanhos](mapping-reference.md#174) | msdyn\_productsizes
[Grupos de dimensões de armazenamento](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | O grupo de dimensões de armazenamento do produto representa o método usado para definir o posicionamento do produto no depósito.
[Estilos](mapping-reference.md#178) | msdyn\_productstyles
[Grupos de dimensões de rastreamento](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | O grupo de dimensões de rastreamento do produto representa o método usado para controlar o produto no estoque.
[Unidades](mapping-reference.md#219) | uoms
[Conversões de unidades](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>Integração de produtos

Neste modelo, o produto é representado pela combinação de duas tabelas do Dataverse: **Produto** e **msdyn\_sharedproductdetails**. Enquanto a primeira tabela contém a definição de um produto (o identificador exclusivo do produto, o nome do produto e a descrição), a segunda contém as colunas armazenadas no nível do produto. A combinação dessas duas tabelas é usada para definir o produto de acordo com o conceito da unidade de manutenção de estoque (SKU). Cada produto lançado terá suas informações nas tabelas mencionadas (Produto e Detalhes Compartilhados do Produto). Para manter o controle de todos os produtos (lançados e não lançados), é usada a tabela **Produtos globais**.

Como o produto é representados como uma SKU, os conceitos de produtos distintos, produtos mestres e grades de produtos podem ser capturados no Dataverse da seguinte maneira:

- **Produtos com o subtipo produto** são produtos definidos por si só. Não é preciso definir nenhuma dimensão. Um exemplo é um livro específico. Para esses produtos, é criada uma linha na tabela **Produto** e outra linha na tabela **msdyn\_sharedproductdetails**. Não é criada nenhuma linha da família de produtos.
- **Produtos mestres** são usados como produtos genéricos que detêm a definição e as regras que determinam o comportamento em processos comerciais. Com base nessas definições, é possível gerar produtos distintos que são conhecidos como grades de produtos. Por exemplo, Camiseta é o produto mestre, que pode ter as dimensões Cor e Tamanho. Podem ser liberadas variações com diferentes combinações dessas dimensões, como uma camiseta azul pequena ou uma camiseta verde média. Na integração, é criada uma linha por grade na tabela de produtos. Essa linha contém informações específicas da grade, como as diferentes dimensões. As informações genéricas do produto são armazenadas na tabela **msdyn\_sharedproductdetails**. (Estas informações genéricas são mantidas no produto mestre.) As informações do produto mestre são sincronizadas com o Dataverse assim que o produto mestre liberado é criado (mas antes da liberação das variações).
- **Produtos distintos** refere-se a todos os produtos com o subtipo produto e todas as grades de produtos.

![Modelo de dados de produtos.](media/dual-write-product.png)

Com a funcionalidade de gravação dupla habilitada, os produtos do aplicativos de finanças e operações serão sincronizados em outros produtos do Dynamics 365 no estado **Rascunho**. Eles são adicionados à primeira lista de preços com a mesma moeda usada no aplicativo de participação do cliente e usando a classificação alfabética no nome da lista de preços. Ou seja, são adicionados à primeira lista de preços em um aplicativo do Dynamics 365 que correlaciona a moeda de sua tabela na qual o produto é liberado em um aplicativo de finanças e operações. Se não houver uma lista de preços para a moeda especificada, uma lista de preços será criada automaticamente e o produto será atribuído a ela.

A implementação atual dos plug-ins de gravação dupla que associam a lista de preços padrão à unidade faz a pesquisa da moeda associada ao aplicativo de finanças e operações e localiza a primeira lista de preços no aplicativo de engajamento do cliente, usando classificação alfabética no nome da lista de preços. Para definir uma lista de preços padrão para uma moeda específica na qual você tem várias listas de preços para essa moeda, você deve atualizar o nome da lista de preços para um nome mais antigo em ordem alfabética do que qualquer outra lista de preços para aquela mesma moeda. Se não houver uma lista de preços para a moeda fornecida, uma nova será criada.

Por padrão, os produtos de aplicativos de finanças e operações são sincronizados com outros aplicativos do Dynamics 365 no estado **Rascunho**. Para sincronizar o produto com estado **Ativo** para poder usá-lo diretamente em cotações de ordens de venda, por exemplo, é necessário escolher a seguinte configuração: **Sistema > Administração > Administração do sistema > Configurações do sistema > guia Vendas** e selecione **Criar produtos em estado ativo = sim**.

Quando os produtos são sincronizados, você deve inserir um valor para o campo **Unidade de vendas** no aplicativo de finanças e operações, pois ele é um campo obrigatório no Sales.

A criação de famílias de produtos do Dynamics 365 Sales não é suportada com a sincronização de gravação dupla de produtos.

A sincronização de produtos acontece a partir de aplicativo de finanças e operações com o Dataverse. Isso significa que os valores das colunas da tabela de produtos podem ser alterados no Dataverse, mas, quando a sincronização for disparada (quando um campo da coluna for modificado em um aplicativo de finanças e operações), os valores serão substituídos no Dataverse.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement |
---|---
[Produtos distintos liberados pelo CDS](mapping-reference.md#213) | Produto |
[Produtos liberados V2](mapping-reference.md#189) | msdyn_sharedproductdetails |
[Todos os produtos](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>Dimensões do produto

As dimensões do produto são características que identificam uma grade de produto. As quatro dimensões do produto (Cor, Tamanho, Estilo e Configuração) também são mapeadas para o Dataverse para definir as grades de produtos. A ilustração a seguir mostra o modelo de dados para a dimensão do produto Cor. O mesmo modelo é aplicado a Tamanhos, Estilos e Configurações.

![Modelo de dados para dimensões de produto.](media/dual-write-product-two.png)

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement |
---|---
[Cores](mapping-reference.md#170) | msdyn\_productcolors
[Tamanhos](mapping-reference.md#174) | msdyn\_productsizes
[Estilos](mapping-reference.md#178) | msdyn\_productstyles
[Configurações](mapping-reference.md#171) | msdyn\_productconfigurations

Quando um produto têm dimensões do produto diferentes (por exemplo, um produto mestre têm Tamanho e Cor como dimensões do produto), cada produto distinto (ou seja, cada grade de produto) é definido como uma combinação dessas dimensões do produto. Por exemplo, o número do produto B0001 é uma camiseta extra pequena, e o número do produto B0002 é uma camiseta preta pequena. Nesse caso, as combinações existentes de dimensões do produto são definidas. Por exemplo, a camiseta do exemplo anterior pode ser extra pequena e preta, pequena e preta, média e preta ou grande e preta, mas não pode ser extra grande e preta. Ou seja, as dimensões do produto que produto mestre pode tomar são especificadas, e é possível liberar variações com base nesses valores.

Para controlar as dimensões do produto que um produto mestre podem tomar, as tabelas a seguir são criadas e mapeadas no Dataverse para cada dimensão do produto. Para obter mais informações, consulte [Visão geral das informações do produto](../../../../supply-chain/pim/product-information.md).

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement |
---|---
[Cores do produto mestre](mapping-reference.md#187) | msdyn_sharedproductcolors |
[Configuração do produto mestre](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[Tamanhos do produto mestre](mapping-reference.md#190) | msdyn_sharedproductsizes |
[Estilos do produto mestre](mapping-reference.md#191) | msdyn_sharedproductstyles |
[Código de barras identificado por número de produto](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Configurações de ordem padrão e configurações de ordem padrão específicas ao produto

As configurações de ordem padrão definem o local e o depósito de onde os itens serão originários ou armazenados, as quantidades mínima, máxima, múltiplas e padrão que serão usadas para a comercialização ou o gerenciamento de estoque, os prazos de entrega, o sinalizador de parada e o método de promessa de ordens. Essas informações estão disponíveis no Dataverse usando as configurações de ordem padrão e a entidade de configurações de ordem padrão específica do produto. Você pode ler mais informações sobre a funcionalidade no [artigo Configurações de ordem padrão](../../../../supply-chain/production-control/default-order-settings.md).

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement |
---|---
[Configurações Padrão da Ordem](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Configurações de ordem padrão de produto V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unidade de medida e conversões de unidade de medida

As unidades de medida e sua respectiva conversão estão disponíveis no Dataverse seguindo o modelo de dados exibido no diagrama.

![Modelo de dados para unidade de medida.](media/dual-write-product-three.png)

O conceito de unidade de medida é integrado entre os aplicativos de finanças e operações e outros aplicativos do Dynamics 365. Para cada classe de unidade em um aplicativo de finanças e operações, é criado um grupo de unidades em um aplicativo do Dynamics 365, que contém as unidades que pertencem à classe de unidade. Uma unidade base padrão também é criada para cada grupo de unidades.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement |
---|---
[Conversões de unidade específicas do produto](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Unidades](mapping-reference.md#219) | uoms
[Conversões de unidades](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Sincronização inicial de dados de unidade correspondentes entre o aplicativo de finanças e operações e o Dataverse

### <a name="initial-synchronization-of-units"></a>Sincronização inicial de unidades

Quando a gravação dupla está habilitada, unidades de aplicativos dos aplicativos de finanças e operações são sincronizadas com outros aplicativos do Dynamics 365. Os grupos de unidades sincronizados de aplicativos de finanças e operações no Dataverse têm um sinalizador que indica que eles são "Mantidos externamente".

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Unidades compatíveis e classes de unidade/grupos de dados do aplicativo de finanças e operações e outros aplicativos do Dynamics 365

Primeiramente, é importante observar que a chave de integração para unidade é msdyn_symbol. Portanto, esse valor deve ser exclusivo no Dataverse ou em outros aplicativos do Dynamics 365. Como em outros aplicativos do Dynamics 365 é o par “ID de grupo de unidades” e “Nome” que define a exclusividade de uma unidade. Você precisa considerar cenários diferentes para combinar dados de unidades entre aplicativos de finanças e operações e o Dataverse.

Para unidades correspondentes/sobrepostas em aplicativos de finanças e operações e em outros aplicativos do Dynamics 365:

+ **A unidade pertence a um grupo de unidades em outros aplicativos do Dynamics 365 que corresponde à classe de unidade associada em aplicativos de finanças e operações**. Nesse caso, a coluna msdyn_symbol em outros aplicativos do Dynamics 365 deve ser preenchida com o símbolo de unidade de aplicativos de finanças e operações. Portanto, quando os dados forem combinados e o grupo de unidades for definido como "Mantido externamente" em outros aplicativos do Dynamics 365.
+ **A unidade pertence a um grupo de unidades em outros aplicativos do Dynamics 365 que não corresponde à classe de unidade associada em aplicativos de finanças e operações (nenhuma classe de unidade existente em aplicativos de finanças e operações para a classe de unidade em outros aplicativos do Dynamics 365).** Nesse caso, msdyn_symbol deve ser preenchido com uma cadeia de caracteres aleatória. Observe que esse valor deve ser exclusivo em outros aplicativos do Dynamics 365.

Para unidades e classes de unidade no aplicativo de finanças e operações não existentes em outros aplicativos do Dynamics 365:

Como parte da gravação dupla, os grupos de unidades de aplicativos de finanças e operações e suas unidades correspondentes são criados e sincronizados em outros aplicativos do Dynamics 365 e no Dataverse, e o grupo de unidades será definido como "Mantido externamente". Nenhum trabalho extra de bootstrapping é necessário.

Para unidades em outros aplicativos do Dynamics 365 que não existem em aplicativos de finanças e operações:

A coluna msdyn_symbol deve ser preenchida para todas as unidades. As unidades sempre podem ser criadas em aplicativos de finanças e operações na classe de unidade correspondente (se houver). Se a classe de unidade não existe, primeiro ela deve ser criada (não é possível criar uma classe de unidade em aplicativos de finanças e operações, exceto por meio de extensões, caso você esteja estendendo a enumeração) correspondendo ao outro grupo de unidades de aplicativos do Dynamics 365. Depois, você poderá criar a unidade. Observe que o símbolo de unidade em aplicativos de finanças e operações deve ser o msdyn_symbol especificado anteriormente em outros aplicativos do Dynamics 365 para a unidade.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Políticas de produtos: grupos de dimensões, rastreamento e armazenamento

As políticas de produtos são conjuntos de políticas usados para definir produtos e suas características no estoque. O grupo de dimensões do produto, o grupo de dimensões de rastreamento do produto e grupo de dimensões de armazenamento podem ser encontrados com políticas de produtos.

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement |
---|---
[Grupos de dimensões de produto](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[Grupos de dimensões de armazenamento](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[Grupos de dimensões de rastreamento](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>Hierarquias de produtos

Aplicativos do Finance and Operations | Aplicativos do Customer Engagement |
---|---
[Atribuições de categoria de produtos](mapping-reference.md#167) | msdyn_productcategoryassignments |
[Hierarquias de categorias de produtos](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[Funções de hierarquia de categorias de produtos](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>Chave de integração para produtos

Para identificar com exclusividade produtos entre o Dynamics 365 Finance e produtos no Dataverse, são utilizadas chaves de integração.
Para produtos, **(productnumber)** é a chave exclusiva que identifica um produto no Dataverse. Ela é composta pela concatenação de: **(empresa, msdyn_productnumber)**. A **empresa** indica a entidade legal no aplicativo de finanças e operações e **msdyn_productnumber** indica o número do produto no caso do produto específico no aplicativo de finanças e operações.

Para usuários de outros aplicativos do Dynamics 365, o produto é identificado na interface de usuário com **msdyn_productnumber** (observe que o rótulo da coluna é **Número do produto**). No formulário do produto são mostrados tanto a empresa quanto msydn_productnumber. Entretanto, a coluna (productnumber), a chave exclusiva de um produto, não é exibida.

Se você criar aplicativos em Dataverse, deverá prestar atenção ao uso do **productnumber** (a ID do produto exclusiva) como a chave de integração. Não use **msdyn_productnumber**, pois ela não é exclusiva.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Sincronização inicial de produtos e migração de dados do Dataverse para o aplicativo de finanças e operações

### <a name="initial-synchronization-of-products"></a>Sincronização inicial de produtos

Quando a gravação dupla é habilitada, os produtos dos aplicativos de finanças e operações são sincronizados com o Dataverse e aplicativos de engajamento do cliente. Os produtos criados no Dataverse e em outros aplicativos do Dynamics 365 antes da gravação dupla ser liberada não serão atualizados ou combinados com dados de produtos dos aplicativos de finanças e operações.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Correspondência de dados de produtos do aplicativo de finanças e operações e de outros aplicativos do Dynamics 365

Se os mesmos produtos forem mantidos (sobreposição/correspondência) em aplicativos de finanças e operações e no Dataverse e em outro aplicativos do Dynamics 365, ao habilitar a gravação dupla, ocorrerá a sincronização de produtos de finanças e operações e linhas duplicadas do mesmo produto serão exibidas no Dataverse.
Para evitar a situação anterior, se outros aplicativos do Dynamics 365 tiverem produtos que se sobrepõem/correspondem a finanças e operações, quando o administrador habilitar a gravação dupla deverá ocorrer bootstrap das colunas **Empresa** (exemplo: “USMF”) e **msdyn_productnumber** (exemplo: “1234: Black:S”) antes da sincronização de produtos. Ou seja, essas duas colunas no produto no Dataverse devem ser preenchidas com a respectiva empresa em finanças e operações à qual o produto deve corresponder e com o seu número de produto.

Desse modo, a sincronização é habilitada e acontece, os produtos do aplicativo de finanças e operações serão sincronizados com os produtos correspondentes no Dataverse e em outros aplicativos do Dynamics 365. Isso é aplicável para produtos distintos e grades de produto.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migração de dados de produtos de outros aplicativos do Dynamics 365 para o aplicativo de finanças e operações

Se outros aplicativos do Dynamics 365 tiverem produtos que não estão presentes no aplicativo de finanças e operações, primeiro o administrador pode usar **EcoResReleasedProductCreationV2Entity** para importar esses produtos no aplicativo de finanças e operações. Depois, ele pode corresponder os dados de produtos do aplicativo de finanças e operações e de outros aplicativos do Dynamics 365, conforme descrito acima.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

