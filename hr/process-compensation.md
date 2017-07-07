---
title: "Processar remuneração"
description: "O processamento de remuneração permite calcular novos valores de remuneração básica para seus funcionários com base em ajustes de capital, metas de aumento de mérito e desempenho."
author: kherr
manager: AnnBe
ms.date: 07/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 6e30357b0bca8745b69bff19a55828b180c3b829
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="process-compensation"></a>Processar remuneração
O processamento de remuneração permite calcular novos valores de remuneração básica para seus funcionários com base em ajustes de capital, metas de aumento de mérito e desempenho. Esta publicação no blog abrangerá o fluxo básico de processamento de remuneração para planos de compensação fixa sem ter em conta o desempenho.

## <a name="plan-the-new-compensation-amounts-and-budgets"></a>Planeje os novos montantes e orçamentos de remuneração
Para dar aos seus funcionários um aumento de mérito, você deve configurar um orçamento de aumento fixo para cada um de seus departamentos: Gerenciamento de remuneração > Links > Metas de aumento de mérito. (Alternativamente, você pode abrir este formulário através do Departamento: Organização > Departamentos.) Aqui você pode especificar se os funcionários de um determinado sindicato ou local devem obter uma porcentagem diferente de aumento. Os campos **Orçamento** e **Moeda** são informativos e podem ser usados ​​para anotar um valor em moeda para o orçamento.

## <a name="set-up-the-compensation-process"></a>Configurar o processo de remuneração
Um evento de processo permite que você especifique os parâmetros para o processamento de compensação. Isso inclui o período da data a ser avaliado para determinar os montantes da remuneração.  e a data em que os novos montantes de remuneração devem entrar em vigor.

Opcionalmente, você pode incluir uma data de contratação fixa paga, se qualquer um de seus planos de remuneração fixos usar uma regra de contrato de percentagem. Para esses planos, qualquer pessoa que tenha sido contratada após a data de início do ciclo e antes da data de contratação fixa paga pagará 100% de seu mérito calculado ou aumento geral. Qualquer pessoa que tenha sido contratada após a data de contratação fixa paga e antes da data final do ciclo receberá uma parte do seu aumento calculado com base em quantos dias fora do total dos dias do ciclo em que estava empregada. Por exemplo, se o nosso ciclo for realizado de 1 de janeiro a 31 de dezembro e nós tivermos uma data fixa de pagamento de 1 de abril, um empregado contratado em março receberá o aumento calculado total enquanto um empregado contratado em 1 de julho receberá aproximadamente metade do aumento calculado.

A data **Ponto-em-horas** do evento de processo é usado apenas para processar determinados planos de compensação variável e não será abordada nesta publicação no blog. O **Prazo final da revisão** é o prazo para fazer todas as recomendações para que os novos valores de remuneração possam ser carregados no registro do funcionário. A data da revisão é apenas informativa.

Uma vez que os parâmetros do evento do processo foram salvos, você pode clicar no botão **Configuração** para indicar os planos a serem incluídos nesse processo e quais ações de remuneração fixas devem ser tomadas para cada plano.

Clique no botão **Adicionar** na aba superior para adicionar um plano de remuneração fixa ao evento de processo. As colunas **Usar outro aproveitamento**, **Fator de aproveitamento**, e **Descrição do aproveitamento** são usadas apenas para planos de remuneração variável e não são abordadas neste tópico.

Salve o registro, clique no botão **Adicionar** na aba inferior para adicionar ações de remuneração fixa para ao plano selecionado. Use a opção Habilitar recomendação se desejar inserir um valor diferente do aumento de diretriz calculado para a ação. Se você deseja que uma ação seja calculada com base no resultado da ação anterior para vincular várias ações de remuneração, marque a opção Usar resultado anterior. Ações de remuneração fixa são tipos de lógica de remuneração para os quais você pode dar nomes descritivos. Para os planos Grade e Band, você só pode adicionar ações de remuneração fixa que são dos seguintes tipos:

| Tipo de ação de remuneração fixa | Funcionalidade                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Capital próprio                        | As ações de capital próprio comparam a taxa de remuneração do funcionário a partir da data final do ciclo com o ponto de referência mais baixo para o nível indicado no trabalho do funcionário. Se a taxa de remuneração do funcionário for inferior ao ponto de referência mínimo, o aumento necessário para que o funcionário atinja o ponto mínimo no intervalo será calculado.                                                                                |
| Mérito                         | As ações de mérito calcularão um aumento com base na taxa de pagamento do funcionário na data final do ciclo e na porcentagem de aumento encontrada no orçamento de aumento fixo para o departamento, sindicato e local do funcionário.                                                                                                                                                                                         |
| Geral                       | As ações gerais calcularão um aumento com base em uma porcentagem ou darão aos funcionários um valor fixo. Isso é determinado com base nas configurações de remuneração fixa na guia Geral.                                                                                                                                                                                                                        |
| Promoção                     | As ações de promoção fornecem um local nomeado onde você pode atribuir o aumento. Por isso, marque a opção **Habilitar recomendação** para que você possa inserir uma recomendação para os funcionários que receberão promoções.  Os funcionários sem um aumento recomendado não terão a ação de promoção adicionada aos seus registros de remuneração fixa.                                                                       |
| Outra alteração de nível            | No exemplo anterior, Demotion é o nome da nossa ação de remuneração fixa com um tipo de alteração de outros níveis. Isso gera um aumento de orientação 0 (mudança zero) para que você possa inserir um valor de recomendação para ajustar a taxa de pagamento do funcionário. (Certifique-se de marcar a opção **Habilitar a recomendação**.) Funcionários sem uma recomendação não terão esta ação adicionada aos registros de remuneração fixa. |

Você só pode adicionar ações de remuneração fixa com um tipo de plano passo a passo.

| Tipo de ação de remuneração fixa | Funcionalidade                                                                                                                                                                                           |
|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Etapa                           | Na guia Geral, indique se esta ação de etapa deve mover os funcionários para 0 etapas, 1 etapa ou duas etapas.                                                                                  |
|                                | **0 etapas** - O funcionário receberá a taxa de pagamento para a etapa atual em que está.                                                                                                                      |
|                                | **1 etapa** - O sistema verificará se o funcionário já está no último ponto de referência para o seu nível.                                                                                             |
|                                | **2 etapas** - O sistema moverá o funcionário em duas etapas em seu nível atual. O sistema só pode mover o funcionário uma ou zero etapas se atingir o último ponto de referência para o seu nível. |

## <a name="run-the-compensation-process"></a>Execute o processo de remuneração
Após o evento de processo ter sido configurado com os campos, planos e ações necessários da data, você pode clicar em **Executar processo** na página de evento de processo. Isso abre a caixa de diálogo Executar eventos de processo de remuneração. Nessa caixa de diálogo, clique na opção **Exibir resultados de processamento** para ver como os valores da remuneração foram calculados para cada funcionário. Clicar em **OK** executará o processo de remuneração para todos os funcionários presentes nos planos de remuneração selecionados, na data final do ciclo.

## <a name="view-the-process-results"></a>Exibir os resultados do processo
Para exibir os resultados do processo, abra a página **Resultados do processo**. Um novo evento de remuneração será criado sempre que o evento de processo for executado. Desta forma, você pode executar testes, fazer ajustes e executar o evento de compensação várias vezes para ver como várias mudanças afetam a remuneração de funcionário.

A página de resultados do processo contém informações sobre a execução do processo, incluindo quando a execução ocorreu, o usuário que executou o processo e se houve algum erro quando o processo foi executado. Você também pode marcar a opção **Bloqueado** para desabilitar o botão **Carregar remuneração** e impedir que alguém carregue eventos de remuneração em registros de funcionário. Clicar no botão **Resultados de funcionários** exibirá a lista dos funcionários incluídos na execução.

Os resultados do funcionário mostram informações sobre o processo, bem como quaisquer ações de remuneração realizadas no processo. A seção de remuneração fixa conterá um registro para cada ação incluída no evento do processo para o plano de remuneração. As colunas Diretriz atual e Recomendação exibirão mais informações para a ação selecionada na seção de remuneração fixa. Se a ação tiver as recomendações ativadas marcadas, os campos da recomendação serão editáveis. Isso permitirá que você ajuste manualmente os valores para o funcionário. Nota: se você marcou Usar resultado anterior para a ação no evento de processo, você deve atualizar manualmente os valores para qualquer ação dependente.

Uma vez que os valores de remuneração tiverem sido revisados ​​para um funcionário e quaisquer ajustes nos valores recomendados tiverem sido feitos, você poderá alterar o **Status** na linha **Evento de funcionário** para indicar se o evento foi aprovado ou deve ser ignorado. Opcionalmente, você pode apagar todas as alterações feitas na recomendação do funcionário clicando no botão **Recalcular**. Isso marcará o evento de funcionário existente com um status de Ignorar e criará um novo evento de funcionário com valores recalculados.

## <a name="loading-approved-compensation-changes"></a>Carregando alterações de remuneração aprovadas
Uma vez que um ou mais eventos de funcionário tiverem seu status atualizado para Aprovado, eles podem ser carregados nos registros de remuneração fixa dos funcionários. Isso pode ser feito selecionando cada evento de funcionário um por vez e clicando no botão Carregar remuneração de funcionário na página de resultados do funcionário, ou clicando em **Carregar remuneração** na página de resultados do processo para carregar todos os eventos de funcionário aprovados de uma só vez.

Clicar em **OK** na caixa de diálogo **Carregar remuneração** adicionará as linhas de ação de compensação não-zero à página **Remuneração fixa do funcionário**.

