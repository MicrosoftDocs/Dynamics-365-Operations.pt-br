---
title: Sincronize valores reais do projeto do Project Service Automation diretamente para o diário de integração do projeto para lançamento no Finance and Operations.
description: Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar valores reais do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 3b6427d7eede8fe35fcd86928c3d5b8507876e2e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846066"
---
# <a name="synchronize-project-actuals-directly-from-project-service-automation-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Sincronize valores reais do projeto do Project Service Automation diretamente para o diário de integração do projeto para lançamento no Finance and Operations.

[!include[banner](../includes/banner.md)]

Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar valores reais do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Microsoft Dynamics 365 for Finance and Operations.

O modelo sincroniza transações do Project Service Automation para uma tabela de preparo no Finance and Operations. Após a sincronização ser concluída, você **deverá** importar os dados da tabela de preparo para o diário de integração.

> [!NOTE]
> - A integração de valores reais do projeto está disponível no Microsoft Dynamics 365 for Finance and Operations versão 8.01.
> - Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade. Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.
> - Se você estiver usando o Finance and Operations 7.3.0 e estiver transferindo as transações de taxa do Project Service Automation, instale o KB 4345320 para incluir essas taxas na fatura do projeto.
> - Se estiver inserindo valores de impostos em transações de tempo ou de despesas no Project Service Automation, instale a atualização 7 do Project Service Automation. Caso contrário, os valores reais de impostos não serão vinculados aos valores reais associados de tempo ou de despesas, bem como não serão sincronizados com o Finance and Operations. Para obter mais informações, entre em contato com o suporte.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Fluxo de dados do Project Service Automation para o Finance and Operations

A solução de integração do Project Service Automation para o Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre valores reais do projeto do Project Service Automation para o Finance and Operations.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.

[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)

## <a name="project-actuals-from-project-service-automation"></a>Valores reais do projeto a partir do Project Service Automation

### <a name="template-and-tasks"></a>Modelo e tarefas

Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e as tarefas subjacentes são usados para sincronizar valores reais do projeto do Project Service Automation para o Finance and Operations:

- **Nome do modelo na Integração de dados:** valores reais do projeto (do PSA para o Fin and Ops)
- **Nome das tarefas no projeto:**

    - Reais
    - TransactionConnections

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finance and Operations                                   |
|----------------------------|----------------------------------------------------------|
| Reais                    | Entidade de integração para valores reais do projeto                   |
| Conexões com transações    | Entidade de integração para relacionamentos de transações do projeto |

### <a name="entity-flow"></a>Fluxo de entidades

Os valores reais do projeto são gerenciados no Project Service Automation e são sincronizados para o diário de integração do projeto no o Finance and Operations. A contabilidade será aplicada com base nas dimensões financeiras padrão e na configuração de lançamento.

### <a name="prerequisites"></a>Pré-requisitos

Antes da sincronização de valores reais, você deve configurar parâmetros de integração do Project Service Automation e sincronizar projetos, tarefas de projetos e categorias de transação de despesa do projeto.

### <a name="power-query"></a>Power Query

No modelo de valores reais, você deve usar o Microsoft Power Query para Excel para concluir estas tarefas:

- Transformar o tipo de transação no Project Service Automation no tipo de transação correto no Finance and Operations. Essa transformação já está definida no modelo de valores reais do projeto (do PSA para o Fin and Ops).
- Transformar o tipo de cobrança do Project Service Automation no tipo de cobrança correto do Finance and Operations. Essa transformação já está definida no modelo de valores reais do projeto (do PSA para o Fin and Ops). O tipo de cobrança é mapeado para a propriedade de linha com base na configuração na página **Parâmetros de integração do Project Service Automation**.
- Filtre para unidades organizacionais de recurso específicas que devem ser sincronizadas com esse modelo.
- Se tempo intercompanhia ou valores reais de despesas intercompanhia forem sincronizados para o Finance and Operations, você deverá transformar a unidade organizacional de contrato na entidade legal correta no Finance and Operations. No modelo de valores reais do projeto (do PSA para o Fin and Ops), uma coluna condicional é definida com base em dados de demonstração. Você deve atualizar a última coluna condicional inserida para as entidades legais corretas. Caso contrário, poderá ocorrer um erro de integração ou transações reais incorretas poderão ser importadas para o Finance and Operations.
- Se tempo intercompanhia ou valores reais de despesas intercompanhia não forem sincronizados para o Finance and Operations, você deverá excluir a última coluna condicional inserida do modelo. Caso contrário, poderá ocorrer um erro de integração ou transações reais incorretas poderão ser importadas para o Finance and Operations.

#### <a name="contract-organizational-unit"></a>Unidade organizacional de contrato
Para atualizar a coluna condicional inserida no modelo, clique na seta **Mapa** para abrir o mapeamento. Selecione o link **Filtragem e consulta avançada** para abrir o Power Query.

- Se você estiver usando o modelo de valores reais do Project padrão (do PSA para o Fin and Ops), no Power Query, selecione a última **Condição inserida** na seção **Etapas aplicadas**. Na entrada **Função**, substitua **USSI** pelo nome da entidade legal que deve ser usado com a integração. Adicione condições adicionais à entrada **Função** conforme necessário e atualize a condição **else** do **USMF** para a entidade legal correta.
- Se estiver criando um novo modelo, você deverá adicionar a coluna para dar suporte a tempo e despesas intercompanhia. Selecione **Adicionar coluna condicional** e atribua um nome à coluna, como **LegalEntity**. Insira uma condição para a coluna em que, se **msdyn\_contractorganizationalunitid.msdyn\_name** for \<unidade organizacional\>, \<insira a entidade legal\>; caso contrário, o valor será nulo.

### <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um exemplo do mapeamento da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mapeamento de modelo](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table-after-integration-from-project-service-automation"></a>Importar da tabela de preparação após a integração do Project Service Automation

A importação do processo periódico da tabela de preparo deve ser executada após a sincronização de valores reais do Project Service Automation para o Finance and Operations. Este processo importará as transações do projeto da tabela de preparo para o diário de integração do Project Service Automation, em que a contabilidade é aplicada e as transações importadas podem ser lançadas. Recomendamos que você execute esse processo em modo de lote e, opcionalmente, configurar para executar como um lote recorrente.

## <a name="update-actuals-from-finance-and-operations"></a>Atualizar valores reais do Finance and Operations

### <a name="template-and-tasks"></a>Modelo e tarefas

O seguinte modelo e as tarefas subjacentes são usados para sincronizar o número do comprovante e os impostos para transações de projeto lançadas do Finance and Operations para o Project Service Automation:

- **Nome do modelo na Integração de dados:** atualização de valores reais do projeto (Fin and Ops para PSA)
- **Nome das tarefas no projeto:**

    - Reais 
    - TransactionConnections

### <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations                                   | Project Service Automation |
|----------------------------------------------------------|----------------------------|
| Entidade de integração para valores reais do projeto                   | Reais                    |
| Entidade de integração para relacionamentos de transações do projeto | Conexões com transações    |

### <a name="entity-flow"></a>Fluxo de entidades

Os valores reais do projeto são gerenciados no Project Service Automation e são sincronizados para o diário de integração do projeto no o Finance and Operations. Após os valores reais serem lançados depois no Finance and Operations, eles são atualizados no Project Service Automation com o número de comprovante do Finance and Operations. Se os impostos tiverem sido adicionados no Finance and Operations, os novos valores reais de impostos serão criados no Project Service Automation.

### <a name="power-query"></a>Power Query

No modelo de atualização de valores reais, você deve usar o Power Query para concluir estas tarefas:

- Transformar o tipo de transação no Finance and Operations no tipo de transação correto no Project Service Automation. Essa transformação já está definida no modelo atualização de valores reais do projeto (o Fin and Ops para o PSA).
- Transformar o tipo de cobrança do Finance and Operations no tipo de cobrança correto do Project Service Automation. Essa transformação já está definida no modelo atualização de valores reais do projeto (o Fin and Ops para o PSA).

### <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra exemplos de mapeamentos da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Finance and Operations para o Project Service Automation.

[![Mapeamento de modelo](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mapeamento de modelo](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)
