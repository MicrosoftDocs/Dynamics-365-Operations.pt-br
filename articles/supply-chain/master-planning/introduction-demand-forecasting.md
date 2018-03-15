---
title: "Visão geral da previsão de demanda"
description: "A previsão de demanda é usada para prever a demanda independente nas ordens de venda e a demanda dependente em qualquer ponto de dissociação das ordens dos clientes. As regras aprimoradas de redução de previsão de demanda oferecem uma solução ideal para a personalização em massa."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 18ed011fa1c1aa35b4a401d51bffc6af19395577
ms.openlocfilehash: 6a0455c5d86f953e270501a7f1648f7700f717d0
ms.contentlocale: pt-br
ms.lasthandoff: 02/13/2018

---

# <a name="demand-forecasting-overview"></a>Visão geral da previsão de demanda

[!include[banner](../includes/banner.md)]


A previsão de demanda é usada para prever a demanda independente nas ordens de venda e a demanda dependente em qualquer ponto de dissociação das ordens dos clientes. As regras aprimoradas de redução de previsão de demanda oferecem uma solução ideal para a personalização em massa.

Para gerar a previsão da linha de base, um resumo de transações históricas será passado para um serviço de Aprendizado de Máquina do Microsoft Azure hospedado no Azure. Como esse serviço não é compartilhado entre usuários, ele pode ser facilmente personalizado para atender aos requisitos específicos do setor. Você pode usar o Finance and Operations para visualizar a previsão, ajustar a previsão e exibir KPIs (indicadores chave de desempenho) sobre a precisão da previsão.

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

-   **Modularidade** – A previsão de demanda é modular e fácil de configurar. Você pode ativar e desativar a funcionalidade alterando a chave de configuração em **Comércio** &gt; **Previsão de estoque** &gt; **Previsão de demanda**.
-   **Reutilização da pilha da Microsoft** – O Microsoft iniciou a plataforma Aprendizado de Máquina em fevereiro de 2015. O Aprendizado de Máquina, que agora faz parte da Microsoft Cortana Analytics Suite, permite criar rápida e facilmente experimentos de análise preditiva, como experiências de estimativa de demanda, usando linguagens de programação R ou Python e uma interface simples de arrastar e soltar.
    -   Você pode baixar experimentos de previsão de demanda do Finance and Operations, alterá-los para atender às suas necessidades de negócios, publicá-los como um serviço Web no Azure e usá-los para gerar previsões de demanda. Os experimentos estarão disponíveis para download se você tiver adquirido uma assinatura do Finance and Operations para um planejador de produção como usuário em nível empresarial.
    -   Você pode baixar qualquer experimento de previsão de demanda atualmente disponível na [Galeria de Análise da Cortana](https://gallery.cortanaanalytics.com/). Desde que os experimentos de previsão de demanda do Finance and Operations sejam automaticamente integrados ao Finance and Operations, os clientes e parceiros devem tratar a integração dos experimentos baixados da [Galeria de Análise da Cortana](https://gallery.cortanaanalytics.com/). Portanto, os experimentos da [Galeria de Análise da Cortana](https://gallery.cortanaanalytics.com/) não são tão simples de usar quanto os experimentos de previsão de demanda do Finance and Operations. Você deve modificar o código dos experimentos de modo que eles usem a API (interface de programação de aplicativo) do Finance and Operations.
    -   Você pode criar seus próprios experimentos no Estúdio de Aprendizado de Máquina do Microsoft Azure, publicá-los como serviços no Azure e usá-los para gerar previsões de demanda.
    -   Se você não precisar de alto desempenho ou que uma grande quantidade de dados seja processada, use a camada gratuita do Aprendizado de Máquina. É recomendável que você sempre comece nessa camada, especialmente durante as fases de implementação e de teste. Se você precisar de desempenho mais alto e de armazenamento adicional, poderá usar a camada padrão do Aprendizado de Máquina. Essa camada requer uma assinatura do Azure e envolve custos adicionais. Para obter detalhes sobre os preços do Aprendizado de Máquina, consulte <http://aka.ms/machine-learning-price-info>.
-   **Redução de previsão em qualquer ponto de dissociação** – A previsão de demanda no Finance and Operations baseia-se nessa funcionalidade, que permite prever a demanda dependente e independente em qualquer ponto de dissociação.

## <a name="basic-flow-in-demand-forecasting"></a>Fluxo básico da previsão de demanda
O diagrama a seguir mostra o fluxo básico da previsão de demanda. 

[![diagrama de introdução da previsão de demanda](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

A geração de previsão de demanda começa no Finance and Operations. Os dados transacionais históricos do banco de dados transacional do Finance and Operations são coletados e preenchem uma tabela de preparo. Essa tabela de preparo é alimentada posteriormente em um serviço de Aprendizado de Máquina. Ao executar um mínimo de personalização, você pode obstruir várias fontes de dados na tabela de preparo. As fontes de dados podem incluir arquivos do Microsoft Excel, arquivos CSV (valores separados por vírgulas) e dados do Microsoft Dynamics AX 2009 e Microsoft Dynamics AX 2012. Portanto, você pode gerar as previsões de demanda que considera os dados históricos que são difundidos entre vários sistemas. No entanto, os dados mestres, como nomes de itens e unidades de medida, devem ser iguais nas várias fontes de dados.

Se você usar os experimentos de Aprendizado de Máquina da previsão de demanda do Finance and Operations, eles procurarão um melhor ajuste entre cinco métodos de previsão de série de tempo para calcular uma previsão estatística. Os parâmetros desses métodos de previsão são gerenciados no Finance and Operations. 

As previsões, os dados históricos e todas as alterações que foram feitas nas previsões de demanda em iterações anteriores serão, então, disponibilizadas no Finance and Operations. 

Você pode usar o Finance and Operations para visualizar e modificar as previsões estatísticas. Os ajustes manuais devem ser autorizados para que as previsões possam ser usadas para planejamento.

## <a name="limitations"></a>Limitações
A previsão de demanda no Finance and Operations é uma ferramenta que ajuda os clientes do setor de manufatura a criar processos de previsão. Ela oferece a funcionalidade principal de uma solução de previsão de demanda e é criada de modo que possa ser facilmente estendida. A previsão de demanda pode não ser o melhor ajuste para clientes de setores como varejo, atacado, armazenamento, transporte ou outros serviços profissionais.

<a name="see-also"></a>Consulte também
--------

[Configuração da previsão de demanda](demand-forecasting-setup.md)

[Gerando uma previsão estatística](generate-statistical-baseline-forecast.md)

[Ajustes manuais na previsão estatística](manual-adjustments-baseline-forecast.md)

[Autorizando a previsão ajustada](authorize-adjusted-forecast.md)

[Monitorando a precisão da previsão](monitor-forecast-accuracy.md)

[Remover exceções de dados históricos de transação ao calcular uma previsão de demanda](remove-historical-outliers-calculating-demand-forecast.md)

[Estender a funcionalidade de previsão de demanda](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)




