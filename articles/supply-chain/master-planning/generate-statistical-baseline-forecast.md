---
title: ​Gerar uma previsão estatística​
description: Este tópico fornece informações sobre os parâmetros e filtros usados no cálculo da previsão de demanda.
author: roxanadiaconu
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 562cf07348e77d9c2f169e31a852843bea10fcc6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816499"
---
# <a name="generate-a-statistical-baseline-forecast"></a>​Gerar uma previsão estatística​

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre os parâmetros e filtros usados no cálculo da previsão de demanda. 

Ao criar uma previsão de baseline, primeiro você deve especificar os parâmetros e os filtros usados no cálculo. Por exemplo, você pode criar uma previsão de baseline que estima a demanda baseada nos dados de transação do ano passado para uma empresa específica, para o mês de entrada e para um grupo de itens selecionado. 

Para gerar uma previsão de demanda, vá para **Planejamento mestre &gt; Previsão &gt; Previsão de demanda &gt; Gerar previsão estatística**. 

A classificação de previsão pode ser selecionada no momento da geração da previsão. Os valores disponíveis são: Dia, Semana e Mês. 

O número de classificações para as quais serão geradas uma previsão é definido no campo **Horizonte de previsão**. 

Quando a estratégia de previsão é definida para **Copiar sobre demanda histórica**, o fim do horizonte histórico é ignorado. O sistema copia o número de classificações especificado no campo **Horizonte de previsão** para a demanda de previsão, começando pela data definida no campo **Data inicial** em **Horizonte histórico**. Copiando a demanda histórica de uma determinada data em diante, os planejadores de produção podem planejar o próximo trimestre de duas maneiras:

-   Copiando a demanda do mesmo trimestre do ano passado.
-   Copiando a demanda do trimestre anterior.

Para evitar confusão nos planos de produção, um determinado número de classificações de previsão pode ser congelado. Esse número é definido no campo **Congelar limite de tempo**. Na página **Previsão de demanda ajustada**, as células das classificações congeladas são desabilitadas para fornecer uma indicação visual de que esses valores não devem ser alterados. 

A data inicial da previsão de demanda de linha de base não precisa ser a data atual ou uma data futura. Para definir uma data inicial diferente, use **Data de início de previsão de linha de base - Data inicial**. Por exemplo, em junho, os usuários poderão gerar uma previsão para o próximo ano. Como as classificações de previsão entre o fim da demanda histórica e o início da linha de base estão ausentes, as previsões podem não ser precisas. Se você estiver usando o serviço de previsão de demanda, há quatro maneiras de preencher as lacunas ausentes. Você pode escolher o método que deseja definindo o parâmetro MISSING\_VALUE\_SUBSTITUTION na página **Parâmetros de previsão de demanda**. 

> [!NOTE]
> A substituição de valor ausente funciona somente para os intervalos em dados entre o início e o fim de dados históricos. Ela não preencherá dados antes ou depois do último ponto de dados físico; ela só funciona como uma extrapolação entre pontos de dados existentes reais. 

O campo **Data de início de previsão de linha de base** - **Data inicial** deve ser definido como o início de uma classificação de previsão, por exemplo, nos Estados Unidos, um domingo, se a previsão for semanal. O sistema ajusta automaticamente o campo **Data de início de previsão de linha de base** - **Data inicial** de modo que corresponda ao início de uma classificação de previsão. 

O campo **Data de início de previsão de linha de base** - **Data inicial** pode ser definido para uma data no passado. Em outras palavras, é possível gerar uma previsão de demanda no passado. Isso será útil porque permite que os usuários ajustem os parâmetros do serviço de previsão para que a previsão estatística gerada no passado corresponda à demanda histórica real. Os usuários poderão, então, continuar usando essas configurações de parâmetro para gerar uma previsão estatística para o futuro. 

Os ajustes manuais feitos nas iterações de previsão de demanda anteriores poderão ser aplicados automaticamente à nova previsão estatística se a caixa de seleção **Transferir ajustes manuais para a previsão de demanda**. Se a caixa de seleção estiver desmarcada, os ajustes manuais não serão adicionadas à previsão estatísticas, mas não serão excluídos. Os ajustes manuais feitos em uma previsão podem ser excluídos somente no momento da importação da previsão, desmarcando a caixa de seleção **Salvar os ajustes manuais feitos na previsão de demanda da linha de base**. Os ajustes manuais são salvos no momento da autorização. Portanto, se um usuário fizer ajustes manuais na previsão, mas não autorizar a previsão no Supply Chain Management, as alterações serão perdidas. Para obter mais informações sobre os ajustes manuais e como eles funcionam, consulte [Autorizar uma previsão ajustada](authorize-adjusted-forecast.md). 

Uma geração de previsão de demanda pode ter um nome e comentários para facilitar a identificação da previsão gerada. Esses valores podem ser vistos no histórico de geração de previsão na página **Histórico de geração de previsão estatística**. 

O grupo de planejamento intercompanhia, as chaves de alocação de itens e outros filtros podem ser aplicados no momento da geração da previsão. Eles podem ser usados para melhorar o desempenho ou para dividir os dados em partes gerenciáveis. No entanto, observe que uma previsão de demanda não será gerada para os membros de qualquer chave de alocação de item que não esteja associada a um grupo de planejamento intercompanhia, mesmo se a chave de alocação de item for selecionada na consulta. 

> [!TIP]
> Os usuários talvez recebam erros ao gerar uma previsão de demanda ou a geração de previsão será concluída sem log de sessão. Isso pode ocorrer devido aos dados que restaram na consulta usada anteriormente para a geração da demanda. Para resolver esse problema, clique em **Selecionar** para abrir a página **Consulta**, selecione **Redefinir** e gere novamente a previsão de linha de base. 

Se a previsão não for gerada para um grande conjunto de itens, mas, por exemplo, para um item ou uma chave de alocação de item por vez, você poderá marcar a caixa de seleção **Usar modo de resposta da solicitação** na guia **Planejamento mestre - Configuração - Previsão de demanda** - **Parâmetros de previsão de demanda - Aprendizado de Máquina do Azure** a fim de melhorar o desempenho.

> [!NOTE]
> Uma previsão aparentemente tranquila talvez deva-se aos dados históricos que precisam ser de um período histórico maior (no mínimo 3 períodos para selecionar padrões, como 3 anos com previsão mensal). Para obter um resultado melhor, tente alterar a granularidade do intervalo de tempo ou aumentar o intervalo de tempo.

<a name="additional-resources"></a>Recursos adicionais
--------

- [Configuração da previsão de demanda](demand-forecasting-setup.md)

- [Faça ajustes manuais para a previsão estatística](manual-adjustments-baseline-forecast.md)

- [Autorizar uma previsão ajustada](authorize-adjusted-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]