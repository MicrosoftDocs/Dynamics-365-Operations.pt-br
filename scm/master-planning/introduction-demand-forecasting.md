---
title: "Visão geral de previsões de demanda"
description: "A previsão de demanda é usada para prever a demanda independente nas ordens de venda e a demanda dependente em qualquer ponto de dissociação das ordens dos clientes. Regras aprimoradas de redução de previsões de demanda fornecem uma solução ideal para a personalização massa."
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
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9152616b81e7873426f296376b5e57c94439379d
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-overview"></a>Visão geral de previsões de demanda

A previsão de demanda é usada para prever a demanda independente nas ordens de venda e a demanda dependente em qualquer ponto de dissociação das ordens dos clientes. Regras aprimoradas de redução de previsões de demanda fornecem uma solução ideal para a personalização massa.

Para gerar a previsão da linha de base, um resumo de transações históricas será passado para um serviço de Aprendizado de Máquina do Microsoft Azure hospedado no Azure. Como esse serviço não é compartilhado entre usuários, ele pode ser facilmente personalizado para atender aos requisitos específicos do setor. Você pode usar o dynamics 365 para as operações a previsão, visualizem ajustem a previsão, e exibir indicadores chave de desempenho principais (KPIs) sobre a exatidão de previsão.

## <a name="key-features-of-demand-forecasting"></a>Principais recursos de previsão de demanda
Estes são alguns dos principais recursos de previsão de demanda:

-   Gera uma previsão estatística baseada em dados históricos,
-   Usa um conjunto dinâmico de dimensões de previsão.
-   Visualiza tendências de demanda, intervalos de confiança e ajustes da previsão.
-   Autoriza a previsão ajustada a ser usada em processos de planejamento.
-   Remove exceções.
-   Crie medidas de precisão de previsão.

## <a name="major-themes-in-demand-forecasting"></a>Temas principais da previsão de demanda
Os três temas principais são implementados na previsão de demanda:

-   **Modularidade** – A previsão de demanda é modular e fácil de configurar. Você pode desligar sobre a funcionalidade e alterando a chave de configuração comércio ** ** &gt; ** em estoque esperada ** &gt; ** previsão de demanda **.
-   ** A reutilização de pilha Microsoft ** – Microsoft que iniciou o computador a plataforma sabe em fevereiro de 2015. Faça as máquinas, saiba que passa parte do grupo de teste de O Microsoft Cortana, permite criam-nos rapidez e facilidade experiências em caráter de previsão de análise, como experiências previsto de demanda, usando os algoritmos R ou as linguagens de programação de pitão e uma interface simples de arrastar e soltar.
    -   Podem baixar o dynamics 365 experiências de previsões de demanda de operações, alterá-las para atender às suas necessidades comerciais, os publica como um serviço da Web em Azure, e usá-los para gerar previsões de demanda. As experiências estão disponíveis para o download se você adquiriu uma dynamics 365 para a subscrição de operações para um planejador de produção como o usuário do nível da empresa.
    -   Você pode baixar qualquer experimento de previsão de demanda atualmente disponível na [Galeria de Análise da Cortana](https://gallery.cortanaanalytics.com/). Considerando que 365 para o dynamics experiências de previsões de demanda de operações estão integradas automaticamente com dynamics 365 para operações, clientes e parceiros deve tratar a integração das experiências que de baixa galeria [] de análise de Cortana (https://gallery.cortanaanalytics.com/). Portanto, em experiências [galeria de análise de Cortana] não será https://gallery.cortanaanalytics.com/) (simples usar como 365 para dynamics experiências de previsões de demanda de operações. Você deve alterar o código das experiências para usarem o dynamics 365 para a interface de programação de aplicativo (API) de operações.
    -   Você pode criar seus próprios experimentos no Estúdio de Aprendizado de Máquina do Microsoft Azure, publicá-los como serviços no Azure e usá-los para gerar previsões de demanda.
    -   Se você não precisar de alto desempenho ou que uma grande quantidade de dados seja processada, use a camada gratuita do Aprendizado de Máquina. É recomendável que você sempre comece nessa camada, especialmente durante as fases de implementação e de teste. Se você precisar de desempenho mais alto e de armazenamento adicional, poderá usar a camada padrão do Aprendizado de Máquina. Essa camada requer uma assinatura do Azure e envolve custos adicionais. Para obter detalhes sobre os preços do Aprendizado de Máquina, consulte <http://aka.ms/machine-learning-price-info>.
-   ** A redução de previsão em qualquer ponto desacoplando ** – previsão de demanda em dynamics cria 365 para operações dessa funcionalidade, que permitem o prever dependente a demanda e independentes em qualquer ponto desacoplando.

## <a name="basic-flow-in-demand-forecasting"></a>Fluxo básico da previsão de demanda
O diagrama a seguir mostra o fluxo básico da previsão de demanda. 

[diagrama da introdução de previsões de demanda do![(]. /media/demand-forecasting-introduction.png)](. /media/demand-forecasting-introduction.png)

Começa de geração de previsões de demanda em dynamics 365 para as operações. Os dados transacionais de históricos dynamics 365 de dados transacional operações são coletados e preenchem uma tabela de preparo. Essa tabela de preparo é alimentada posteriormente para um computador que tenha certeza o serviço. Executando a personalização mínima, você pode obstruir várias fontes de dados na tabela de preparo. As fontes de dados podem incluir arquivos do Microsoft Excel, arquivos (CSV) do arquivo de valores separados por vírgulas, os dados do Microsoft Dynamics AX 2009 e do Microsoft Dynamics AX 2012. Portanto, você pode gerar as previsões de demanda que considera os dados históricos que são difundidos entre vários sistemas. No entanto, os dados mestres, como nomes de itens e unidades de medida, devem ser iguais nas várias fontes de dados.

Se você usar o dynamics 365 para o computador de previsões de demanda de operações que procuram sabe experiências, um melhor caber entre cinco séries temporais que prevê métodos para calcular uma previsão da linha de base. Parâmetros desses métodos de previsão são gerenciados em dynamics 365 para as operações. 

Previsões, os dados históricos, e todas as alterações que foram feitas nas previsões de demanda em iterações anteriores serão então disponíveis em dynamics 365 para as operações. 

Você pode usar o dynamics 365 para as operações e visualizem alterem previsões de linha de base. Os ajustes manuais devem ser autorizados para que as previsões possam ser usadas para planejamento.

## <a name="limitations"></a>Limitações
A previsão de demanda em dynamics 365 para operações são uma ferramenta que ajude clientes no setor da transformação criar processos de previsão. Fornece a funcionalidade principal de uma solução de previsões de demanda e é criado de forma que possam ser facilmente estendidos. A previsão de demanda não poderia ser melhor caber para clientes em setores como varejo, vendas no atacado, armazenamento, o transporte, ou outros serviços profissionais.

<a name="see-also"></a>Consulte também
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


