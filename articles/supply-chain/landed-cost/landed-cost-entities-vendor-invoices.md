---
title: Entidades de fatura de fornecedor
description: Este artigo fornece informações sobre entidades da fatura de fornecedor, que permitem que códigos de tipo de custo sejam configurados para custos internos ou custos derivados externamente.
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
ms.openlocfilehash: 171b383e1549babd76fd18e4932436a66aa62cc1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873917"
---
# <a name="vendor-invoice-entities"></a>Entidades da fatura de fornecedor

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

O módulo **Custo de entrega** permite que os códigos de tipo de custo sejam configurados para custos internos ou custos derivados externamente. Se um custo for externo a uma empresa, espera-se uma fatura do provedor de serviços. Essa fatura é processada como um diário de fatura que pode ser associado a uma viagem e o valor da fatura pode ser distribuído por um ou mais custos da viagem.

As entidades da fatura de fornecedor permitem que o valor de uma linha do diário seja alocado em um ou mais custos de uma viagem que compartilham o mesmo código de tipo de custo.

Um custo pode ser alocado somente se o cabeçalho do diário de fatura e as linhas do diário de fatura existirem.

## <a name="vendor-voyage-cost-allocations-itmledgerjournalcostlinesvoyagesentity"></a>Alocações de custo de viagem do fornecedor (ITMLedgerJournalCostLinesVoyagesEntity)

A entidade de dados de alocações de custo de viagem do fornecedor permite que uma linha da fatura de fornecedor seja alocada em um ou mais custos que são aplicados à área de custo de viagem. Esta funcionalidade é compatível com a entidade `ITMLedgerJournalCostLinesVoyagesEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor alocado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Número | Número |
| Número da linha da transação de custo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |
| Número da linha do diário | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sim** | Número |
| Número do diário | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sim** | Número |
| Viagem | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sim** | Número |

## <a name="vendor-shipping-container-cost-allocations-itmledgerjournalcostlinescontainersentity"></a>Alocações de custo de contêineres de remessa do fornecedor (ITMLedgerJournalCostLinesContainersEntity)

A entidade de dados de alocações de custo do contêiner de remessa do fornecedor permite que uma linha da fatura de fornecedor seja alocada em um ou mais custos aplicados à área de custo do contêiner de remessa. Esta funcionalidade é compatível com a entidade `ITMLedgerJournalCostLinesContainersEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor alocado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Número | Número |
| Contêiner de remessa | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sim** | Número |
| Número da linha da transação de custo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |
| Número da linha do diário | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sim** | Número |
| Número do diário | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sim** | Número |
| Viagem | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sim** | Número |

## <a name="vendor-folio-cost-allocations-itmledgerjournalcostlinesfoliosentity"></a>Alocações de custo do portfólio do fornecedor (ITMLedgerJournalCostLinesFoliosEntity)

A entidade de dados de alocações de custo de fólio do fornecedor permite que uma linha da fatura de fornecedor seja alocada em um ou mais custos que são aplicados à área de custo de fólio. Esta funcionalidade é compatível com a entidade `ITMLedgerJournalCostLinesFoliosEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor alocado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Número | Número |
| Número da linha da transação de custo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |
| Fólio | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sim** | Número |
| Número da linha do diário | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sim** | Número |
| Número do diário | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sim** | Número |

## <a name="vendor-purchase-order-cost-allocations-itmledgerjournalcostlinespurchtableentity"></a>Alocações de custo de pedido de compra do fornecedor (ITMLedgerJournalCostLinesPurchTableEntity)

A entidade de dados de alocações de custo do pedido de compra do fornecedor permite que uma linha da fatura de fornecedor seja alocada em um ou mais custos que são aplicados à área de custo do pedido de compra. Esta funcionalidade é compatível com a entidade `ITMLedgerJournalCostLinesPurchTableEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor alocado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Número | Número |
| Número da linha da transação de custo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |
| Número da linha do diário | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sim** | Número |
| Número do diário | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sim** | Número |
| Ordem de compra | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sim** | Número |

## <a name="vendor-item-cost-allocations-itmledgerjournalcostlinespurchlineentity"></a>Alocações de custo de item de fornecedor (ITMLedgerJournalCostLinesPurchLineEntity)

A entidade de dados de alocações de custo de item do fornecedor permite que uma linha da fatura de fornecedor seja alocada em um ou mais custos que são aplicados à área de custo de item. A área de custo do item cobre os custos na linha do pedido. Esta funcionalidade é compatível com a entidade `ITMLedgerJournalCostLinesPurchLineEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor alocado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Número | Número |
| Número da linha da transação de custo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |
| Número da linha do diário | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sim** | Número |
| Número do diário | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sim** | Número |
| Ordem de compra | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sim** | Número |
| Número da linha da ordem de compra | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |

## <a name="vendor-transfer-order-line-cost-allocations-itmledgerjournalcostlinestransferlineentity"></a>Alocações de custo de linha de pedido de transferência do fornecedor (ITMLedgerJournalCostLinesTransferLineEntity)

A entidade de dados de alocações de custo de linha de pedido de transferência do fornecedor permite que uma linha de fatura do fornecedor seja alocada em um ou mais custos aplicados à área de custo de linha de transferência. Esta funcionalidade é compatível com a entidade `ITMLedgerJournalCostLinesTransferLineEntity`. A tabela a seguir lista os campos e mapeamentos que compõem essa entidade.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Valor alocado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | Número | Número |
| Número da linha da transação de custo | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |
| Número da linha do diário | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sim** | Número |
| Número do diário | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sim** | Número |
| Ordem de transferência | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sim** | Número |
| Número da linha do pedido de transferência | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sim** | Número |

### <a name="reference-table"></a>Tabela de referência

As linhas de custo de viagem têm uma associação direta com um registro de transação de custo. Este registro inclui o valor **ID da tabela de referência**. Esse valor é exclusivo para cada área de custo (viagem, contêiner de transporte etc.). Quando números de tabela específicos são referenciados para dados criados usando entidades de dados, as entidades são divididas com base nos valores de **ID da tabela de referência**.

Os valores da tabela de referência (`RefTableId`) e o tipo de transação (`TransType`) estão implícitos na seleção da linha de compra de custo de entrega ou da entidade de linha de transferência de custo de entrega.

## <a name="vendor-invoice-journal-lines-vendorinvoicejournallineentity"></a>Linhas do diário de fatura do fornecedor (VendorInvoiceJournalLineEntity)

Antes que um valor de linha de lançamento possa ser alocado a um ou mais custos no módulo **Custo de entrega**, a linha de lançamento deve ser associada a uma área de custo. Para oferecer suporte a essa funcionalidade, o módulo **Custo de entrega** adiciona alguns novos campos à tabela de linhas do diário (`LedgerJournalTrans`).

### <a name="fields-added-to-the-vendor-invoice-journal-line-entity"></a>Campos adicionados à entidade de linha do diário da fatura de fornecedor

A tabela a seguir lista os campos que o módulo **Custo de entrega** adiciona à entidade de linha do diário de fatura do fornecedor (`VendorInvoiceJournalLineEntity`). Esses campos permitem que o sistema crie linhas de diário e atribua custos a elas.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Área de custo | LedgerJournalTrans.ITMCostArea | Int | Número | Número |
| Código de tipo de custo | LedgerJournalTrans.ITMCostTypeId | Nvarchar(20) | Número | Número |

### <a name="mainoffset-account"></a>Conta principal/de contrapartida

A conta principal/de contrapartida para uma linha de diário de fatura associada a uma viagem de custo desembarcado é determinada pelo código do tipo de custo. Quando o código do tipo de custo é incluído na linha do diário de fatura, a conta de contrapartida do código será usada como conta principal ou conta de contrapartida, dependendo do cenário:

- **Diário de linha única** – Se uma conta principal (em outras palavras, a conta do fornecedor) for definida e um código de tipo de custo for fornecido, o valor da conta de contrapartida para esse código de tipo de custo será inserido na conta de contrapartida.
- **Diário de várias linhas** – Se uma conta principal não for definida, mas um código de tipo de custo for fornecido, o valor da conta de contrapartida para esse código de tipo de custo será inserido na conta principal. A linha do diário que está creditando o fornecedor não fará referência a um código de tipo de custo.

## <a name="sequencing"></a>Sequenciamento

Devido às dependências entre as tabelas de diário e de linhas de diário, o registro de viagem deve ser criado primeiro. As linhas de viagem podem ser criadas somente após a criação da viagem, do contêiner de remessa e dos fólios.

Para alocar uma fatura de viagem, o sistema deve processar as entidades na seguinte ordem:

1. Título de diário de faturas (`VendInvoiceJournalHeaderEntity`)
1. Linha de diário de faturas (`VendInvoiceJournalLineEntity`)
1. Alocações de custo de entrega (`ITMLedgerJournalEntities`)
