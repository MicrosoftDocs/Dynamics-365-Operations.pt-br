---
title: Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management
description: Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar entidades de Contato (Contatos) e Contato (Clientes) entre o Dynamics 365 Sales e o Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 084030ab6ff06a1140621bb91435edf6cff4f82cc4bbc13813ab46f76e42174d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756838"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a>Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Microsoft Dataverse para Aplicativos](/powerapps/administrator/data-integrator).

Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar entidades de Contato (Contatos) e Contato (Clientes) diretamente do Dynamics 365 Sales para o Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales. Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.

[![Fluxo de dados em Prospect to cash.](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração do PowerApps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar tabelas de Contato (Contatos) no Sales com tabelas de Contato (Clientes) no Supply Chain Management.

- **Nomes dos modelos na Integração de dados**

    - Contatos (Sales para Supply Chain Management) - Direto
    - Contatos para Cliente (Sales para Supply Chain Management) - Direto

- **Nomes das tarefas no projeto de Integração de dados**

    - Contatos
    - ContactToCustomer

A tarefa de sincronização a seguir é necessária para que a sincronização de contatos possa ocorrer: Contas (Sales para Supply Chain Management)

## <a name="entity-sets"></a>Conjuntos de entidades

| Vendas    | Gerenciamento da Cadeia de Fornecedores |
|----------|------------------------|
| Contatos | Contatos do Dataverse           |
| Contatos | Clientes V2           |

## <a name="entity-flow"></a>Fluxo de entidades

Os contatos são gerenciados no Sales e sincronizados para o Supply Chain Management.

Um contato no Sales pode se tornar um contato ou um cliente no Supply Chain Management. Para determinar se um contato no Sales deve ser sincronizado com o Supply Chain Management como um contato ou um cliente, o sistema analisa as seguintes propriedades no contato no Sales:

- **Sincronização com um cliente no Supply Chain Management:** Contatos em que **É Cliente Ativo** está definido como **Sim**
- **Sincronização com um contato no Supply Chain Management:** Contatos em que **É Cliente Ativo** está definido como **Não** e **Empresa** (conta/contato primário) aponta para uma conta (e não um contato)

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

Uma nova coluna **É Cliente Ativo** foi adicionada ao contato. Essa coluna é usada para diferenciar os contatos com atividade de venda dos contatos que não têm atividade de venda. **É Cliente Ativo** só será definido como **Sim** para os contatos com cotações, ordens ou faturas relacionadas. Somente esses contatos são sincronizados com o Supply Chain Management como clientes.

Uma nova coluna **IsCompanyAnAccount** foi adicionada ao contato. Essa coluna indica se um contato está vinculado a uma empresa (conta/contato primário) do tipo **Conta**. Essa informação é usada para identificar os contatos que devem ser sincronizados com o Supply Chain Management como contatos.

Uma nova coluna **Número de Contato** foi adicionada ao contato para ajudar a garantir uma chave natural e exclusiva para a integração. Quando um novo contato é criado, um valor **Número de Contato** é automaticamente gerado usando uma sequência numérica. O valor consiste em **CON** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres. Veja um exemplo: **CON-01000-BVRCPS**

Quando a solução de integração para o Sales é aplicada, um script de atualização define a coluna **Número de Contato** para os contatos existentes usando a sequência numérica mencionada anteriormente. O script de atualização também define a coluna **É Cliente Ativo** como **Sim** para todos os contatos com atividade de venda.

## <a name="in-supply-chain-management"></a>No Supply Chain Management

Os Contatos são marcados com a propriedade **IsContactPersonExternallyMaintained**. Essa propriedade indica que um determinado contato é mantido externamente. Nesse caso, os contatos mantidos externamente são mantidos no Sales.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

### <a name="contact-to-customer"></a>Contato para cliente

- **CustomerGroup** é necessário no Supply Chain Management. Para ajudar a evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento. O valor padrão é usado se a coluna for deixado em branco no Sales.

    O valor do modelo padrão é **10**.

- Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Supply Chain Management. Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.

    - **SiteId** – Um site padrão também pode ser definido em produtos no Supply Chain Management. Um site é necessário para gerar cotações e ordens de venda no Supply Chain Management.

        Não há um valor do modelo definido para **SiteId**.

    - **WarehouseId** – Um depósito padrão também pode ser definido em produtos no Supply Chain Management. Um depósito é necessário para gerar cotações e ordens de venda no Supply Chain Management.

        Não há um valor do modelo definido para **WarehouseId**.

    - **LanguageId** – Um idioma é necessário pra gerar cotações e pedidos de venda no Supply Chain Management.
    
        O valor padrão do modelo é **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de coluna serão sincronizadas do Sales com o Supply Chain Management.

### <a name="contact-to-contact"></a>Contato para contato

![Mapeamento de modelos no Integrador de dados.](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a>Contato para cliente

![Mapeamento de modelos no Integrador de dados.](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a>Tópicos relacionados

[De cliente potencial ao pagamento à vista](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes no Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales](products-template-mapping-direct.md)

[Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]