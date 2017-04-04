---
title: "Visão geral de orçamento"
description: "Quase cada empresa que usa a funcionalidade de financeiros no Microsoft Dynamics 365 para operações terá que criar relatórios de orçamento em números reais. Este artigo explica a configuração mínima necessária para criar orçamentos em dynamics 365 para as operações ou débito de um programa de terceiros."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a639e509cf6a3d2f1b850f27481d7b95546522b8
ms.openlocfilehash: b62e14f7c91692ae97bb332b38b0deeb328cc1bd
ms.lasthandoff: 03/31/2017


---

# <a name="budgeting-overview"></a>Visão geral de orçamento

Quase cada empresa que usa a funcionalidade de financeiros no Microsoft Dynamics 365 para operações terá que criar relatórios de orçamento em números reais. Este artigo explica a configuração mínima necessária para criar orçamentos em dynamics 365 para as operações ou débito de um programa de terceiros.

<a name="overview"></a>Visão Geral
--------

O orçamento aprovado para uma entidade legal é mantido em um documento que é conhecido como *entrada de registro de orçamento*. As linhas em um documento de entrada de registros de orçamento são conhecidas como entradas de account* de *budget, e contêm informações de dimensão financeira, datas, e os valores de orçamento aprovado. O documento de entrada do registro de orçamento é integrado com relatórios financeiros e páginas básicos de consulta onde os valores real do razão são comparados aos valores de orçamento. 

Há vários métodos para criar entradas de registro de orçamento em dynamics 365 para operações:

-   Inserir manualmente as informações de documentos na página **Entradas de registro de orçamento**.
-   Usar o modelo do Microsoft Excel que pode ser aberto clicando no botão **Abrir no Excel** na página **Entradas de registro de orçamento**.
-   Use a entidade de dados **Entradas de Conta de Orçamento** no gerenciamento de dados para importar entradas de registro de orçamento. Considere usar o método e ativar ** conjunto baseado ** ** processamento ** parâmetro quando você deve importar várias entradas do orçamento no sistema.
-   Se a empresa usa a funcionalidade Planejamento de orçamento para preparar dados de orçamento, você pode usar o processo periódico **Gerar a entrada de registro de orçamento**.

O registro de orçamento é considerada concluída quando os saldos de orçamento forem atualizados. ** Entradas de registro de orçamento ** na página, clique em atualizar orçamento ** de saldos ** para uma entrada selecionada do registro de orçamento ou em vários lançamentos. Após a atualização dos saldos do orçamento, o status da entrada de registro de orçamento muda para **Concluído**. A entrada de registro de orçamento concluído não pode ser reaberta para edições. Então, se os dados de orçamento devem ser ajustados, você precisa criar uma nova entrada de registro de orçamento em vez de corrigir dados na entrada de registro de orçamento concluído.

## <a name="configuration"></a>Configuração
Ao configurar o orçamento, comece na página **Parâmetros de orçamento**. Nessa página, defina o diário de orçamento, a sequência numérica de entradas de registro de orçamento e o comportamento padrão nos espaços de trabalho.

Em seguida, se houver políticas que orientem a aprovação das entradas de registro de orçamento, com base no tipo de orçamento (por exemplo, transferências ou revisões), você deve criar fluxos de trabalho da entrada de registros de orçamento na página **Fluxos de trabalho de orçamento**. Se há cenários em que as transferências devem ser permitidas sem a aprovação do fluxo de trabalho, você pode definir regras de transferência de orçamento para dar suporte a esses cenários. 

Na página **Dimensões de orçamento**, você deve selecionar as dimensões financeiras que são usadas para orçamento, com base nas dimensões que são usadas no plano de contas. Você pode selecionar todas as dimensões financeiras ou um subconjunto delas para orçamento.

Defina um *that de modelo de *budget corresponde a qualquer ou a alguns orçamentos. Você pode usar um único modelo de orçamento para todas as entradas de registro de orçamento. Como alternativa, você pode criar módulos separados que se baseiam no tipo de orçamento, na localização geográfica ou em alguma outra forma de classificação de um orçamento. 

> [!NOTE] 
> Se controle de orçamento usado, é possível associá-lo apenas um modelo de orçamento com um período de tempo do ciclo orçamentário específico. 

Crie *códigos de orçamento *que identifiquem o tipo de transações de orçamento para registrar qualquer fluxo de trabalho relacionado. Os códigos de orçamento podem dar suporte aos seguintes tipos de orçamento:

-   Orçamento original
-   Transferência
-   Revisão
-   Ônus
-   Pré-ônus
-   Orçamento mantido para uso futuro

Os códigos de orçamento permitem ter uma trilha de auditoria de alterações de orçamento aprovadas no decorrer do ciclo orçamentário. Se um fluxo de trabalho está associado a um código de orçamento, o fluxo de trabalho estará habilitado para todas as entradas de registro de orçamento usando o código de orçamento, as etapas do fluxo de trabalho deve ser concluído antes do registro de orçamento pode alcançar ** ** concluído o estágio.  

Opcionalmente você também pode configurar o rules* de transferência de *budget. Para usar as regras de transferência do orçamento, selecione ** regras de uso para transferências de orçamento ** ** parâmetros de orçamento ** na página. Quando as regras de transferência de orçamento são usadas, se um usuário cria um documento usando um código de orçamento do tipo **Transferência**, os saldos do orçamento não são atualizados se as regras de transferência de orçamento são violadas. Por exemplo, você pode permitir documentos de transferência de orçamento, onde o orçamento de despesas é transferido entre as contas principais para o departamento de vendas e marketing, mas pode proibir que o orçamento seja transferido de ou para esse departamento, a menos que a aprovação do fluxo de trabalho seja concedida para esse tipo de entrada de conta de orçamento.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Uso de espaços de trabalho e páginas de consulta para rastrear o orçamento versus valores reais
O gerente de orçamento pode analisar o estado atual de um orçamento no espaço de trabalho **Orçamentos e previsões do razão**. As guias **Despesa acima do orçamento** e **Receita abaixo do orçamento** fornecem uma visão rápida das combinações de dimensões financeiras em que os alvos de orçamento não são atendidos ou se aproximam do limite. Você pode personalizar a porcentagem do limite de orçamento e os conjuntos de dimensões financeiras que são usados nestas guias clicando em **Configurar meu espaço de trabalho**. Você pode clicar em **Gerentes de unidade** para ver os trabalhadores responsáveis pelas combinações de dimensões financeiras específicas que estão selecionadas nessas guias. Por exemplo, se você vir que o orçamento das despesas do departamento de operações está ultrapassando o limite de orçamento, procure localizar e contatar o gerente do departamento de operações para abordar o problema. 

> [!NOTE] 
> ** Gerente do departamento ** campo ** unidades organizacionais na página ** determina que gerentes suportam específicas combinações de dimensão financeira. Clique em **Ver mais** na parte inferior da guia para abrir a página de consulta **Orçamento versus valores reais** para obter mais detalhes sobre valores de orçamento versus valores reais. 

A página de consulta **Valor real versus orçamento** permite analisar nos detalhes do orçamento versus valores reais. Selecione uma linha na página de consulta e clique em **Saldos do período** para ver o orçamento e os valores reais em períodos fiscais. A página **Entradas de conta de orçamento** oferece uma análise dos detalhes do valor de orçamento em entradas de registro de orçamento. A página **Entradas de diário geral **abre as transações do razão que estão incluídas no valor calculado **Valores reais**. 

Uma empresa que está usando a funcionalidade de planejamento de orçamento pode criar e usar *previsões de orçamento* no espaço de trabalho **Orçamentos e previsões do razão**.


