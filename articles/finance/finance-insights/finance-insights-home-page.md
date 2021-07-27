---
title: Página inicial do Finance insights (versão prévia)
description: O Finance Insights fornece modelos configuráveis e extensíveis para ajudar você a prever de forma precisa e inteligente o fluxo de caixa da sua empresa, prever quando receberá o pagamento de contas a receber pendentes e gerar uma proposta de orçamento que pode acelerar o processo de orçamento. Todos esses recursos se baseiam nos modelos inteligentes de aprendizado de máquina.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: f0d709ef81fd43c009bf36aba2d4be949b1a737c
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338220"
---
# <a name="finance-insights-home-page-preview"></a>Página inicial do Finance insights (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O Finance Insights fornece modelos configuráveis e extensíveis para ajudar você a prever de forma precisa e inteligente o fluxo de caixa da sua empresa, prever quando receberá o pagamento de contas a receber pendentes e gerar uma proposta de orçamento que pode acelerar o processo de orçamento. Todos esses recursos se baseiam nos modelos inteligentes de aprendizado de máquina. Quando esses novos recursos são combinados com a automação em pagamentos e cobranças de fornecedores, eles fornecem um sistema financeiro avançado e inteligente que conduz a tomada de decisões e ajuda você a tomar ações para responder com eficiência a desafios de negócios atuais e antecipados.

> [!NOTE]
> A versão preliminar pública do Finance Insights está disponível para implantação nos Estados Unidos da América, Canadá, Reino Unido, Europa, Pacífico Asiático, Austrália e Nova Zelândia. A Microsoft está adicionando suporte para mais regiões de forma incremental. Para habilitar o Finance Insights em ambientes de produção, a [exportação para recursos data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) deve ser habilitada primeiro no ambiente de produção.

> [!NOTE]
> Essa funcionalidade está sendo oferecida como um conjunto de versões prévias do recurso. Como uma versão prévia do recurso, você não deve usar os modelos de aprendizado de máquina resultantes para impulsionar ou influenciar suas decisões de negócios ou propostas orçamentárias. O uso deste recurso é regido pelos [Termos de Uso Complementares](https://go.microsoft.com/fwlink/?linkid=2105274).

## <a name="prerequisites"></a>Pré-requisitos

Esta seção lista os requisitos para o uso do Finance insights. Sempre que possível, são fornecidos links para fontes de informações adicionais.

### <a name="legal-requirements"></a>Requisitos legais

Para se inscrever no programa de versão prévia, preencha o [contrato do Finance Insights para o Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u).

### <a name="system-requirements"></a>Requisitos do sistema

É necessário um ambiente do nível 2 (várias áreas) para visualizar o Finance Insights. Para obter informações de contexto sobre os ambientes, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Requisitos da versão

Este documento aplica-se à versão 10.0.11 de aplicativos do Finance and Operations (atualização de plataforma 35) e a versões posteriores.

### <a name="historical-data-requirements"></a>Requisitos de dados históricos

Pelo menos um ano de faturas de clientes é necessário para treinar corretamente o modelo de aprendizado de máquina usado para o recurso de previsões de pagamento do cliente.

### <a name="role-and-permission-requirements"></a>Requisitos de função e permissão

As alterações serão feitas no Microsoft Dynamics 365 Finance, Microsoft Dynamics Lifecycle Services (LCS), Power Apps e Azure. As permissões corretas são necessárias nesses ambientes. Estas são alguns exemplos das alterações que serão feitas:

- Será criado um novo ambiente no Microsoft Power Platform.
- Uma conta de armazenamento, um cofre de chaves e um aplicativo serão criados no Azure.
- O administrador de locatários do Active Directory terá que autorizar o aplicativo AI Builder a acessar o data lake.
- O recurso será ativado no Dynamics 365.

A familiaridade com o processo de criação e gerenciamento de recursos no Azure, Microsoft Dataverse e LCS será útil ao concluir esse processo.

## <a name="configure-finance-insights"></a>Configurar o Finance Insights

Você deve concluir algumas etapas de configuração para poder usar ao Finance Insights. Para obter mais informações sobre como configurar o Finance Insights, consulte:
  - Para versões até 10.0.19: [Configuração para o Finance Insights (versão preliminar) – Versões até 10.0.19](configure-for-fin-insites.md).
  - Para versões 10.0.20 e posteriores: [Configuração para Finance Insights (versão preliminar) – versões 10.0.20 e posteriores](configure-for-fin-insites-PubPrvw.md).

## <a name="create-a-data-integrator-project"></a>Criar um projeto integrador de dados

Você precisará criar um projeto de integrador de dados para que os dados gerados pelo modelo de aprendizado de máquina possam fluir para o Dynamics 365 Finance. Para ver as etapas para criar o projeto, consulte [Criar um projeto de integrador de dados](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Habilitar recursos do Finance Insights

Depois de concluir as etapas de configuração e configurar os dados de demonstração, você deve ativar e configurar cada recurso que planeja usar: previsões de pagamento de cliente, previsão de fluxo de caixa e propostas de orçamento.

### <a name="enable-customer-payment-predictions"></a>Habilitar Previsões de pagamento do cliente
Se você estiver usando dados de demonstração para testar previsões de pagamento de cliente, talvez seja necessário importar dados de demonstração adicionais para criar o modelo de IA com êxito. 

Para habilitar previsões de pagamento de cliente, você deve concluir um conjunto de etapas para criar um modelo de aprendizado de máquina que usa os dados de sua organização para gerar previsões sobre quando os clientes provavelmente pagarão faturas pendentes e quando faturas específicas provavelmente serão pagas. Para obter mais informações e as etapas específicas a serem concluídas, consulte [Habilitar previsões de pagamento de cliente](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Habilitar Revisão de fluxo de caixa
Para habilitar a previsão de fluxo de caixa, é necessário concluir um conjunto de etapas para criar um modelo de aprendizado de máquina que usa os dados de sua organização para gerar previsões de fluxo de caixa. Para obter mais informações e as etapas específicas a serem concluídas, consulte [Habilitar previsões de fluxo de caixa](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Habilitar propostas de orçamento

O recurso de propostas de orçamento usa um modelo de aprendizado de máquina juntamente com os dados históricos da sua organização para gerar uma proposta de orçamento. A proposta gerada pode ajudar você a iniciar um processo de orçamento que é mais eficaz e eficiente do que um processo manual. Para obter as etapas específicas para habilitar esse recurso, consulte [Habilitar propostas de orçamento](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Usar os recursos do Finance insights

### <a name="using-customer-payment-predictions"></a>Usar Previsões de pagamento do cliente

A previsão de fluxo de caixa inteligente é criada a partir da funcionalidade de previsão de fluxo de caixa existente no Dynamics 365 Finance. Para revisar a capacidade existente, consulte [Previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting.md).

- Para saber como as previsões de pagamento do cliente podem fornecer as informações necessárias para ser proativamente atividades de cobrança, consulte [Usar previsões de pagamento de cliente](use-customer-payment-predictions.md).
- Para obter informações que podem ajudar você a avaliar a eficiência do modelo de previsão depois de começar a usar o recurso, consulte [Avaliar o modelo de previsão de pagamento inicial do cliente](evaluate-payment-prediction.md).
- Para obter informações que podem ajudar você a ajustar os dados usados para criar a previsão e, dessa forma, melhorar sua eficácia, consulte [Aperfeiçoar o modelo de previsão](improve-model.md).

Para aprender mais sobre os resultados dos modelos de previsão de IA, consulte [Resultados de modelos de aprendizado de máquina](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Usar previsões de fluxo de caixa

O recurso de previsão de fluxo de caixa pode ajudar você a estimar mais precisamente sua posição de caixa. 

- Para aprender sobre os novos recursos nas previsões de fluxo de caixa, consulte [Previsão de fluxo de caixa](cash-flow-forecast-intro.md).
- Para obter informações sobre a importação de dados externos a serem incluídos na sua previsão de fluxo de caixa, consulte [Usar dados externos em previsões de fluxo de caixa](external-data-in-cash-flow.md). 
- Para obter informações sobre como usar um modelo de IA para projetar o fluxo de caixa em curto prazo, consulte [Posição de caixa](cash-position.md).
- Para obter informações sobre como salvar posições de fluxo de caixa e previsões de fluxo de caixa como instantâneos, bem como comparar um instantâneo com dados efetivos, consulte [Visão geral de instantâneos](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Usar proposta de orçamento

Para obter informações sobre a aceleração da criação de um orçamento, consulte [Propostas de orçamento](budget-proposals.md). 

## <a name="feedback-and-support"></a>Comentários e suporte

Envie um email para [insights de pagamento do cliente (versão prévia)](mailto:fiap@microsoft.com) se tiver interesse em fornecer comentários ou precisar de suporte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
