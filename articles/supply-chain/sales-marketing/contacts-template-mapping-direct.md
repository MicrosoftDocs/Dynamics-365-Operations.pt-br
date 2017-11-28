---
title: Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar Contato (Contatos) e Contato (Clientes) de entidades do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition"
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: 8de9a920f384b69c9b3764a0431208bbdcb395bf
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a>Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar Contato (Contatos) e Contato (Clientes) de entidades diretamente do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales. Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar entidades de Contato (Contatos) no Sales com entidades de Contato (Clientes) no Finance and Operations:

- **Nomes dos modelos na Integração de dados:**

    - Contatos (Sales com o Fin and Ops) – Direto
    - Contatos para Cliente (Sales com o Fin and Ops) – Direto

- **Nomes das tarefas no projeto de Integração de dados:**

    - Contatos
    - ContactToCustomer

A tarefa de sincronização a seguir é necessária para que a sincronização de contatos possa ocorrer: Contas (Sales com o Fin and Ops)

## <a name="entity-sets"></a>Conjuntos de entidades

| Vendas    | Finance and Operations |
|----------|------------------------|
| Contatos | Contatos do CDS           |
| Contatos | Clientes V2           |

## <a name="entity-flow"></a>Fluxo de entidades

Os contatos são gerenciados no Sales e sincronizados com o Finance and Operations.

Um contato no Sales pode se tornar um contato ou um cliente no Finance and Operations. Para determinar se um contato no Sales deve ser sincronizado com o Finance and Operations como um contato ou um cliente, o sistema analisa as seguintes propriedades no contato no Sales:

- **Sincronização com um cliente no Finance and Operations:** Contatos em que **É Cliente Ativo** está definido como **Sim**
- **Sincronização com um contato no Finance and Operations:** Contatos em que **É Cliente Ativo** está definido como **Não** e **Empresa** (conta/contato primário) apontam para uma conta (e não um contato)

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

Um novo campo **É Cliente Ativo** foi adicionado ao contato. Esse campo é usado para diferenciar os contatos com atividade de venda dos contatos que não têm atividade de venda. **É Cliente Ativo** só será definido como **Sim** para os contatos com cotações, ordens ou faturas relacionadas. Somente esses contatos serão sincronizados com o Finance and Operations como clientes.

Um novo campo **IsCompanyAnAccount** foi adicionado ao contato. Esse campo indica se um contato está vinculado a uma empresa (conta/contato primário) do tipo **Conta**. Essa informação é usada para identificar os contatos que devem ser sincronizados com o Finance and Operations como contatos.

Um novo campo **Número de Contato** foi adicionado ao contato para ajudar a garantir uma chave natural e exclusiva para a integração. Quando um novo contato é criado, um valor **Número de Contato** é automaticamente gerado usando uma sequência numérica. O valor consiste em **CON** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres. Veja um exemplo: **CON-01000-BVRCPS**

Quando a solução de integração para o Sales é aplicada, um script de atualização define o campo **Número de Contato** para os contatos existentes usando a sequência numérica mencionada anteriormente. O script de atualização também define o campo **É Cliente Ativo** como **Sim** para todos os contatos com atividade de venda.

## <a name="in-finance-and-operations"></a>No Finance and Operations

Os Contatos são marcados com a propriedade **IsContactPersonExternallyMaintained**. Essa propriedade indica que um determinado contato é mantido externamente. Nesse caso, os contatos mantidos externamente são mantidos no Sales.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

### <a name="contact-to-customer"></a>Contato para cliente

- **CustomerGroup** é necessário no Finance and Operations. Para ajudar a evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento. O valor padrão é usado se o campo for deixado em branco no Sales.

    O valor do modelo padrão é **10**.

- Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Finance and Operations. Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.

    - **SiteId** – um site padrão também pode ser definido em produtos no Finance and Operations. Um site é necessário para gerar cotações e ordens de venda no Finance and Operations.

        Não há um valor do modelo definido para **SiteId**.

    - **WarehouseId** – um depósito padrão também pode ser definido em produtos no Finance and Operations. Um depósito é necessário para gerar cotações e ordens de venda no Finance and Operations.

        Não há um valor do modelo definido para **WarehouseId**.

    - **LanguageId** – Um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations.
    
        O valor padrão do modelo é **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..

### <a name="contact-to-contact"></a>Contato para contato

![Mapeamento de modelo no Integrador de dados](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Contato para cliente

![Mapeamento de modelo no Integrador de dados](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Tópicos relacionados

[Prospect to cash](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes do Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar produtos diretamente do Finance and Operations com produtos no Sales](products-template-mapping-direct.md)

[Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales](sales-order-template-mapping-direct.md)

[Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales](sales-invoice-template-mapping-direct.md)



