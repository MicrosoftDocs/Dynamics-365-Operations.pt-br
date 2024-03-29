---
title: Home page do Finance Insights
description: O Finance Insights fornece modelos configuráveis e extensíveis para ajudar você a prever de forma precisa e inteligente o fluxo de caixa da sua empresa, prever quando receberá o pagamento de contas a receber pendentes e gerar uma proposta de orçamento que pode acelerar o processo de orçamento. Todos esses recursos se baseiam nos modelos inteligentes de aprendizado de máquina.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2f04ef1a0de815596f629fede25a247c58e026f4
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643868"
---
# <a name="finance-insights-home-page"></a>Home page do Finance Insights

[!include [banner](../includes/banner.md)]

O Finance Insights fornece soluções configuráveis e extensíveis para ajudá-lo a prever de forma inteligente o fluxo de caixa da sua empresa, prever quando você poderá receber o pagamento de contas a receber pendentes e gerar uma proposta de orçamento que pode ajudar a acelerar o processo de orçamento. Esses recursos usam modelos inteligentes de aprendizado de máquinas para criar modelos usando dados fornecidos (incluindo dados de terceiros, como informações de relatório de consumidores de um bureau). Esses recursos inteligentes informam a tomada de decisões e ajudam você a executar ações para responder efetivamente a desafios de negócios atuais e antecipados. Você é responsável por quaisquer dados usados com, ou saídas do Finance insights.

> [!NOTE]
> O Finance Insights está disponível para implantação nos Estados Unidos da América, Canadá, Reino Unido, Europa, Pacífico Asiático, Japão, Austrália e Nova Zelândia. A Microsoft está adicionando suporte para mais regiões de forma incremental.

## <a name="prerequisites"></a>Pré-requisitos

Esta seção lista os requisitos para o uso do Finance insights. Sempre que possível, são fornecidos links para fontes de informações adicionais.

### <a name="system-requirements"></a>Requisitos do sistema

É necessário um ambiente do nível 2 (várias áreas) para visualizar o Finance Insights. Para obter informações de contexto sobre os ambientes, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Requisitos da versão

Este artigo se aplica ao Microsoft Dynamics 365 Finance versão 10.0.21 e a versões posteriores.

### <a name="license-requirements"></a>Requisitos para licenciamento

O Finance insights usa créditos AI Builder para criar previsões financeiras. Todas as licenças necessárias para isso são incluídas na licença de locatário. Cada locatário do Dynamics 365 Finance recebe 20.000 em créditos AI Builder por mês. Se forem necessários créditos adicionais para as necessidades comerciais, eles poderão ser comprados diretamente do AI Builder.

### <a name="historical-data-requirements"></a>Requisitos de dados históricos

Pelo menos um ano de faturas de clientes é necessário para treinar corretamente o modelo de aprendizado de máquina usado para o recurso de previsões de pagamento do cliente. Três anos de dados históricos são recomendados para previsões de fluxo de caixa. São recomendados três anos de orçamento histórico e/ou reais para propostas de orçamento inteligente.

## <a name="configure-finance-insights"></a>Configurar o Finance Insights

Você deve concluir etapas de configuração para poder usar o Finance Insights. Para obter mais informações sobre como configurar o Finance Insights, consulte [Configuração do Finance Insights](configure-for-fin-insites.md).

## <a name="create-a-data-integrator-project"></a>Criar um projeto integrador de dados

Você precisará criar um projeto de integrador de dados para que os dados gerados pelo modelo de aprendizado de máquina possam fluir para o Dynamics 365 Finance. Para ver as etapas para criar o projeto, consulte [Criar um projeto de integrador de dados](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Habilitar recursos do Finance Insights

Depois de concluir as etapas de configuração e configurar os dados de demonstração, você deve ativar e configurar cada recurso que planeja usar: previsões de pagamento de cliente, previsão de fluxo de caixa e propostas de orçamento.

### <a name="enable-customer-payment-predictions"></a>Habilitar Previsões de pagamento do cliente
Se você estiver usando dados de demonstração para testar previsões de pagamento de cliente, talvez seja necessário importar dados de demonstração adicionais para criar o modelo de IA com êxito. 

Para habilitar previsões de pagamento de cliente, você deve concluir um conjunto de etapas para criar um modelo de aprendizado de máquina que usa dados de sua organização para gerar previsões sobre quando os clientes provavelmente pagarão faturas pendentes e quando faturas específicas provavelmente serão pagas. Para obter mais informações e as etapas específicas a serem concluídas, consulte [Habilitar previsões de pagamento de cliente](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Habilitar Revisão de fluxo de caixa
Para habilitar a previsão de fluxo de caixa, é necessário concluir um conjunto de etapas para criar um modelo de aprendizado de máquina que usa os dados de sua organização para gerar previsões de fluxo de caixa. Para obter mais informações e as etapas específicas a serem concluídas, consulte [Habilitar previsões de fluxo de caixa](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Habilitar propostas de orçamento

O recurso de propostas de orçamento usa um modelo de aprendizado de máquina juntamente com os dados históricos da sua organização para gerar uma proposta de orçamento. A proposta gerada pode ajudar você a iniciar um processo de orçamento que é mais eficaz e eficiente do que um processo manual. Para obter as etapas específicas para habilitar esse recurso, consulte [Habilitar propostas de orçamento](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Usar os recursos do Finance insights

### <a name="using-customer-payment-predictions"></a>Usar Previsões de pagamento do cliente

- Para saber como as previsões de pagamento do cliente podem fornecer as informações necessárias para iniciar de forma proativa atividades de cobrança, consulte [Usar previsões de pagamento do cliente](use-customer-payment-predictions.md).
- Para obter informações que podem ajudar você a avaliar a eficiência do modelo de previsão depois de começar a usar o recurso, consulte [Avaliar o modelo de previsão de pagamento inicial do cliente](evaluate-payment-prediction.md).
- Para obter informações que podem ajudar você a ajustar os dados usados para criar a previsão e, dessa forma, melhorar sua eficácia, consulte [Aperfeiçoar o modelo de previsão](improve-model.md).
- Para aprender mais sobre os resultados dos modelos de previsão de IA, consulte [Resultados de modelos de aprendizado de máquina](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Usar previsões de fluxo de caixa

O recurso de previsão de fluxo de caixa pode ajudar você a estimar mais precisamente sua posição de caixa. A previsão de fluxo de caixa inteligente é criada a partir da funcionalidade de previsão de fluxo de caixa existente no Dynamics 365 Finance. Para revisar a capacidade existente, consulte [Previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting.md).

- Para aprender sobre os novos recursos nas previsões de fluxo de caixa, consulte [Previsão de fluxo de caixa](cash-flow-forecast-intro.md).
- Para obter informações sobre a importação de dados externos a serem incluídos na sua previsão de fluxo de caixa, consulte [Usar dados externos em previsões de fluxo de caixa](external-data-in-cash-flow.md). 
- Para obter informações sobre como usar um modelo de IA para projetar o fluxo de caixa em curto prazo, consulte [Posição de caixa](cash-position.md).
- Para obter informações sobre como salvar posições de fluxo de caixa e previsões de fluxo de caixa como instantâneos, bem como comparar um instantâneo com dados efetivos, consulte [Visão geral de instantâneos](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Usar proposta de orçamento

Para obter informações sobre a aceleração da criação de um orçamento, consulte [Propostas de orçamento](budget-proposals.md). 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
