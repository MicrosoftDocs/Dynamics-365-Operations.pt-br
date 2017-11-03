---
title: Sincronizar contatos do Sales para contatos ou clientes no Finance and Operations
description: "Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar Contato (Contatos) e Contato (Clientes) do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise."
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
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 41e27776b94df059ada13efb9a3dbf6a29d67f36
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Sincronizar contatos do Sales para contatos ou clientes no Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration). 

Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar entidades Contato (Contatos) e Contato (Clientes) do Microsoft Dynamics 365 for Sales (Sales) para o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations).

## <a name="templates-and-tasks"></a>Modelos e tarefas

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar Contato (Contatos) no Sales para Contato (Clientes) no Finance and Operations:

- **Nomes dos modelos.**

    - Contatos (Sales para Fin and Ops)
    - Contatos para Cliente (Sales para o Fin and Ops)

- **Nomes das tarefas no projeto:**

    - Contatos
    - ContactToCustomer

A tarefa de sincronização a seguir será necessária antes da sincronização de Contato: Contas (Sales para o Fin and Ops)

## <a name="entity-sets"></a>Conjuntos de entidades

| Vendas    | CDS     | Finance and Operations |
|----------|---------|------------------------|
| Contatos | Contato | Contatos do CDS           |
| Contatos | Conta | Clientes V2           |

## <a name="entity-flow"></a>Fluxo de entidades

Os Contatos são gerenciados no Sales e são sincronizados para o CDS (Common Data Service) e o Finance and Operations.

Um Contato no Sales pode se tornar um Contato no CDs e no Finance and Operations. Como alternativa, ele poderá se tornar uma Conta no CDS e um Cliente no Finance and Operations. Para determinar se um contato deve ser separado no Sales para sincronização para o CDS e o Finance and Operations (por exemplo, Contatos no Sales &gt; Contato no CDS &gt; Contatos no Finance e Operations), o sistema examina as seguintes propriedades no Contato no Sales:

- **Sincronizar para Conta no CDS e Cliente no Finance and Operations:** Contatos onde **É Cliente Ativo** está definido como **Sim**
- **Sincronizar para Contato no CDS e Contato no Finance and Operations:** Contatos onde **É Cliente Ativo** está definido com **Não** e **Empresa** (Conta/Contato Principal) apontam para uma Conta (e não um Contato)

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales 

Um novo campo **É Cliente Ativo** foi adicionado ao Contato. Esse campo é usado para diferenciar os Contatos com atividade de venda dos Contatos que não têm atividade de venda. **É Cliente Ativo** só será definido como **Sim** para os Contatos com cotações, ordens ou faturas relacionadas. Somente esses Contatos serão sincronizados para o Finance and Operations como Clientes.

Um novo campo **IsCompanyAnAccount** foi adicionado ao Contato. Esse campo é usado para indicar se um Contato está vinculado a uma Empresa (Conta/Contato Principal) do tipo **Conta**. Essa informação é usada para identificar os Contatos que devem ser sincronizados para o Finance and Operations como Contatos.

Um novo campo **Número de Contato** foi adicionado ao Contato para ajudar a garantir uma chave natural e exclusiva para a integração. Quando um novo Contato é criado, um valor **Número de Contato** é automaticamente gerado usando uma sequência numérica. O valor consiste em **CON** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres. Veja um exemplo: **CON-01000-BVRCPS**

Quando a solução de integração para o Sales é adicionada ao Sales, um script de atualização define o campo **Número de Contato** para os Contatos existentes usando a sequência numérica discutida anteriormente. O script de atualização também define o campo **É Cliente Ativo** como **Sim** para todos os Contatos com atividade de venda.

## <a name="in-finance-and-operations"></a>No Finance and Operations 

Os Contatos são marcados com a propriedade **IsContactPersonExternallyMaintained**. Essa propriedade indica que um determinado Contato é mantido externamente. Neste caso, os Contatos mantidos externamente são mantidos no Sales.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

### <a name="contact-to-contact"></a>Contato para Contato

- Atualize **CDS Organization ID** no mapeamento **Source &gt; CDS**.

    - O valor do modelo padrão para **Organization_OrganizationId [Organization ID]** é **ORG001**.
    - O valor do modelo padrão para **PrimaryAccount_Organization_OrganizationId [Organization ID]** é **ORG001**.

- O **código de região País do Endereço** é necessário no Finance and Operations. Para evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento **CDS &gt; Operations**. O valor padrão é usado se o campo for deixado em branco no Sales. O valor do modelo padrão para **PrimaryAddressCountryRegionISOCode** é **USA**.
- Verifique se existe um valor para o campo a seguir no Finance and Operations. Se as informações não forem necessárias no Finance and Operations, você poderá remover o mapeamento do mapeamento **CDS &gt; Destination**.

    - **Nome de campo no Finance and Operations:** Decisão
    - **Mapeamento:** PrimaryAccountRole = DecisionMakingRole

### <a name="contact-to-customer"></a>Contato para Cliente

- Atualize **CDS Organization ID** no mapeamento **Source &gt; CDS**. O valor do modelo padrão para **Organization_OrganizationId [Organization ID]** é **ORG001**.
- O **código de região País do Endereço** é necessário no Finance and Operations. Para evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento **CDS &gt; Destination**. O valor padrão é usado se o campo for deixado em branco no Sales. O valor do modelo padrão para **PrimaryAddressCountryRegionISOCode** é **USA**.
- **CustomerGroup** é necessário no Finance and Operations. Para evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento **CDS &gt; Destination**. O valor padrão é usado se o campo for deixado em branco no Sales. O valor do modelo padrão para **CustomerGroupId** é **10**.
- Ao adicionar os mapeamentos a seguir de **CDS &gt; Destination**, você poderá ajudar a reduzir o número de atualizações manuais existentes no Finance and Operations. Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.

    - **SiteId** - um site padrão também pode ser definido em produtos no Finance and Operations. Um site é necessário para gerar cotações e ordens de venda no Finance and Operations. Não há um valor do modelo definido para **SiteId**.
    - **WarehouseId** - um depósito padrão também pode ser definido em produtos no Finance and Operations. Um depósito é necessário para gerar cotações e ordens de venda no Finance and Operations. Não há um valor do modelo definido para **WarehouseId**.
    - **LanguageId** - um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations. O valor do modelo padrão para **LanguageId** é **en-us**.

## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelos no integrador de dados

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

### <a name="contact-to-contact"></a>Contato para Contato

![Mapeamento de modelos no integrador de dados](./media/contacts-template-mapping-data-integrator-1.png)

![Mapeamento de modelos para Contatos no integrador de dados](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a>Contato para Cliente

![Mapeamento de modelos no integrador de dados](./media/contacts-template-mapping-data-integrator-3.png)

![Mapeamento de modelos para Contatos no integrador de dados](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a>Tópicos relacionados

[Sincronizar produtos do Finance and Operations com produtos do Sales](products-template-mapping.md)

[Sincronizar contas do Sales para clientes no Finance and Operations](accounts-template-mapping.md)

[Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations](sales-quotation-template-mapping.md)

[Sincronizar cabeçalhos e linhas de ordem de venda do Finance and Operations com o Sales](sales-order-template-mapping.md)

[Sincronizar cabeçalhos e linhas de fatura do Finance and Operations com o Sales](sales-invoice-template-mapping.md)

