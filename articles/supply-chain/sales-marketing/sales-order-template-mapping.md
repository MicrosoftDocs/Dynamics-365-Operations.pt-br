---
title: "Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de ordem de venda do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition com o Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a>Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales

[!include[banner](../includes/banner.md)]

O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de ordem de venda do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition com o Microsoft Dynamics 365 for Sales. 

## <a name="template-and-tasks"></a>Modelo e tarefas

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar cabeçalhos e linhas da ordem de venda do Finance and Operations com o Sales:

- **Nome do modelo na Integração de dados** 

    - Ordens de vendas (Fin and Ops com Sales)
    
- **Nomes das tarefas no projeto de Integração de dados**

    - OrderHeader
    - OrderLine

As tarefas de sincronização necessárias antes da sincronização do cabeçalho e das linhas da fatura do Sales:

- Produtos (Fin and Ops para Sales)
- Contas (Sales para Fin and Ops) (se usadas)
- Contatos para Clientes (Sales com o Fin and Ops) (se usados)

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations |    Common Data Service (CDS)         |     Vendas      |
|------------------------|----------------|----------------|
| Cabeçalhos de ordens de venda CDS| SalesOrder     | SalesOrders |
| Linhas de ordem de venda do CDS  | SalesOrderLine | SalesOrderDetails|

## <a name="entity-flow"></a>Fluxo de entidades

As ordens de venda são criadas no Finance and Operations e sincronizadas com o Sales.

Os filtros em modelo garantem que somente as ordens de venda relevantes serão incluídas na sincronização:

- A solicitação e faturamento do cliente na ordem de venda originada do Sales serão incluídas na sincronização. No Finance and Operations, os campos **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** são usados para rastrear a sincronização nas entidades de dados.

- A **Ordem de venda** no Finance and Operations deve ser confirmada. Somente ordens de venda confirmadas ou as ordens de venda com status superior, por exemplo, Enviado ou Faturado são sincronizadas com o Sales.

- Após criar ou modificar uma ordem de venda, o trabalho em lote **Calcular totais de vendas** no Finance and Operations deve ser executado. Somente ordens de venda com os totais de vendas calculados serão sincronizadas com o CDS e o Sales.

> [!NOTE]
> Os impostos relacionadas aos encargos no **Cabeçalho de ordem de venda** não são incluídos na sincronização do Finance and Operations com o Sales. Isso porque o Sales não oferece suporte às informações de imposto em nível de cabeçalho. Os impostos relacionadas aos encargos em nível de linha são incluídos.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

Os campos novos são adicionados à entidade **Ordem** e exibidos na página:

- **É mantido externamente** - Definido como **Sim** quando a ordem for proveniente do Finance and Operations.

- **Status de processamento** - Usado para mostrar o status de processamento da ordem no Finance and Operations. Os valores são:

    - Ativos
    - Confirmada
    - Guia de remessa
    - Faturadas
    - Separado
    - Parcialmente separada
    - Parcialmente embalada
    - Remetido
    - Parcialmente remetida
    - Parcialmente faturada
    - Cancelado

A configuração **Tem Somente Produtos Mantidos Externamente** é usada em outros cenários de ordem de venda (de sincronização do Sales para Finance and Operation) para manter o controle consistentemente se a ordem de venda for composta totalmente de **Produtos Mantidos Externamente**, nesse caso os produtos são mantidos no Finance and Operations. Isso garante que você não tentará sincronizar linhas da ordem de vendas com produtos que são desconhecidos com o Finance and Operations.
 
Os botões **Criar fatura**, **Cancelar ordem**, **Recalcular**, **Obter produtos** e **Procurar endereço** na página **Ordem de venda** são ocultos das ordens mantidas externamente porque as faturas serão criadas no Finance and Operations e sincronizadas com o Sales. A página da ordem não é editável porque as informações da ordem de venda serão sincronizadas do Finance and Operations.
 
O **Status da ordem de venda** permanecerá ativo para garantir que as alterações do Finance and Operations podem fluir para a **Ordem de venda** no Sales. Isso é controlado pela definição do **Statecode [Status]** padrão como **Ativo** no projeto de integração de dados.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento 

Antes de sincronizar as ordens de venda, é importante atualizar os sistemas com a seguinte configuração:

### <a name="setup-in-sales"></a>Configuração no Sales

- Garante permissões para a equipe à qual o usuário (de seu **Conjunto de conexão** do Sales) está atribuído. Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas não a equipe. Sem isso você receberá um erro informando que a equipe Principal está faltando ao executar o projeto do Integrador de dados. 

    - Em **Configurações** > **Segurança** > **Equipes**, selecione a equipe relevante, clique em **Gerenciar funções** e selecione uma função com as permissões desejadas, por exemplo, Administrador do Sistema.

- Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que **Usar sistema de cálculo de precificação do sistema** esteja definido como **Sim**. 

- Em **Configurações** > **Administração** > **Configurações do sistema** > **Sales**, certifique-se de que o **Método de cálculo de desconto** esteja definido como **Item de linha**. 

### <a name="setup-in-finance-and-operations"></a>Configuração no Finance and Operations

Defina**Vendas e marketing** > **Tarefas periódicas** > **Calcular os totais de vendas** para executar como trabalho em lotes, com **Calcular total para ordens de venda** definido como **Sim**. Isso é importante porque somente as ordens de venda com os totais de vendas calculados serão sincronizados com o CDS e o Sales. A frequência do trabalho em lotes deve ser alinhada à frequência da sincronização de ordens de venda.

### <a name="setup-in-the-data-integration-project"></a>Configuração no Projeto de integração de dados

#### <a name="salesheader-task"></a>Tarefa de SalesHeader

- Atualize o mapeamento para **ID da Organização CDS na Origem** > **CDS**.

    - O valor do modelo padrão para **Account_Organization_OrganizationId** é ORG001.
    - O valor do modelo padrão para **InvoiceAccount_Organization_OrganizationId** é ORG001.
    - O valor do modelo padrão para **Organization_OrganizationId** é ORG001.

- Verifique se o mapeamento necessário existe em **Origem** > **CDS para InvoiceCountryRegionId para BillingAddress_Country** e para **DeliveryCountryRegionId para DeliveryAddress_Country**.

    - O valor do modelo é **ValueMap** com um número de países mapeado.

- **Lista de preços** é necessário para criar ordens no Sales. Atualize o **ValueMap** em **CDS** > **Destino** para **pricelevelid.name [Price List Name]** para a **Lista de preços** usada no Sales por moeda. Você pode usar a **Lista de preços** padrão para uma única moeda ou usar **ValueMap** se tiver **Listas de preços** em várias moedas.
    
    - O valor padrão do modelo para **pricelevelid.name [Price List Name]** é Serviço CRM USA (amostra). 

#### <a name="salesline-task"></a>Tarefa de SalesLine

- Atualize o mapeamento para **ID da Organização CDS na Origem** > **CDS**. 
    
    - O valor do modelo padrão para **SalesOrder_Organization_OrganizationId** é ORG001.
    - O valor do modelo padrão para **Product_Organization_OrganizationId** é ORG001.

- Verifique se o mapeamento necessário existe na **Origem** > **CDS** para **DeliveryCountryRegionId** para **DeliveryAddress_Country**.

    - O valor do modelo é **ValueMap** com um número de países mapeado.
    
- Verifique se o **ValueMap** necessário para **SalesUnitSymbol** no Finance and Operations existe em **Origem** > **Mapeamento de CDS**.

    - O valor do modelo com **ValueMap** é definido para **SalesUnitSymbol to Quantity_UOM**.

## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelos no integrador de dados

> [!NOTE]
> Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

### <a name="orderheader"></a>OrderHeader

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-1.png)

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a>OrderLine

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-3.png)

![Mapeamento de modelos no integrador de dados](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Tópicos relacionados

[Sincronizar produtos do Finance and Operations com produtos do Sales](products-template-mapping.md)

[Sincronizar contas do Sales com clientes do Finance and Operations](accounts-template-mapping.md)

[Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping.md)

[Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar cabeçalhos e linhas de fatura do Finance and Operations com o Sales](sales-invoice-template-mapping.md)


