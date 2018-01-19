---
title: "Processar remuneração"
description: "O processamento de remuneração permite calcular novos valores de remuneração básica para seus funcionários com base em ajustes de capital, metas de aumento de mérito e desempenho."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 671bdea9e58309742424b098abb78522c2a6155e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="process-compensation"></a>Processar remuneração
O processamento de remuneração permite calcular novos valores de remuneração básica para seus funcionários com base em ajustes de capital, metas de aumento de mérito e desempenho. Este tópico aborda o fluxo básico de processamento de remuneração para planos de compensação fixa sem ter em conta o desempenho de um funcionário.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Planeje os novos montantes e orçamentos de remuneração
Para dar aos seus funcionários um aumento de mérito, você deve configurar um orçamento de aumento fixo para cada um de seus Departamentos: Gerenciamento de remuneração > Links > Metas de aumento de mérito. (Como alternativa, você pode abrir este formulário por meio do Departamento: Organização > Departamentos). Aqui você pode especificar se os funcionários de um determinado sindicato ou local devem obter uma porcentagem diferente de aumento. Os campos **Orçamento** e **Moeda** são informativos e podem ser usados ​​para anotar um valor em moeda para o orçamento.

## <a name="set-up-the-compensation-process"></a>Configurar o processo de remuneração
Um evento de processo permite que você especifique os parâmetros para o processamento de compensação. Isso inclui o período de datas de avaliação para determinar os valores de remuneração e a data em que os valores da nova remuneração deverão entrar em vigor.

Opcionalmente, você pode incluir uma data de contratação fixa paga, se qualquer um de seus planos de remuneração fixos usar uma regra de contrato de percentagem. Para esses planos, qualquer pessoa que tenha sido contratada após a data de início do ciclo e antes da data de contratação fixa paga pagará 100% de seu mérito calculado ou aumento geral. Qualquer pessoa que tenha sido contratada após a data de contratação fixa paga e antes da data final do ciclo receberá uma parte do seu aumento calculado com base em quantos dias fora do total dos dias do ciclo em que estava empregada. Por exemplo, se o nosso ciclo for realizado de 1º de janeiro a 31 de dezembro e nós tivermos uma data fixa de pagamento de 1º de abril, um empregado contratado em março receberá o aumento calculado total enquanto um empregado contratado em 1º de julho receberá aproximadamente metade do aumento calculado.

A data **Pontual** do evento de processo é usado apenas para processar determinados planos de compensação variável e não será abordada aqui. O **Prazo final da revisão** é o prazo para fazer todas as recomendações para que os novos valores de remuneração possam ser carregados no registro do funcionário. A data da revisão é apenas informativa.

Depois que os parâmetros do evento do processo tiverem sido salvos, você poderá clicar no botão **Configuração** para indicar os planos a serem incluídos nesse processo e quais ações de remuneração fixas devem ser tomadas para cada plano.

Clique no botão **Adicionar** na aba **Planos** para adicionar um plano de remuneração ao evento de processo. As colunas **Usar outro aproveitamento**, **Fator de aproveitamento**, e **Descrição do aproveitamento** são usadas apenas para planos de remuneração variável e não serão abordadas neste tópico.

Salve o registro e então clique no botão **Adicionar** na aba **Ações** para adicionar ações de remuneração fixa ao plano selecionado. Use a opção **Habilitar recomendação** para inserir um valor diferente do aumento de diretriz calculado para a ação. Para calcular uma ação com base no resultado da ação anterior para vincular várias ações de remuneração, marque a opção **Usar resultado anterior**. As ações de remuneração fixa são tipos de lógica de remuneração para os quais você pode dar nomes descritivos. Para os planos Grade e Band, você só pode adicionar ações de remuneração fixa que são dos seguintes tipos:

| Tipo de ação de remuneração fixa | Funcionalidade                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Capital próprio                        | As ações de capital próprio comparam a taxa de remuneração do funcionário a partir da data final do ciclo com o ponto de referência mais baixo para o nível indicado no trabalho do funcionário. Se a taxa de remuneração do funcionário for inferior ao ponto de referência mínimo, o aumento necessário para que o funcionário atinja o ponto mínimo no intervalo será calculado.                                                                                |
| Mérito                         | As ações de mérito calcularão um aumento com base na taxa de pagamento do funcionário na data final do ciclo e na porcentagem de aumento encontrada no orçamento de aumento fixo para o departamento, sindicato e local do funcionário.                                                                                                                                                                                         |
| Geral                       | As ações gerais calcularão um aumento com base em uma porcentagem ou darão aos funcionários um valor fixo. Isso é determinado com base nas configurações de **Remuneração fixa** na guia **Geral**.                                                                                                                                                                                                                        |
| Promoção                     | As ações de promoção fornecem um local nomeado onde você pode atribuir o aumento. Por isso, marque a opção **Habilitar recomendação** para que você possa inserir uma recomendação para os funcionários que receberão promoções.  Os funcionários sem um aumento recomendado não terão a ação **Promoção** adicionada aos seus registros de remuneração fixa.                                                                       |
| Outra alteração de nível            | No exemplo anterior, **Rebaixamento** é o nome da nossa ação **Remuneração fixa** com um tipo **Outra alteração de nível**. Isso gera um aumento de orientação 0 (mudança zero) para que você possa inserir um valor de recomendação para ajustar a taxa de pagamento do funcionário. (Marque a opção **Habilitar a recomendação**). Os funcionários sem uma recomendação não terão essa ação adicionada aos seus registros de remuneração fixa. |

Você só pode adicionar ações **Remuneração fixa** com um tipo de plano Passo a Passo.

| Tipo de ação de remuneração fixa | Funcionalidade                                                                                                                                                                                           |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Etapa                           | Na guia Geral, indique se esta ação de etapa deve mover os funcionários para 0 etapas, 1 etapa ou duas etapas.                                                                                  |
|                                | **0 etapas** - O funcionário receberá a taxa de pagamento para a etapa atual em que está.                                                                                                                      |
|                                | **1 etapa** - O sistema verificará se o funcionário já está no último ponto de referência para o seu nível.                                                                                             |
|                                | **2 etapas** - O sistema moverá o funcionário em duas etapas em seu nível atual. O sistema só pode mover o funcionário uma ou zero etapas se atingir o último ponto de referência para o seu nível. |

## <a name="run-the-compensation-process"></a>Execute o processo de remuneração
Após o evento de processo ter sido configurado com os campos, planos e ações de data necessários, você poderá clicar em **Executar processo** na página **Evento de processo**. Isso abre o diálogo **Executar eventos de processo de remuneração**. Nessa caixa de diálogo, clique na opção **Exibir resultados de processamento** para ver como os valores da remuneração foram calculados para cada funcionário. Clicar em **OK** executará o processo de remuneração para todos os funcionários presentes nos planos de remuneração selecionados, na data final do ciclo.

## <a name="view-the-process-results"></a>Exibir os resultados do processo
Para exibir os resultados do processo, abra a página **Resultados do processo**. Um novo evento de remuneração será criado sempre que o evento de processo for executado. Desta forma, você pode executar testes, fazer ajustes e executar o evento de compensação várias vezes para ver como várias mudanças afetam a remuneração de funcionário.

A página **Resultados do processo** contém informações sobre a execução do processo, incluindo quando a execução ocorreu, o usuário que executou o processo e se houve algum erro quando o processo foi executado. Você também pode marcar a opção **Bloqueado** para desabilitar o botão **Carregar remuneração** e impedir que alguém carregue eventos de remuneração em registros de funcionário. Clicar no botão **Resultados de funcionários** exibirá a lista dos funcionários incluídos na execução.

A opção **Resultados do funcionário** mostra informações sobre o processo, além de quaisquer ações de remuneração realizadas no processo. A seção **Remuneração fixa** conterá um registro de cada ação incluída no evento de processo do plano de remuneração. As colunas **Diretriz Atual** e **Recomendação** exibirão mais informações sobre a ação selecionada na seção **Remuneração fixa**. Se **Habilitar recomendações** tiver sido marcado para a ação, os campos de Recomendação serão editáveis. Isso permitirá que você ajuste manualmente os valores para o funcionário. Observe que, se você tiver marcado **Usar resultado anterior** para a ação no evento de processo, deverá atualizar manualmente os valores de qualquer ação dependente.

Quando os valores de remuneração tiverem sido revisados ​​para um funcionário e quaisquer ajustes nos valores recomendados tiverem sido feitos, você poderá alterar o **Status** na linha **Evento de funcionário** para indicar se o evento foi aprovado ou se deve ser ignorado. Opcionalmente, você pode apagar todas as alterações feitas na recomendação do funcionário clicando no botão **Recalcular**. Isso marcará o evento de funcionário existente com um status de Ignorar e criará um novo evento de funcionário com valores recalculados.

## <a name="loading-approved-compensation-changes"></a>Carregando alterações de remuneração aprovadas
Quando um ou mais eventos de funcionário tiverem seu status atualizado para Aprovado, eles podem ser carregados nos registros de remuneração fixa dos funcionários. Faça isso selecionando cada evento de funcionário por vez e clicando no botão **Carregar remuneração de funcionário** na página **Resultados do funcionário** ou clicando em **Carregar remuneração** na página **Resultados do processo** para carregar todos os eventos de funcionário aprovados de uma só vez.

Clicar em **OK** na caixa de diálogo **Carregar remuneração** adicionará as linhas de ação de compensação não-zero à página **Remuneração fixa do funcionário**.

