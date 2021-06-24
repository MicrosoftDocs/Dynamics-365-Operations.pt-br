---
title: Visão geral de orçamento
description: Quase todas as empresas que usam a funcionalidade Finanças no Microsoft Dynamics 365 Finance precisarão ser capazes de criar relatórios de orçamento versus valores reais. Este artigo explica a configuração mínima necessária para criar orçamentos no Finance and Operations ou carregá-los no programa de um terceiro.
author: panolte
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 60113
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ae13ce4038346cd5b101b5c40fe3b7c5e617fbf
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187931"
---
# <a name="budgeting-overview"></a>Visão geral de orçamento 

[!include [banner](../includes/banner.md)]

Quase todas as empresas que usam a funcionalidade Finanças no Microsoft Dynamics 365 Finance precisarão ser capazes de criar relatórios de orçamento versus valores reais. Este artigo explica a configuração mínima necessária para criar orçamentos no Finance and Operations ou carregá-los no programa de um terceiro.

## <a name="overview"></a>Visão Geral

O orçamento aprovado para uma entidade legal é mantido em um documento que é conhecido como *entrada de registro de orçamento*. As linhas de um documento de entrada de registros de orçamento são conhecidas como entradas da *conta de orçamento* e contêm informações de dimensão financeira, datas e os valores de orçamento aprovado. O documento de entrada do registro de orçamento é integrado às páginas de relatórios financeiros básicos e de consulta onde os valores reais do razão são comparados aos valores de orçamento. 

Há vários métodos para criar entradas de registro de orçamento:

-   Inserir manualmente as informações de documentos na página **Entradas de registro de orçamento**.
-   Usar o modelo do Microsoft Excel que pode ser aberto clicando no botão **Abrir no Excel** na página **Entradas de registro de orçamento**.
-   Use a entidade de dados **Entradas de Conta de Orçamento** no gerenciamento de dados para importar entradas de registro de orçamento. Considere o uso deste método e a ativação do parâmetro **Processamento** **baseado em conjunto** quando precisar importar várias entradas de conta de orçamento para o sistema.
-   Se a empresa usa a funcionalidade Planejamento de orçamento para preparar dados de orçamento, você pode usar o processo periódico **Gerar a entrada de registro de orçamento**.

A entrada de registro de orçamento é considerada concluída quando os saldos do orçamento são atualizados. Na página **Entradas de registro de orçamento**, clique em **Atualizar saldos de orçamentos** para uma entrada de registro de orçamento selecionada ou várias entradas. Após a atualização dos saldos do orçamento, o status da entrada de registro de orçamento muda para **Concluído**. A entrada de registro de orçamento concluído não pode ser reaberta para edições. Então, se os dados de orçamento devem ser ajustados, você precisa criar uma nova entrada de registro de orçamento em vez de corrigir dados na entrada de registro de orçamento concluído.

## <a name="configuration"></a>Configuração
Ao configurar o orçamento, comece na página **Parâmetros de orçamento**. Nessa página, defina o diário de orçamento, a sequência numérica de entradas de registro de orçamento e o comportamento padrão nos espaços de trabalho.

Em seguida, se houver políticas que orientem a aprovação das entradas de registro de orçamento, com base no tipo de orçamento (por exemplo, transferências ou revisões), você deve criar fluxos de trabalho da entrada de registros de orçamento na página **Fluxos de trabalho de orçamento**. Se há cenários em que as transferências devem ser permitidas sem a aprovação do fluxo de trabalho, você pode definir regras de transferência de orçamento para dar suporte a esses cenários. 

Na página **Dimensões de orçamento**, você deve selecionar as dimensões financeiras que são usadas para orçamento, com base nas dimensões que são usadas no plano de contas. Você pode selecionar todas as dimensões financeiras ou um subconjunto delas para orçamento.

Defina um *modelo de orçamento* que corresponde a todos ou alguns dos orçamentos. Você pode usar um único modelo de orçamento para todas as entradas de registro de orçamento. Como alternativa, você pode criar módulos separados que se baseiam no tipo de orçamento, na localização geográfica ou em alguma outra forma de classificação de um orçamento. 

> [!NOTE] 
> Se o controle de orçamento for usado, você poderá associar apenas um modelo de orçamento com um período de tempo específico do ciclo orçamentário. 

Crie *códigos de orçamento* que identifiquem o tipo de transações de orçamento para registrar qualquer fluxo de trabalho relacionado. Os códigos de orçamento podem dar suporte aos seguintes tipos de orçamento:

-   Orçamento original
-   Transferência
-   Revisão
-   Ônus
-   Pré-ônus
-   Orçamento mantido para uso futuro

Os códigos de orçamento permitem ter uma trilha de auditoria de alterações de orçamento aprovadas no decorrer do ciclo orçamentário. Se um fluxo de trabalho estiver associado a um código de orçamento, o fluxo de trabalho será habilitado para todas as entradas de registro de orçamento que usam esse código de orçamento, e as etapas do fluxo de trabalho devem ser concluídas antes de a entrada de registro de orçamento atingir o estágio **Concluída**.  

Você também pode configurar as *regras de transferência de orçamento*. Para usar as regras de transferência de orçamento, selecione **Usar regras para transferências de orçamento** na página **Parâmetros de orçamento**. Quando as regras de transferência de orçamento são usadas, se um usuário cria um documento usando um código de orçamento do tipo **Transferência**, os saldos do orçamento não são atualizados se as regras de transferência de orçamento são violadas. Por exemplo, você pode permitir documentos de transferência de orçamento, onde o orçamento de despesas é transferido entre as contas principais para o departamento de vendas e marketing, mas pode proibir que o orçamento seja transferido de ou para esse departamento, a menos que a aprovação do fluxo de trabalho seja concedida para esse tipo de entrada de conta de orçamento.

Funcionalidade introduzida no Microsoft Dynamics 365 Finance versão 10.0.7 (janeiro de 2020) com capacidade e flexibilidade adicionais para entradas de registro de orçamento. Para habilitar as melhorias, vá para o espaço de trabalho **Gerenciamento de recursos** e selecione **Entradas de registro de orçamento somente para quantidade** e/ou **Entradas de registro de orçamento com tipo de valor como padrão**.

O único recurso de **Entradas de registro de orçamento para quantidade** permite que você lance uma entrada de registro de orçamento com valores de somente quantidade. Por exemplo, você pode lançar uma entrada de orçamento com uma quantidade 32 e preço zero, o que resultará em um valor igual a zero. Você pode usar essa quantidade no contexto de um relatório financeiro para determinar um preço por quantidade. Observe que nenhum relatório ou consulta foi atualizado como parte desse recurso; o recurso só permite que você lance um valor igual a zero.

O recurso **Entradas de registro de orçamento com tipo de valor como padrão** permite que o tipo de valor padrão em uma entrada do registro de orçamento seja um tipo de valor diferente da despesa. A linha de entrada do registro de orçamento agora terá como padrão a despesa quando o tipo de conta principal for despesa; terá como padrão a receita quando o tipo de conta principal for receita e terá despesa como padrão para todos os outros tipos de conta.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Uso de espaços de trabalho e páginas de consulta para rastrear o orçamento versus valores reais
O gerente de orçamento pode analisar o estado atual de um orçamento no espaço de trabalho **Orçamentos e previsões do razão**. As guias **Despesa acima do orçamento** e **Receita abaixo do orçamento** fornecem uma visão rápida das combinações de dimensões financeiras em que os alvos de orçamento não são atendidos ou se aproximam do limite. Você pode personalizar a porcentagem do limite de orçamento e os conjuntos de dimensões financeiras que são usados nestas guias clicando em **Configurar meu espaço de trabalho**. Você pode clicar em **Gerentes de unidade** para ver os trabalhadores responsáveis pelas combinações de dimensões financeiras específicas que estão selecionadas nessas guias. Por exemplo, se você vir que o orçamento das despesas do departamento de operações está ultrapassando o limite de orçamento, procure localizar e contatar o gerente do departamento de operações para abordar o problema. 

> [!NOTE] 
> O campo **Gerente do departamento** na página **Unidades Organizacionais** determina os gerentes que dão suporte a combinações de dimensões financeiras específicas. Clique em **Ver mais** na parte inferior da guia para abrir a página de consulta **Orçamento versus valores reais** para obter mais detalhes sobre valores de orçamento versus valores reais. 

A página de consulta **Valor real versus orçamento** permite analisar nos detalhes do orçamento versus valores reais. Selecione uma linha na página de consulta e clique em **Saldos do período** para ver o orçamento e os valores reais em períodos fiscais. A página **Entradas de conta de orçamento** oferece uma análise dos detalhes do valor de orçamento em entradas de registro de orçamento. A página **Entradas de diário geral** abre as transações do razão que estão incluídas no valor calculado **Valores reais**. 

Uma empresa que está usando a funcionalidade de planejamento de orçamento pode criar e usar *previsões de orçamento* no espaço de trabalho **Orçamentos e previsões do razão**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
