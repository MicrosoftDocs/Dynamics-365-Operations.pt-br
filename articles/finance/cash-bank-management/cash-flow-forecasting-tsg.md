---
title: Solucionar problemas de configuração de previsão de fluxo de caixa
description: Este tópico oferece respostas para dúvidas que você possa ter ao configurar a previsão de fluxo de caixa. Ele aborda perguntas frequentes sobre a configuração de fluxo de caixa, atualizações para fluxo de caixa e fluxo de caixa do Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985278"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Solucionar problemas de configuração de previsão de fluxo de caixa

[!include [banner](../includes/banner.md)]

Este tópico oferece respostas para dúvidas que você possa ter ao configurar a previsão de fluxo de caixa. Ele aborda perguntas frequentes sobre a configuração de fluxo de caixa, atualizações para fluxo de caixa e fluxo de caixa do Power BI.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>Por que o fluxo de caixa é mostrado para uma única entidade legal?

A previsão de fluxo de caixa é configurada e calculada por entidade legal. Os relatórios do Power BI e o recurso de previsões de fluxo de caixa no Finance Insights mostram os resultados.

A previsão de fluxo de caixa deve ser configurada para cada entidade legal para a qual você deseja ver uma previsão. Revise a configuração de previsão de fluxo de caixa em todas as entidades legais. Como alternativa, revise a configuração de todas as entidades legais para a previsão de fluxo de caixa e verifique se elas estão definidas da maneira desejada.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Por que o Power BI não mostra todos os dados do fluxo de caixa?

Várias etapas devem ser concluídas para que previsões de fluxo de caixa apareçam em exibições do Power BI. Revise a seguinte lista de verificação e verifique se todas as etapas foram concluídas:

- Configure o fluxo de caixa para cada entidade legal.
- Nos parâmetros da contabilidade, defina a moeda do sistema e o tipo de taxa de câmbio do sistema.
- Defina a moeda contábil do razão e o tipo de taxa de câmbio.
- Insira as taxas de câmbio entre a moeda da transação e a moeda contábil.
- Insira as taxas de câmbio entre a moeda contábil e a moeda do sistema.
- Insira as taxas de câmbio entre a moeda contábil e a moeda de cada banco.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>Por que o fluxo de caixa do Power BI funcionou em versões anteriores, mas agora está em branco?

Verifique se as medidas "Medida de fluxo de caixa V2" e "LedgerCovLiquidityMeasurement" do Repositório de entidades foram configuradas. Para obter mais informações sobre como trabalhar com dados no Repositório de entidades, consulte [Integração do Power BI com o Repositório de entidades](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verifique se todas as etapas necessárias para exibir conteúdo do Power BI foram concluídas. Para obter mais informações, consulte [Conteúdo de visão geral do caixa do Power BI](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>As entidades do Repositório de entidades foram atualizadas?

Você deve atualizar as entidades periodicamente para garantir que os dados sejam atuais e precisos. Para atualizar manualmente uma entidade específica, acesse **Administração do sistema \> Configuração \> Repositório de entidades**, selecione a entidade e, depois, selecione **Atualizar**. Os dados também podem ser atualizados automaticamente. Na página **Repositório de entidades**, defina a opção **Atualização automática habilitada** como **Sim**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]