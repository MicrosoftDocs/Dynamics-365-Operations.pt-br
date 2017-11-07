---
title: "Solução de problemas para orçamento de posição"
description: "Este artigo oferece respostas para as perguntas que você pode ter ao configurar o orçamento de posições. Aborda as perguntas mais frequentes sobre como criar elementos de custos de orçamento, grupos de remuneração, e grades de remuneração."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 421520fcd1b215a19c126ccea51b025977552448
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="position-budgeting-troubleshooting"></a>Solução de problemas para orçamento de posição

[!include[banner](../includes/banner.md)]


Este artigo oferece respostas para as perguntas que você pode ter ao configurar o orçamento de posições. Aborda as perguntas mais frequentes sobre como criar elementos de custos de orçamento, grupos de remuneração, e grades de remuneração. 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>Por que eu não consigo encontrar a página da posição de previsão em Recursos humanos?
---------------------------------------------------------------

As posições de previsão foram movidas para o Orçamento.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>Por que não consigo excluir um elemento de custo de orçamento?
Não é possível excluir um elemento de custo de orçamento que é atribuído a uma posição de previsão. Antes que você possa excluir um elemento de custo de orçamento, deverá removê-lo de todas as posições de previsão. **Dica:** para localizar todas as posições às quais um elemento de custo de orçamento está atribuído, selecione o elemento de custo na página **Elementos de custo do orçamento** e clique em **Atualizar posições**. As posições que usam o elemento de custo são listadas na grade superior.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>Como posso remover um elemento de custo de diversas posições de previsão sem abrir todas elas?
Não é possível remover um elemento de custo. Entretanto, se você alterar as datas de início e fim de modo que fiquem fora do intervalo de datas do ciclo de planejamento de orçamento, o elemento de custo não será mais atribuído às posições de previsão no ciclo de planejamento de orçamento. Para fazer essa alteração, abra o elemento de custo de orçamento e, na Guia Rápida **Cálculo de custo**, clique em **Alterar datas** e altere a data de efetivação ou a data de vencimento. Em seguida, clique em **OK** para atualizar automaticamente todas as posições de previsão às quais o elemento de custo está atribuído. **Dica:** se você usar esse método, saiba que removerá o elemento de custo de orçamento de **todas** as posições de previsão em que as datas de início e de término não estiverem mais no intervalo apropriado. Se esse efeito não é o que você está pretendendo, será necessário abrir cada uma das posição de previsão da qual deseja remover o elemento de custo de orçamento e fazer as alterações manualmente.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>Por que não consigo inserir um valor anual na Guia Rápida Cálculo de custo do elemento de custo de orçamento?
Não é possível inserir um valor anual se houver elementos de custo de orçamento na Guia Rápida **Base de cálculo** porque o sistema requer uma porcentagem para calcular o valor. Para alterar o valor, remova todos os elementos de custo de orçamento da Guia Rápida **Base de cálculo**.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>Por que não consigo alterar o tipo de custo de orçamento de ganho para outro tipo de custo de orçamento?
Alguns elementos de custo de orçamento usam o elemento de custo de ganho como base de cálculo. Para alterar o campo **Tipo de custo de orçamento**, remova o elemento de custo de ganho da Guia Rápida **Base de cálculo** de todos os elementos de custo de orçamento.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>Por que não consigo alterar a data nas linhas de elemento de custo de orçamento de um elemento de custo de orçamento?
Não é possível alterar a data na linha do elemento de custo de orçamento quando um elemento de custo de orçamento é usado para a posição da previsão. Essa limitação ajuda a garantir que as posições de previsão sigam sempre as diretrizes do elemento de custo de orçamento. Para alterar a data, na Guia Rápida **Cálculo do custo**, clique em **Alterar datas** e insira as novas datas. Em seguida, clique em **OK** para atualizar automaticamente as posições de previsão às quais o elemento de custo está atribuído.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>Por que não consigo alterar aos custos de um elemento de custo de orçamento na página Grupo de remuneração?
Você só pode criar e modificar os elementos de custo de orçamento na página **Elementos de custo de orçamento**.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>Por que recebo uma mensagem de erro quando altero as datas de um elemento de custo em uma posição de previsão?
As datas na linha do elemento de custo da posição de previsão devem estar nos seguintes intervalos:

-   As datas de ativação e de aposentadoria da posição.
-   As datas de ativação e de vencimento do elemento de custo de orçamento.
-   As datas de início e fim do ciclo orçamentário associado ao processo de planejamento de orçamento da posição de previsão.





