---
title: Sincronizar faturas de contrato no Field Service com faturas de texto livre no Supply Chain Management
description: Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar faturas de contrato no Dynamics 365 Field Service às faturas de texto livre no Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: f1790366cebf317472bc1ef9a5ecd2a19fe755d3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980822"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Sincronizar faturas de contrato no Field Service com faturas de texto livre no Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar faturas de contrato no Dynamics 365 Field Service às notas fiscais de texto livre no Dynamics 365 Supply Chain Management.

## <a name="templates-and-tasks"></a>Modelos e tarefas

O modelo e as tarefas subjacentes a seguir são usadas para executar a sincronização de faturas de contrato do Field Service para faturas de texto livre no Supply Chain Management.

**Nome do modelo na Integração de dados**

- Faturas de contrato (Field Service para Supply Chain Management)

**Nomes das tarefas no projeto de Integração de dados**

- Cabeçalhos de fatura
- Linhas da fatura

As sincronização a seguir é necessária antes que a sincronização de faturas de contrato possa ocorrer:

- Contas (Sales para Supply Chain Management) – Direto

## <a name="entity-set"></a>Conjunto de entidades

| Field Service  | Gerenciamento da Cadeia de Fornecedores                 |
|----------------|----------------------------------------|
| faturas       | Cabeçalhos de fatura de texto livre de cliente do Dataverse |
| invoicedetails | Linhas de fatura de texto livre de cliente do Dataverse   |

## <a name="entity-flow"></a>Fluxo de entidades

As faturas criadas com base em um contrato no Field Service podem ser sincronizadas com o Supply Chain Management por um projeto de Integração de dados do Microsoft Dataverse. As atualizações dessas faturas serão sincronizadas com as faturas de texto livre no Supply Chain Management se o status de contabilidade das faturas de texto livre for **Em processamento**. Depois que as faturas de texto livre forem lançadas no Supply Chain Management e o status da contabilidade for atualizado para **Concluído**, você não poderá mais sincronizar atualizações do Field Service.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM

A coluna **Tem Linhas com Origem de Contrato** foi adicionada à tabela **Fatura**. Essa coluna ajuda a garantir que somente as faturas criadas a partir de um contrato sejam sincronizadas. O valor será **verdadeiro** se a fatura contiver pelo menos uma linha de fatura que seja originária de um contrato.

A coluna **Tem Origem de Contrato** foi adicionada à tabela **Linha de fatura**. Essa coluna ajuda a garantir que somente as linhas de fatura criadas a partir de um contrato sejam sincronizadas. O valor será **verdadeiro** se a linha da fatura for originária de um contrato.

**Data da fatura** é um campo obrigatório no Supply Chain Management. Portanto, a coluna deverá ter um valor no Field Service antes que a sincronização ocorra. Para atender a esse requisito, lógica a seguir foi adicionada:

- Se a coluna **Data da fatura** estiver em branco na tabela **Fatura** (ou seja, se não tiver nenhum valor), ela será definida como a data atual quando uma linha de fatura originária de um contrato for adicionada.
- O usuário poderá alterar a coluna **Data da fatura**. No entanto, quando o usuário tentar salvar uma fatura originária de um contrato, ele receberá uma mensagem de erro de processo comercial se a coluna **Data da fatura** estiver em branco na fatura.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="in-supply-chain-management"></a>No Supply Chain Management

Uma origem de fatura deve ser configurada para a integração, para distinguir as faturas de texto livre no Supply Chain Management que são criadas com base em faturas de contrato no Field Service. Quando uma fatura tiver uma origem do tipo **Integração de fatura de contrato** , o campo **Número da fatura externa** será exibido no cabeçalho **Fatura de venda** .

Além de ser exibida no cabeçalho da fatura, as informação de **Número da fatura externa** pode ser usada para ajudar a garantir que as faturas criadas com base em faturas de contrato do Field Service sejam filtradas durante a sincronização de faturas do Supply Chain Management para o Field Service.

1. Acesse **Contas a receber** \> **Configurar** \> **Códigos de origem da fatura**.
2. Selecione **Nova** para criar uma nova origem de fatura.
3. No campo **Origem da fatura** , insira um nome para a origem da fatura, como **FS**.
4. No campo **Descrição** insira uma descrição, como **Fatura de Contrato do Field Service**.
5. Marque a caixa de seleção **Atribuição do tipo de origem** .
6. Defina o campo **Tipo de origem da fatura** como **Integração de fatura de contrato**.
7. Selecione **Salvar**.

### <a name="in-the-data-integration-project"></a>No Projeto de integração de dados

Tarefa: **linhas da fatura**  

Verifique se o valor padrão do campo **Valor de Exibição da Conta Principal** do Supply Chain Management foi atualizado para corresponder ao valor desejado.

O valor do modelo padrão é **401100**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>Faturas de contrato (Field Service para Supply Chain Management): Cabeçalhos de fatura

[![Mapeamento de modelo na Integração de dados](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>Faturas de contrato (Field Service para Supply Chain Management): Linhas da fatura

[![Mapeamento de modelo na Integração de dados](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)
