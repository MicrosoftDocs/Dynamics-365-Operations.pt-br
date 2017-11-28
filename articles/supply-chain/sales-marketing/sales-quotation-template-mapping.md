---
title: "Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c8cfc484eed02423dbf0c7caaf8ac2337b6ac38d
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a>Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda do Microsoft Dynamics 365 for Sales (Sales) com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations). 

## <a name="template-and-tasks"></a>Modelo e tarefas

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations:

- **Nome do modelo:** Cotações de venda (Sales para Fin e Ops)
- **Nomes das tarefas no projeto:**

    - QuoteHeader
    - QuoteLine

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de cotação de venda possa ocorrer:

- Produtos (Fin and Ops para Sales)
- Contas (Sales para Fin and Ops) (se usadas)
- Contatos para Clientes (Sales com o Fin and Ops) (se usados)

## <a name="entity-set"></a>Conjunto de entidades

| Vendas        | CDS           | Finance and Operations    |
|--------------|---------------|---------------------------|
| Cotações       | Cotação     | Cabeçalhos de cotação de venda   |
| QuoteDetails | QuotationLine | Linhas de cotação de venda do CDS |

## <a name="entity-flow"></a>Fluxo de entidades

As cotações de vendas são criadas no Sales e sincronizadas ao Finance and Operations.

As cotações de vendas do Sales são sincronizadas somente se as seguintes condições forem atendidas:

- Todos os produtos nas linhas de cotação de vendas são mantidas externamente.
- A cotação de venda está ativa ou ativada.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade Cotação para rastrear consistentemente se a cotação de vendas consiste totalmente de produtos mantidos externamente. Se uma cotação de venda mantiver somente produtos externamente, os produtos serão mantidos no Finance and Operations. Este comportamento ajuda a garantir que você não tente sincronizar linhas da cotação de vendas com produtos que são desconhecidos para Finance and Operations.

Todos os produtos e linhas da cotação são atualizados com as informações **Tem Somente Produtos Mantidos Externamente** do cabeçalho de cotação. Essas informações podem ser encontradas no campo **A Cotação Tem Somente Produtos Mantidos Externamente** na entidade Linha de cotação.

Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Finance and Operations. Essa configuração não suporta atualmente mapeamento de integração. No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são dominados e tratados pelo Finance and Operations.

No Sales, a solução torna os seguintes campos somente para leitura, porque os valores não são sincronizados com o Finance and Operations:

- **Campos somente leitura no cabeçalho de cotação de vendas:** % de Desconto, Desconto, Valor do Frete
- **Campos somente leitura nas linhas de cotação de venda:** Imposto

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de sincronizar as ordens de venda, é importante atualizar os sistemas com a seguinte configuração:

### <a name="setup-in-sales"></a>Configuração no Sales

- Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Sales** e certifique-se de que o campo **Método de cálculo de desconto** esteja definido como **Por unidade**. Esta configuração ajuda a garantir que o desconto do item de linha do Sales corresponde à configuração no Finance and Operations. Caso contrário, o desconto não será correto no Finance and Operations, porque o Finance and Operations irá ler o desconto como um desconto por unidade, mesmo se ele tiver um desconto por linha no Sales.

### <a name="setup-in-finance-and-operations"></a>Configuração no Finance and Operations

- Vá para **Contas a receber** &gt; **Configurar** &gt; **Parâmetros de contas a receber**. Na guia **Sequência numérica**, selecione a sequência numérica para cotações de venda, e clique em **Exibir detalhes**. Em seguida, em **Configuração geral**, defina o campo **Manual** como **Sim**.
- Vá para **Contas a receber** &gt; **Configurar** &gt; **Parâmetros de contas a receber**. Em seguida, na guia **Remessas**, defina o campo **Controle da data de entrega** como **Nenhum**. Essa configuração ajuda a evitar que a sincronização falhe para cotações de venda.

### <a name="setup-in-the-data-integration-project"></a>Configuração no Projeto de integração de dados

#### <a name="quoteheader"></a>QuoteHeader

- O campo **Data de entrega solicitada** é obrigatório no Finance and Operations e a sincronização falhará se o campo ficar em branco. Para evitar esse problema, se o campo estiver em branco, uma data padrão é obtida de **Origem &gt; CDS**. A data deve ser atualizada para um valor preferido. Atualmente, não poderá inserir um valor como **Hoje** para representar a data de hoje. Você deve digitar uma data específica. O valor do modelo padrão para **Data de entrega solicitada:** é **1/1/2020**.
- O **Código de região do país do endereço** é obrigatório no Finance and Operations. Para ajudar a evitar erros de sincronização, você pode especificar um valor padrão a ser usado, se o campo ficar em branco no Sales. Esse valor padrão também é útil, porque você não precisa inserir um valor manualmente no campo **País/região** para endereços locais. Não há valor do modelo padrão para **DeliveryAddressCountryRegionISOCode**.
- Atualize o mapeamento para **ID da Organização CDS** em **Fonte &gt; CDS**, de forma que ele corresponda a **Organização CDS** na entidade da Organização:

    - O valor do modelo padrão para **Organization_OrganizationId** é **ORG001**.
    - O valor do modelo padrão para **Account_Organization_OrganizationId** é **ORG001**.
    - O valor do modelo padrão para **InvoiceAccount_OrganizationId** é **ORG001**.

#### <a name="quoteline"></a>QuoteLine

- Atualize o mapeamento para **ID da Organização CDS** em **Fonte &gt; CDS**, de forma que ele corresponda a **Organização CDS** na entidade da Organização:

    - O valor do modelo padrão para **Organization_OrganizationId** é **ORG001**.
    - O valor do modelo padrão para **Product_Organization_Organization_OrganizationId** é **ORG001**.
    - O valor do modelo padrão para **Quotation_Organization_Organization_OrganizationId** é **ORG001**.

- O campo **Data de entrega solicitada** é obrigatório no Finance and Operations e a sincronização falhará se o campo ficar em branco. Para evitar esse problema, se o campo estiver em branco, uma data padrão é obtida de **Origem &gt; CDS**. A data deve ser atualizada para um valor preferido. Atualmente, não poderá inserir um valor como **Hoje** para representar a data de hoje. Você deve digitar uma data específica. O valor do modelo padrão para **Data de entrega solicitada:** é **1/1/2020**.
- Você pode adicionar os seguintes mapeamentos de **CDS &gt; Destino** para ajudar a garantir que as linhas de cotação serão importadas para Finance and Operations, se não houver informações padrão do cliente ou do produto:

    - **SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations. Não há valor do modelo padrão para **SiteId**.
    - **WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations. Não há valor do modelo padrão para **WarehouseId**.

- Certifique-se de que existe o mapa de valor obrigatório para a unidade de medida (UDM) de vendas no Finance and Operations no mapeamento de **CDS &gt; Destino** para **Quantity_UOM** para **SALESUNITSYMBOL**.

## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelos no integrador de dados

> [!NOTE]
> - Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Finance and Operations. Essa configuração não suporta atualmente mapeamento de integração. No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são tratados pelo Finance and Operations.
> - Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

### <a name="quoteheader"></a>QuoteHeader

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a>QuoteLine

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Tópicos relacionados

[Sincronizar produtos do Finance and Operations com produtos do Sales](products-template-mapping.md)

[Sincronizar contas do Sales com clientes do Finance and Operations](accounts-template-mapping.md)

[Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping.md)



