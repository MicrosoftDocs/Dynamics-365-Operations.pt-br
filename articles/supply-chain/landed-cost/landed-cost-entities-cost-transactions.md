---
title: Entidades de transação de custo
description: Este tópico fornece informações sobre entidades de transação de custo, que permitem que o valor de um custo seja dividido entre o conteúdo de uma área de custo por meio da seleção de um método de divisão.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 41a9525cb766907b7de97f1e856a3b640d7718ac
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813031"
---
# <a name="cost-transaction-entities"></a>Entidades de transação de custo

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

## <a name="apportionment"></a>Divisão proporcional

O custo de entrega permite a divisão do valor de um custo entre o conteúdo de uma área de custo (viagens, contêiner de remessa etc.) por meio da seleção de um método de divisão. O método de divisão é definido como parte da configuração de custos automáticos que se baseiam em regras comerciais. Ele é obtido como parte do custo quando uma linha de viagem é criada.

### <a name="configure-the-apportionment-mapping-for-use-with-data-entities"></a>Configurar o mapeamento de divisão para uso com entidades de dados

Quando um custo é criado a partir de uma fonte externa, como um controlador de frete, a origem externa não pode especificar o método preferencial para dividir o valor de custo. O mapeamento de divisão define o método de divisão padrão para cada código de tipo de custo. A tabela de mapeamentos de divisão é acessada na página **Mapeamento de divisão** no Microsoft Dynamics 365 Supply Chain Management (**Custo de Entrega \> Configuração de custos \> Mapeamento de divisão**).

Se uma combinação de mapeamento tiver sido definida e um custo que corresponda ao código de tipo de custo for criado usando uma entidade de transação de custo, o método de divisão mapeado será usado em vez de um valor fornecido à entidade.

Se nenhum valor estiver presente na tabela de mapeamento, mas um valor tiver sido fornecido para a entidade, o valor fornecido será usado.

Se nenhum valor existir na tabela de mapeamento ou no registro enviado à entidade, a criação falhará.

### <a name="apportionment-mapping-itmapportionmentmapping"></a>Mapeamento de divisão (ITMApportionmentMapping)

A entidade de mapeamento de divisão (`ITMApportionmentMapping`) cria relações de mapeamento de divisão e permite que usuários criem ou atualizem registros.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Método de divisão proporcional | ITMApportionmentMapping.ApportionmentMethod | Int | Número | Número |
| Código de tipo de custo | ITMApportionmentMapping.ShipCostTypeId | Nvarchar(20) | **Sim** | Número |

## <a name="voyage-costs-itmcosttransvoyageentity"></a>Custos de viagem (ITMCostTransVoyageEntity)

A entidade de custo de viagem (`ITMCostTransVoyageEntity`) cria transações de custo de viagem que são aplicadas no nível de viagem. Durante o processo de importação, o sistema usa os valores **Categoria** e **Método de divisão** incluídos na entidade para determinar como o valor do custo é dividido por todo o conteúdo da viagem.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Método de divisão proporcional | ITMCostTrans.ApportionmentMethod | Int | Número | Número |
| Valor de custo | ITMCostTrans.CostValue | Numeric(32, 6) | Número | Número |
| Moeda | ITMCostTrans.CurrencyCode | Nvarchar(3) | Número | **Sim** |
| Número da linha | ITMCostTrans.LineNum | Numeric(32, 16) | **Sim** | Número |
| Tipo de custo vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Número | Número |
| Custo mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Número | Número |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Número | Número |
| Código de tipo de custo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Número | Número |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | Número | **Sim** |
| Viagem | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Grupo de impostos do item | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Número | Número |

## <a name="shipping-container-costs-itmcosttransshippingcontainerentity"></a>Custos do contêiner de remessa (ITMCostTransShippingContainerEntity)

A entidade de custo do contêiner de remessa (`ITMCostTransShippingContainerEntity`) cria custos do contêiner de remessa que são aplicados no nível do contêiner de remessa. Durante o processo de importação, o sistema usa os valores **Categoria** e **Método de divisão** incluídos na entidade para determinar como o valor do custo é dividido por todo o conteúdo do contêiner de remessa.

Os campos **Agregação**, **Trecho** e **Trecho vinculado** são específicos de registros nos quais o valor **Área de custo** é *Contêiner de remessa*. Portanto, eles não estão presentes em entidades de dados para outras áreas de custo.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Agregação | ITMCostTrans.AggregatedCost | Int | Número | Número |
| Método de divisão proporcional | ITMCostTrans.ApportionmentMethod | Int | Número | Número |
| Valor de custo | ITMCostTrans.CostValue | Numeric(32, 6) | Número | Número |
| Moeda | ITMCostTrans.CurrencyCode | Nvarchar(3) | Número | **Sim** |
| Número da linha | ITMCostTrans.LineNum | Numeric(32, 16) | **Sim** | Número |
| Tipo de custo vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Número | Número |
| Itinerário vinculado | ITMCostTrans.LinkLegId | Nvarchar(20) | Número | Número |
| Custo mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Número | Número |
| Contêiner de remessa | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Número | Número |
| Código de tipo de custo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Número | Número |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | Número | **Sim** |
| Viagem | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Trecho | ITMCostTrans.ShipLegId | Nvarchar(20) | Número | Número |
| Grupo de impostos do item | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Número | Número |

## <a name="folio-costs-itmcosttransfolioentity"></a>Custos de fólio (ITMCostTransFolioEntity)

A entidade de custo de fólio (`ITMCostTransFolioEntity`) cria registros de transações de custo que se aplicam ao nível de fólio. Durante o processo de importação, o sistema usa os valores **Categoria** e **Método de divisão** incluídos na entidade para determinar como o valor do custo é dividido pelo conteúdo de cada fólio.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Método de divisão proporcional | ITMCostTrans.ApportionmentMethod | Int | Número | Número |
| Valor de custo | ITMCostTrans.CostValue | Numeric(32, 6) | Número | Número |
| Moeda | ITMCostTrans.CurrencyCode | Nvarchar(3) | Número | **Sim** |
| Número da linha | ITMCostTrans.LineNum | Numeric(32, 16) | **Sim** | Número |
| Tipo de custo vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Número | Número |
| Custo mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Número | Número |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Número | Número |
| Código de tipo de custo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Número | Número |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | Número | **Sim** |
| Fólio | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Grupo de impostos do item | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Número | Número |

## <a name="purchase-order-costs-itmcosttranspurchaseentity"></a>Custos da ordem de compra (ITMCostTransPurchaseEntity)

A entidade de custo da ordem de compra (`ITMCostTransPurchaseEntity`) cria transações de custo que se aplicam ao cabeçalho da ordem de compra. Durante o processo de importação, o sistema usa os valores **Categoria** e **Método de divisão** incluídos na entidade para determinar como o valor do custo é dividido pelo conteúdo de cada fólio.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Método de divisão proporcional | ITMCostTrans.ApportionmentMethod | Int | Número | Número |
| Valor de custo | ITMCostTrans.CostValue | Numeric(32, 6) | Número | Número |
| Moeda | ITMCostTrans.CurrencyCode | Nvarchar(3) | Número | **Sim** |
| Número da linha | ITMCostTrans.LineNum | Numeric(32, 16) | **Sim** | Número |
| Tipo de custo vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Número | Número |
| Custo mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Número | Número |
| Ordem de compra | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Número | Número |
| Código de tipo de custo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Número | Número |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | Número | **Sim** |
| Grupo de impostos do item | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Número | Número |

## <a name="item-costs-itmcosttransitementity"></a>Custos de item (ITMCostTransItemEntity)

A entidade de custo de item (`ITMCostTransItemEntity`) cria transações de custo que se aplicam ao nível de item. Esta entidade é específica para itens em linhas de ordem de compra. O valor do custo é aplicado totalmente à linha.

Os campos **Valor do ajuste** e **Ajuste de valor** são específicos das áreas de custo do nível de linha. Portanto, eles não estão presentes em entidades de dados para outras áreas de custo.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor do ajuste | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | Número | Número |
| Valor de custo | ITMCostTrans.CostValue | Numeric(32, 6) | Número | Número |
| Moeda | ITMCostTrans.CurrencyCode | Nvarchar(3) | Número | **Sim** |
| Número da linha | ITMCostTrans.LineNum | Numeric(32, 16) | **Sim** | Número |
| Tipo de custo vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Número | Número |
| Custo mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Número | Número |
| Ordem de compra | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Número da linha da ordem de compra | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Número | Número |
| Código de tipo de custo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Número | Número |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | Número | **Sim** |
| Grupo de impostos do item | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Número | Número |
| Ajuste de valor | ITMCostTrans.ValueAdjustmentMethod | Int | Número | Número |

## <a name="transfer-line-costs-itmcosttranstransferlineentity"></a>Transferir custos de linha (ITMCostTransTransferLineEntity)

A entidade de custo linha de transferência (`ITMCostTransTransferLineEntity`) cria transações de custo que se aplicam ao nível da linha da ordem de transferência. O valor destes custos é aplicado totalmente à linha da ordem de transferência.

Os campos **Valor do ajuste** e **Ajuste de valor** são específicos das áreas de custo do nível de linha. Portanto, eles não estão presentes em entidades de dados para outras áreas de custo.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor do ajuste | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | Número | Número |
| Valor de custo | ITMCostTrans.CostValue | Numeric(32, 6) | Número | Número |
| Moeda | ITMCostTrans.CurrencyCode | Nvarchar(3) | Número | **Sim** |
| Número da linha | ITMCostTrans.LineNum | Numeric(32, 16) | **Sim** | Número |
| Tipo de custo vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | Número | Número |
| Custo mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | Número | Número |
| Categoria | ITMCostTrans.ShipCostCategory | Int | Número | Número |
| Código de tipo de custo | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | Número | Número |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | Número | **Sim** |
| Ordem de transferência | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Número da linha do pedido de transferência | ITMCostTrans.TransRecId | Nvarchar(20) | **Sim** | Número |
| Grupo de impostos do item | ITMCostTrans.TaxItemGroup | Nvarchar(10) | Número | Número |
| Ajuste de valor | ITMCostTrans.ValueAdjustmentMethod | Int | Número | Número |

### <a name="transaction-table"></a>Tabela de transações

Um registro de transação de custo é associado a uma área de custo por meio da atribuição de um número de tabela de transação (`TransTableId`). Quando são necessários números de identificação de tabela específicos, as entidades são divididas com base nesses valores, de forma que exista uma entidade para cada área de custo.

O valor da tabela de transações (`TransTableId`) é implícito na seleção da entidade da transação de custo.

### <a name="calculated-fields"></a>Campos calculados

Os seguintes campos não estão disponíveis para inserção ou atualização quando uma entidade de transação de custo é usada, porque esses campos são definidos somente quando as ações específicas são executadas em relação ao registro da viagem:

- **Custo estimado** – este campo é definido quando uma fatura é lançada para a viagem (ordem de compra) ou uma transferência é recebida.
- **Moeda de custo estimado** – este campo é definido quando uma fatura é lançada para a viagem (ordem de compra) ou uma transferência é recebida.
- **Custo real** – este campo é definido quando uma fatura de fornecedor é lançada. Ele está associado ao custo.

### <a name="find-auto-costs"></a>Localizar custos automáticos

Um botão **Localizar custos automáticos** que está disponível para cada área de custo (viagens, contêiner de remessa e assim por diante) é uma forma de atualizar as transações de custo para essa área de custo a partir das informações nas tabelas de configuração. Quando você seleciona o botão de uma área de custo, o sistema limpa os custos existentes para essa área de custo e cria novos registros com base na configuração atual das tabelas de configuração de custo automático.

Os registros de transação de custo que são criados usando uma entidade de dados são marcados como importados. Esses registros não são excluídos quando você seleciona **Localizar custos automáticos**, pois eles não serão recriados a partir das tabelas de configuração de custo automático. No entanto, um registro de transação de custo sinalizado como importado ainda pode ser excluído.

### <a name="linked-fields"></a>Campos vinculados

Cada transação de custo pode ser associada a outro registro na mesma área de custo. Esta associação é estabelecida por meio do campo **Tipo de custo vinculado**. Ele habilita um valor de custo a ser calculado como uma porcentagem de outro custo.

O campo **Tipo de custo vinculado** só poderá ser validado se o registro referenciado for processado primeiro ou se ele já existir na tabela. O mesmo requisito se aplica ao campo **Trecho vinculado** que é usado somente para custos na área de custo do contêiner de remessa.
