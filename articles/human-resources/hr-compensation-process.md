---
title: Processar remuneração
description: O processamento de remuneração permite calcular novos valores de remuneração básica para seus funcionários com base em ajustes de capital, metas de aumento de mérito e desempenho.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 7c72f866886f320d8a7fa22d6ccfa7e43284b5bf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071404"
---
# <a name="process-compensation"></a>Processar remuneração


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O processamento de remuneração permite calcular novos valores de remuneração básica para seus funcionários com base em ajustes de capital, metas de aumento de mérito e desempenho. Este tópico aborda o fluxo básico de processamento de remuneração para planos de compensação fixa sem ter em conta o desempenho de um funcionário.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Planeje os novos montantes e orçamentos de remuneração
Para dar aos funcionários um aumento de mérito, você deve configurar um orçamento de aumento fixo para cada um dos Departamentos: **Gerenciamento de remuneração** > **Links** > **Metas de aumento de mérito**. (Como alternativa, você pode abrir esta página por meio do Departamento: **Organização** > **Departamentos**). Você pode especificar se os funcionários de certo sindicato ou local devem obter uma porcentagem diferente de aumento. Os campos **Orçamento** e **Moeda** são informativos e podem ser usados ​​para anotar um valor em moeda para o orçamento.

## <a name="set-up-the-compensation-process"></a>Configurar o processo de remuneração
Na página **Processos de remuneração**, você pode especificar os parâmetros para o processamento de remuneração. Isso inclui o período de datas de avaliação para determinar os valores de remuneração e a data em que os valores da nova remuneração deverão entrar em vigor.

Opcionalmente, você poderá incluir uma **Data de contratação proporcional para pagamento fixo** se um de seus planos de remuneração fixa usar uma regra de contrato de porcentagem. Para esses planos, qualquer pessoa contratada após a **Data de início do ciclo** e antes da **Data de contratação proporcional para pagamento fixo** receberá 100% de mérito calculado ou aumento geral. Qualquer pessoa contratada após a **Data de contratação proporcional para pagamento fixo** e antes da **Data final do ciclo** receberá uma parte do aumento calculado com base em quantos dias fora do total de dias do ciclo ele foi empregado. Por exemplo, se o seu ciclo for realizado de 1º de janeiro a 31 de dezembro e houver uma data de contratação proporcional para pagamento fixo de 1º de abril, um funcionário contratado em março receberá o aumento calculado total enquanto um funcionário contratado em 1º de julho receberá aproximadamente metade do aumento calculado.

A data **Pontual** do evento de processo é usado apenas para processar determinados planos de compensação variável e não será abordada aqui. O **Prazo final da revisão** é o prazo para fazer todas as recomendações para que os novos valores de remuneração possam ser carregados no registro do funcionário. A data da revisão é apenas informativa.

Depois que os parâmetros do evento do processo forem salvos, você poderá clicar no botão **Configuração** para selecionar os planos a serem incluídos quando o processo for executado e quais ações de remuneração fixa devem ser tomadas para cada plano.

Clique no botão **Adicionar** na guia **Planos** para adicionar um plano de remuneração ao evento de processo. As colunas **Usar outro aproveitamento**, **Fator de aproveitamento**, e **Descrição do aproveitamento** são usadas apenas para planos de remuneração variável e não serão abordadas neste tópico.

Salve o registro e clique no botão **Adicionar** na guia **Ações** para adicionar ações de remuneração fixa ao plano selecionado. Use a opção **Habilitar recomendação** para inserir um valor diferente do aumento de diretriz calculado para a ação. Para calcular uma ação que se baseie no resultado da ação anterior para vincular várias ações de remuneração, marque a opção **Usar resultado anterior**. As ações de remuneração fixa são tipos de lógica de remuneração às quais você pode dar nomes descritivos. Para os planos **Grade** e **Band**, você só pode adicionar ações de remuneração fixa que são dos seguintes tipos:

| Tipo de ação de remuneração fixa | Funcionalidade                  |
|-------------------------------|-------------------------------------------------------------------------|
| Capital próprio                        | As ações de capital próprio comparam a taxa de remuneração do funcionário a partir da data final do ciclo com o ponto de referência mais baixo para o nível indicado no trabalho do funcionário. Se a taxa de remuneração do funcionário for inferior ao ponto de referência mínimo, o aumento necessário para que o funcionário atinja o ponto mínimo no intervalo será calculado.                                                                                |
| Mérito                         | As ações de mérito calcularão um aumento com base na taxa de pagamento do funcionário na data final do ciclo e na porcentagem de aumento encontrada no orçamento de aumento fixo para o departamento, sindicato e local do funcionário.                                                                                                                                                                                         |
| Geral                       | As ações gerais calcularão um aumento com base em uma porcentagem ou darão aos funcionários um valor fixo. Isso é determinado com base nas configurações de **Remuneração fixa** na guia **Geral**.                                                                                                                                                                                                                        |
| Promoção                     | As ações promocionais fornecem um local nomeado em que você pode oferecer aumentos de prêmio. Marque a opção **Habilitar recomendação** para inserir uma recomendação para funcionários que receberão promoções.  Os funcionários sem um aumento recomendado não terão a ação **Promoção** adicionada aos seus registros de remuneração fixa.                                                                       |
| Outra alteração de nível            | No exemplo anterior, **Rebaixamento** é o nome da ação **Remuneração fixa** com um tipo **Outra alteração de nível**. Isso gera um aumento de orientação 0 (mudança zero) para que você possa inserir um valor de recomendação para ajustar a taxa de pagamento do funcionário. (Selecione a opção **Habilitar recomendação**). Os funcionários sem uma recomendação não terão essa ação adicionada aos registros de remuneração fixa. |

Você só pode adicionar ações **Remuneração fixa** com um tipo de plano Passo a Passo.

| Tipo de ação de remuneração fixa | Funcionalidade                |
|--------------------------------|------------------------------|
| Etapa                           | Na guia **Geral**, indique se esta ação de etapa deve mover os funcionários para 0 etapa, 1 etapa ou 2 etapas.                                                                                  |
|                                | **0 etapas** - O funcionário receberá a taxa de pagamento para a etapa atual em que está.                                                                                                                      |
|                                | **1 etapa** - O sistema verificará se o funcionário já está no último ponto de referência para o seu nível.                                                                                             |
|                                | **2 etapas** - O funcionário avançará duas etapas em seu nível atual. O funcionário só pode mover uma ou zero etapas se atingir o último ponto de referência para o seu nível. |

## <a name="run-the-compensation-process"></a>Execute o processo de remuneração
Após o evento de processo ter sido configurado com os campos, planos e ações de data necessários, clique em **Executar processo** na página **Evento de processo**. Isso abrirá caixa de diálogo **Executar eventos de processo de remuneração**. Clique na opção **Exibir resultados de processamento** para ver como os valores da remuneração foram calculados para cada funcionário. Clicar em **OK** executará o processo de remuneração para todos os funcionários presentes nos planos de remuneração selecionados, na data final do ciclo.

## <a name="view-the-process-results"></a>Exibir os resultados do processo
Para exibir os resultados do processo, abra a página **Resultados do processo**. Um novo evento de remuneração será criado sempre que o evento de processo for executado. Isso permite executar avaliações, fazer ajustes e executar o evento de remuneração várias vezes para ver como várias mudanças afetam a remuneração do funcionário.

A página **Resultados do processo** contém informações sobre a execução do processo, incluindo quando a execução ocorreu, o usuário que executou o processo e se houve algum erro quando o processo foi executado. Selecione a opção **Bloqueado** para desabilitar o botão **Carregar remuneração** e impedir que alguém carregue eventos de remuneração em registros de funcionário. Clicar no botão **Resultados de funcionários** exibirá a lista dos funcionários incluídos na execução.

A opção **Resultados do funcionário** mostra informações sobre o processo, além de quaisquer ações de remuneração realizadas no processo. A seção **Remuneração fixa** conterá um registro de cada ação incluída no evento de processo do plano de remuneração. As colunas **Diretriz Atual** e **Recomendação** exibirão mais informações sobre a ação selecionada na seção **Remuneração fixa**. Se **Habilitar recomendações** tiver sido marcado para a ação, os campos de **Recomendação** serão editáveis. Isso permitirá que você ajuste manualmente os valores para o funcionário. Observe que, se você tiver marcado **Usar resultado anterior** para a ação no evento de processo, deverá atualizar manualmente os valores de qualquer ação dependente.

Quando os valores de remuneração tiverem sido revisados ​​para um funcionário e quaisquer ajustes nos valores recomendados tiverem sido feitos, você poderá alterar o **Status** na linha **Evento de funcionário** para indicar se o evento foi aprovado ou se deve ser ignorado. Opcionalmente, você pode apagar todas as alterações feitas na recomendação do funcionário clicando no botão **Recalcular**. Isso marcará o evento de funcionário existente com um status de Ignorar e criará um novo evento de funcionário com valores recalculados.

## <a name="loading-approved-compensation-changes"></a>Carregando alterações de remuneração aprovadas
Quando um ou mais eventos de funcionário tiverem o status atualizado para **Aprovado**, eles poderão ser carregados nos registros de remuneração fixa dos funcionários. Faça isso selecionando cada evento de funcionário por vez e clicando no botão **Carregar remuneração de funcionário** na página **Resultados do funcionário** ou clicando em **Carregar remuneração** na página **Resultados do processo** para carregar todos os eventos de funcionário aprovados de uma só vez.

Clicar em **OK** na caixa de diálogo **Carregar remuneração** adicionará as linhas de ação de compensação não-zero à página **Remuneração fixa do funcionário**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
