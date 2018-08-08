---
title: Sincronizar faturas de contrato do Field Service com faturas de texto livre no Finance and Operations
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar faturas de contrato no Microsoft Dynamics 365 for Field Service com faturas de texto livre no Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: ace66c037953f4b1b2e8b93a315faefdb090b1eb
ms.openlocfilehash: 6672e283a5e56b068e3494d53a0fd6dd08253ba9
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-finance-and-operations"></a>Sincronizar faturas de contrato do Field Service com faturas de texto livre no Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar faturas de contrato no Microsoft Dynamics 365 for Field Service com faturas de texto livre no Microsoft Dynamics 365 for Finance and Operations.

## <a name="templates-and-tasks"></a>Modelos e tarefas

O modelo e as tarefas subjacentes a seguir são usadas para executar a sincronização de faturas de contrato no Field Service com faturas de texto livre no Finance and Operations.

**Nome do modelo na Integração de dados:**

- Faturas de contrato (Field Service com o Fin and Ops)

**Nomes das tarefas no projeto de Integração de dados:**

- Cabeçalhos de fatura
- Linhas da fatura

As sincronização a seguir é necessária antes que a sincronização de faturas de contrato possa ocorrer:

- Contas (Sales com o Fin and Ops) – Direto

## <a name="entity-set"></a>Conjunto de entidades

| Field Service  | Finance and Operations                 |
|----------------|----------------------------------------|
| faturas       | Cabeçalhos de fatura de texto livre de cliente CDS |
| invoicedetails | Linhas de fatura de texto livre de cliente CDS   |

## <a name="entity-flow"></a>Fluxo de entidades

As faturas criadas a partir de um contrato no Field Service podem ser sincronizadas com o Finance and Operations por um projeto de Integração de dados de CDS (Common Data Service). As atualizações dessas faturas serão sincronizadas com as faturas de texto livre no Finance and Operations se o status de contabilidade das faturas de texto livre for **Em processamento**. Depois que as faturas de texto livre forem lançadas no Finance and Operations e o status da contabilidade for atualizado para **Concluído**, você não poderá mais sincronizar atualizações do Field Service.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM

O campo **Tem Linhas com Origem de Contrato** foi adicionado à entidade **Fatura**. Esse campo ajuda a garantir que somente as faturas criadas a partir de um contrato sejam sincronizadas. O valor será **verdadeiro** se a fatura contiver pelo menos uma linha de fatura que seja originária de um contrato.

O campo **Tem Origem de Contrato** foi adicionado à entidade **Linha da Fatura**. Esse campo ajuda a garantir que somente as linhas de faturas criadas a partir de um contrato sejam sincronizadas. O valor será **verdadeiro** se a linha da fatura for originária de um contrato.

**Data da fatura** é um campo obrigatório no Finance and Operations. Portanto, o campo deverá ter um valor no Field Service antes que a sincronização ocorra. Para atender a esse requisito, lógica a seguir foi adicionada:

- Se o campo **Data da fatura** estiver em branco na entidade **Fatura** (ou seja, se não tiver nenhum valor), ela será definida como a data atual quando uma linha de fatura originária de um contrato for adicionada.
- O usuário poderá alterar o campo **Data da fatura**. No entanto, quando o usuário tentar salvar uma fatura originária de um contrato, ele receberá uma mensagem de erro de processo comercial se o campo **Data da fatura** estiver em branco na fatura.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="in-finance-and-operations"></a>No Finance and Operations

Uma origem de fatura deve ser configurada para a integração para distinguir as faturas de texto livre no Finance and Operations que são criadas a partir de faturas de contrato no Field Service. Quando uma fatura tiver uma origem do tipo **Integração de fatura de contrato** , o campo **Número da fatura externa** será exibido no cabeçalho **Fatura de venda** .

Além de ser exibido no cabeçalho da fatura, as informações **Número da fatura externa** podem ser usadas para ajudar a garantir que as faturas criadas a partir de faturas de contrato do Field Service serão filtradas durante a sincronização de faturas do Finance and Operations com o Field Service.

1. Acesse **Contas a receber** \> **Configurar** \> **Códigos de origem da fatura**.
2. Selecione **Nova** para criar uma nova origem de fatura.
3. No campo **Origem da fatura** , insira um nome para a origem da fatura, como **FS**.
4. No campo **Descrição** insira uma descrição, como **Fatura de Contrato do Field Service**.
5. Marque a caixa de seleção **Atribuição do tipo de origem** .
6. Defina o campo **Tipo de origem da fatura** como **Integração de fatura de contrato**.
7. Selecione **Salvar**.

### <a name="in-the-data-integration-project"></a>No Projeto de integração de dados

Tarefa: **linhas da fatura**  

Verifique se o valor padrão do campo **Valor de Exibição da Conta Principal** do Finance and Operations foi atualizado para corresponder o valor desejado.

O valor do modelo padrão é **401100**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-headers"></a>Faturas de contrato (Field Service com o Fin and Ops): Cabeçalhos de fatura

[![Mapeamento de modelo na Integração de dados](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-fin-and-ops-invoice-lines"></a>Faturas de contrato (Field Service com o Fin and Ops): Linhas de fatura

[![Mapeamento de modelo na Integração de dados](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)

