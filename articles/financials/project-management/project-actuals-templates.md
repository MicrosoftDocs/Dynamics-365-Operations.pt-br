---
title: "Sincronize valores reais do projeto do Project Service Automation diretamente para o diário de integração do projeto para lançamento no Finance and Operations."
description: "Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar valores reais do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: pt-br
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Sincronize valores reais do projeto do Project Service Automation diretamente para o diário de integração do projeto para lançamento no Finance and Operations.

Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar valores reais do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations.

O modelo sincroniza transações do Project Service Automation para uma tabela de preparo no Finance and Operations. Após a sincronização ser concluída, você deverá importar da tabela de preparo para o diário de integração.

> [!NOTE]
> A integração de valores reais do projeto está disponível no Dynamics 365 for Finance and Operations versão 8.01.

> [!NOTE]
> Se estiver inserindo valores de impostos em transações de tempo ou de despesas no Project Service Automation, instale a atualização 7 do Project Service Automation. Se essa atualização não estiver instalada, os valores reais de impostos não serão vinculados aos valores reais associados de tempo ou de despesas e não serão sincronizadas para o Finance and Operations. Entre em contato com o suporte para obter mais informações.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Fluxo de dados do Project Service Automation para o Finance and Operations

A solução de integração do Project Service Automation para o Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre valores reais do projeto do Project Service Automation para o Finance and Operations.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.

[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)


## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e as tarefas subjacentes são usados para sincronizar valores reais do projeto do Project Service Automation para o Finance and Operations:

-  **Nome do modelo na Integração de dados:** valores reais do projeto (do PSA para o Fin and Ops)

-  **Nome das tarefas no projeto:** 
    - Reais 
    - TransactionConnections

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations                                      |
|---------------------------------|-------------------------------------------------------------|
| Reais                         | Entidade de integração para valores reais do projeto                      |
| Conexões com transações         | Entidade de integração para relacionamentos de transações do projeto    |

## <a name="entity-flow"></a>Fluxo de entidades

Os valores reais do projeto são gerenciados no Project Service Automation e são sincronizados para o Finance and Operations para o diário de integração do projeto. A contabilidade será aplicada com base nas dimensões financeiras padrão e na configuração de lançamento.

## <a name="preconditions"></a>Precondições

Antes da sincronização de valores reais, você deve configurar parâmetros de integração do Project Service Automation e sincronizar projetos, tarefas de projetos e categorias de transação de despesa do projeto.

## <a name="power-query"></a>Power Query

Você deve usar o Microsoft Power Query no modelo de valores reais do projeto para:
- Transformar o **tipo de transação** do Project Service Automation no **tipo de transação** correto no Finance and Operations. O modelo de valores reais do projeto (do PSA para o Fin and Ops) já tem essa transformação definida.
- Transformar o **tipo de cobrança** do Project Service Automation no **tipo de cobrança** correto no Finance and Operations. O modelo de valores reais do projeto (do PSA para o Fin and Ops) já tem essa transformação definida. O tipo de cobrança é mapeado para a **propriedade de linha** com base na configuração no formulário de parâmetros de integração do Dynamics 365 for Project Service Automation.
- Filtre para **Unidades organizacionais de recurso** específicas que devem ser sincronizadas com esse modelo.
- Se **tempo intercompanhia ou valores reais de despesas intercompanhia** forem sincronizados para o Finance and Operations, você deverá transformar a **unidade organizacional de contrato** na **entidade legal** correta no Finance and Operations. O modelo de valores reais do projeto (do PSA para o Fin and Ops) tem uma coluna condicional definida com base em dados de demonstração. Você deve atualizar a última coluna de condição inserida para as entidades legais corretas. A falha nessa ação poderá resultar em um erro de integração ou em transações reais incorretas importadas para o Finance and Operations.
- Se **tempo intercompanhia ou valores reais de despesas intercompanhia** não forem sincronizados para o Finance and Operations, você deverá excluir a última coluna de condição inserida do modelo. A falha nessa ação poderá resultar em um erro de integração ou em transações reais incorretas importadas para o Finance and Operations.

### <a name="contract-organizational-unit"></a>Unidade organizacional de contrato
Para atualizar a coluna de condição inserida no modelo, clique na seta **Mapa** para abrir o mapeamento. Selecione para abrir a Filtragem e consulta avançada.
- Se você estiver usando o modelo de valores reais do Microsoft Project padrão (do PSA para o Fin and Ops), selecione o lasat **Condição inserida** na seção **Etapas aplicadas**. Na entrada **Função**, substitua **USSI** pelo nome da **Entidade legal** que deve ser usado com a integração. Adicione condições adicionais conforme necessário à entrada **Função** e atualize a condição **else** do **USMF** para a **Entidade legal**  correta.
- Se estiver criando um novo modelo, você deverá adicionar essa coluna para dar suporte a tempo e despesas intercompanhia. Selecione **Adicionar coluna condicional** e atribua um nome à coluna, como LegalEntity. Insira a condição da coluna em que, se msdyn_contractorganizationalunitid.msdyn_name for <organizational unit>, então <enter the Legal entity>; caso contrário, o valor será nulo.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mapeamento de modelo](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table"></a>Importar da tabela de preparo

A importação do processo periódico da tabela de preparo deve ser executada após a sincronização de valores reais do Project Service Automation para o Finance and Operations. Este processo importará as transações do projeto da tabela de preparo para o diário de integração do Project Service Automation, em que a contabilidade é aplicada e as transações importadas podem ser lançadas. É recomendável executar esse processo em modo de lote e, opcionalmente, configurar para executar como um lote recorrente.

## <a name="update-actuals"></a>Atualizar valores reais

O seguinte modelo e as tarefas subjacentes são usados para sincronizar o número do comprovante e os impostos para transações de projeto lançadas do Finance and Operations para o Project Service Automation:

-  **Nome do modelo na Integração de dados:** atualização de valores reais do projeto (Fin and Ops para PSA)
-  **Nome das tarefas no projeto:** 
     - Reais 
     - TransactionConnections

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations                                         | Project Service Automation        |
|----------------------------------------------------------------|-----------------------------------|
| Entidade de integração para valores reais do projeto                         | Reais                           |
| Entidade de integração para relacionamentos de transações do projeto       | Conexões com transações           |

## <a name="entity-flow"></a>Fluxo de entidades

Os valores reais do projeto são gerenciados no Project Service Automation e são sincronizados para o Finance and Operations para o diário de integração do projeto. Após lançados depois no Finance and Operations, os valores reais são atualizados no Project Service Automation com o número de comprovante do Finance and Operations. Se os impostos tiverem sido adicionados no Finance and Operations, os novos valores reais de impostos serão criados no Project Service Automation.

## <a name="power-query"></a>Power Query

Você deve usar o Microsoft Power Query no modelo de atualização de valores reais do projeto para:
- Transformar o **tipo de transação** do Finance and Operations no **tipo de transação** correto no Project Service Automation. O modelo de atualização de valores reais do projeto (Fin and Ops para PSA) já tem essa transformação definida.
- Transformar o **tipo de cobrança** do Finance and Operations no **tipo de cobrança** correto no Project Service Automation. O modelo de atualização de valores reais do projeto (Fin and Ops para PSA) já tem essa transformação definida.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra exemplos de mapeamentos da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Finance and Operations para o Project Service Automation.

[![Mapeamento de modelo](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mapeamento de modelo](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)




