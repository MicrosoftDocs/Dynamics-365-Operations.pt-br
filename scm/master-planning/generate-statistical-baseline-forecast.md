---
title: "Gerar uma previsão estatística"
description: "Este artigo fornece informações sobre os parâmetros e filtros usados no cálculo da previsão de demanda."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c0c918b94fe96d123bb6c25c42fe168a026cd8a9
ms.lasthandoff: 03/31/2017


---

# <a name="generate-a-statistical-baseline-forecast"></a>Gerar uma previsão estatística

Este artigo fornece informações sobre os parâmetros e filtros usados no cálculo da previsão de demanda. 

Ao criar uma previsão de baseline, primeiro você deve especificar os parâmetros e os filtros usados no cálculo. Por exemplo, você pode criar uma previsão de baseline que estima a demanda baseada nos dados de transação do ano passado para uma empresa específica, para o mês de entrada e para um grupo de itens selecionado. 

Gerar uma previsão de demanda, vá ** a previsão de demanda mestre &gt; de previsão &gt; de &gt; planejamento gera a previsão estatística **. 

A classificação de previsão pode ser selecionada no momento da geração da previsão. Os valores disponíveis são: Dia, Semana e Mês. 

O número de classificações para as quais serão geradas uma previsão é definido no campo** Horizonte de previsão**. 

Quando a estratégia de previsão é definida para **Copiar sobre demanda histórica**, o fim do horizonte histórico é ignorado. O sistema copia o número da especificada em ** horizonte de previsão ** campos à demanda de previsão, a partir de conjunto de datas ** ** de data no campo inferior ** horizonte histórico **. Copiando a demanda histórica de uma determinada data em diante, os planejadores de produção podem planejar o próximo trimestre de duas maneiras:

-   Copiando a demanda do mesmo trimestre do ano passado.
-   Copiando a demanda do trimestre anterior.

Para evitar confusão nos planos de produção, um determinado número de classificações de previsão pode ser congelado. Esse número é definido no campo **Congelar limite de tempo**. Na página **Previsão de demanda ajustada**, as células das classificações congeladas são desabilitadas para fornecer uma indicação visual de que esses valores não devem ser alterados. 

A data inicial da previsão de demanda de linha de base não precisa ser a data atual ou uma data futura. Para definir uma data inicial diferente, use **Data de início de previsão de linha de base - Data inicial**. Por exemplo, em junho, os usuários poderão gerar uma previsão para o próximo ano. Como as classificações de previsão entre o fim da demanda histórica e o início da linha de base estão ausentes, as previsões podem não ser precisas. Se estiver usando o Microsoft Dynamics 365 para o serviço de previsões de demanda de operações, há quatro maneiras em que podem preencher os intervalos ausentes. Selecione o método que você deseja definir o parâmetro AUSENTE de SUBSTITUIÇÃO\_do VALOR\_** parâmetros da previsão de demanda ** na página. 

** A linha de base de previsão a data de início ** ** do - data ** campo deve ser definido como o início de uma da previsão, por exemplo, nos Estados Unidos, um domingo se a previsão da semana. O sistema automaticamente ajusta ** data inicial de previsão de linha base ** ** do - data ** de conciliar o início de uma da previsão. 

** A linha de base de previsão a data de início ** ** do - data ** campo pode ser definido para uma data no passado. Em outras palavras, é possível gerar uma previsão de demanda no passado. Isso será útil porque permite que os usuários ajustem os parâmetros do serviço de previsão de modo que a previsão estatística gerada no passado corresponda à demanda histórica real. Os usuários poderão, então, continuar usando essas configurações de parâmetro para gerar uma previsão estatística para o futuro. 

Os ajustes manuais feitos nas iterações de previsão de demanda anteriores poderão ser aplicados automaticamente à nova previsão estatística se a caixa de seleção **Transferir ajustes manuais para a previsão de demanda**. Se a caixa de seleção estiver desmarcada, os ajustes manuais não serão adicionadas à previsão estatísticas, mas não serão excluídos. Os ajustes manuais feitos em uma previsão podem ser excluídos somente no momento da importação da previsão, desmarcando a caixa de seleção **Salvar os ajustes manuais feitos na previsão de demanda da linha de base**. Os ajustes manuais são salvos no momento da autorização. Portanto, se o usuário faz ajustes manuais a previsão, mas não para prever capacita novamente o dynamics 365 para operações, as alterações serão perdidos. Para obter mais informações sobre os ajustes manuais e como trabalham, consulte [autorizando a previsão de authorize-adjusted-forecast.md] (). 

Uma geração de previsão de demanda pode ter um nome e comentários para facilitar a identificação da previsão gerada. Esses valores podem ser vistos no histórico de geração de previsão na página **Histórico de geração de previsão estatística**. 

O grupo de planejamento intercompanhia, as chaves de alocação de itens e outros filtros podem ser aplicados no momento da geração da previsão. Eles podem ser usados para melhorar o desempenho ou para dividir os dados em partes gerenciáveis. No entanto, observe que uma previsão de demanda não será gerada para os membros de qualquer chave de alocação de item que não esteja associada a um grupo de planejamento intercompanhia, mesmo se a chave de alocação de item for selecionada na consulta. 

**Dica**: os usuários podem receber erros enquanto geram uma previsão de demanda; do contrário, a geração de previsão será concluída sem log de sessão. Isso pode ocorrer devido aos dados que restaram na consulta usada anteriormente para a geração da demanda. Para solucionar o problema, clique em **Selecionar** para abrir a página **Consulta**, clique em **Redefinir** e gere novamente a previsão estatística. 

Se a previsão for gerada para uma variedade grande de itens, mas, por exemplo, para um item ou uma chave de alocação de item por vez, a fim de obter melhor desempenho, poderá selecionar ** modo de resposta de solicitação de uso ** a caixa de seleção ** planejamento mestre - o planejamento de demanda - previsão ** no - de instalação ** parâmetros da previsão de demanda - saber de computador de Azure ** guia.

<a name="see-also"></a>Consulte também
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)


