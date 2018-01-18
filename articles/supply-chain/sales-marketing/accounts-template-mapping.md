---
title: Sincronizar contas do Sales com clientes do Finance and Operations
description: "O tópico discute os modelos e as tarefas subjacentes usadas para sincronizar contas do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise."
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1fdbeaaba53cd439d9872be78b1cf67cbc5a57b9
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a>Sincronizar contas do Sales com clientes do Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar contas do Microsoft Dynamics 365 for Sales (Vendas) com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations).

## <a name="template-and-task"></a>Modelo e tarefa

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar contas do Sales com o Finance and Operations:

- **Nome do modelo:** contas (Sales com Fin and Ops)
- **Nome da tarefa no projeto:** Contas - Conta - Clientes

Tarefas de sincronização necessárias antes da sincronização de conta/cliente: nenhuma

## <a name="entity-set"></a>Conjunto de entidades

| Vendas    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Contas | Conta | Clientes              |

## <a name="entity-flow"></a>Fluxo de entidades

As contas são gerenciadas no Sales e sincronizados com o Finance and Operations como clientes. A propriedade **É Mantido Externamente** nesses clientes é definida como **Sim** para rastrear clientes originários de Sales. Durante o faturamento, essas informações são usadas para filtrar faturas sincronizadas com o Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

O campo **Número da Conta** está disponível na página **Conta**. Criou-se uma chave natural e exclusiva para oferecer suporte à integração. O recurso de chave natural da solução Gerenciamento de Relacionamento com o Cliente (CRM) pode afetar clientes que já usam o campo **Número da Conta**, mas que não utilizam os valores exclusivos **Número da Conta** por conta. Atualmente, a solução de integração não é compatível nesse caso.

Quando uma nova conta é criada, se um valor **Número da Conta** ainda não existe, ele é automaticamente gerado com uma sequência numérica. O valor consiste em **ACC** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres. Veja um exemplo: **ACC-01000-BVRCPS**

Quando a solução de integração para o Sales é aplicada, um script de atualização define o campo **Número da Conta** para as contas existentes no Sales. Se não houver valores **Número da Conta**, a sequência numérica descrita antes será usada.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

- O mapeamento de **CustomerGroupId** de **CDS &gt; Destino** deve ser atualizado para um valor válido no Finance and Operations. É possível especificar um valor padrão ou definir o valor usando um mapa de valores. O valor do modelo padrão é **10**.
- O **código de região do país do Endereço** é necessário no Finance and Operations. Para evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento de **CDS &gt; Destino**. O valor padrão é usado se o campo for deixado em branco no Sales.

    - O valor do modelo padrão para **AddressCountryRegionISOCode** é **USA**.
    - O valor do modelo padrão para **DeliveryAddressCountryRegionISOCode** é **USA**.

- Ao adicionar os mapeamentos a seguir de **CDS &gt; Destino**, você poderá ajudar a reduzir o número de atualizações manuais necessário no Finance and Operations. Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.

    - **SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations. Um site padrão pode ser obtido do produto ou cliente no cabeçalho da ordem. O valor do modelo padrão para **SiteId** é **1**.
    - **WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations. Um depósito padrão pode ser obtido do produto ou cliente no cabeçalho da ordem do Finance and Operations. O valor do modelo padrão para **WarehouseId** é **13**.
    - **LanguageId** – Um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations. Por padrão, o idioma no cabeçalho da ordem do cliente é usado. O valor do modelo padrão para **LanguageId** é **en-us**.

- Atualize a ID da organização do CDS (**Organization_OrganizationId**) no mapeamento **Fonte &gt; CDS**. O valor do modelo padrão é **ORG001**.

## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelos no integrador de dados

> [!NOTE]
> Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é preciso configurar uma mapeamento de valores. Os mapeamentos de valores são específicos para os dados nas organizações entre as quais a entidade está sincronizada.

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

![Mapeamento de modelos no integrador de dados](./media/accounts-template-mapping-data-integrator-1.png)

![Mapeamento de modelos para contas no integrador de dados](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Tópicos relacionados

[Sincronizar produtos do Finance and Operations com produtos do Sales](products-template-mapping.md)

[Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping.md)

[Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales](sales-order-template-mapping.md)

[Sincronizar cabeçalhos e linhas de fatura do Finance and Operations com o Sales](sales-invoice-template-mapping.md)




