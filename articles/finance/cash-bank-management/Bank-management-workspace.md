---
title: Espaço de trabalho de gerenciamento bancário
description: Este tópico fornece informações sobre o espaço de trabalho de gerenciamento de banco. Este espaço de trabalho mostra informações relacionadas às contas bancárias da empresa, e inclui uma exibição de Resumo e uma pagina de análise. A exibição de Resumo mostra quadros resumidos, informações de conta bancária, um gráfico do saldo e informações relacionadas. A página de análise usa os recursos do Microsoft Power BI para mostrar os visuais relacionados a saldos da conta bancária.
author: saraschi2
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 18171dd17165268fe0f7ac0cf7b3b225f679b9b6b7aeafb7789e837059cf5d79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755705"
---
# <a name="bank-management-workspace"></a>Espaço de trabalho de gerenciamento bancário

[!include [banner](../includes/banner.md)]

O espaço de trabalho **Gerenciamento de banco** mostra informações relacionadas a contas bancárias da empresa. Esta área de trabalho inclui uma visualização **Resumo** e uma página **Análise**. A exibição **Resumo** mostra quadros resumidos, informações de conta bancária, um gráfico do saldo e informações relacionadas. A página **Análise** usa os recursos do Microsoft Power BI para mostrar os visuais relacionados a saldos da conta bancária.

## <a name="summary-view"></a>Exibição de resumo

### <a name="summary"></a>Resumo

Os quadros na seção **Resumo** fornecem uma visão geral das contas bancárias e fornecem acesso rápido às páginas que você precisa usar com mais frequência. As informações de reconciliação bancária são específicas à funcionalidade avançada de reconciliação bancária. As informações são incluídas somente para as contas bancárias que têm a opção **Reconciliação bancária avançada** definida como **Sim** na **Conta bancária**. Da seção **Resumo**, você pode importar arquivos eletrônicos bancários para contas bancárias em todas as entidades legais.

### <a name="bank-accounts"></a>Contas Bancárias

Cada conta bancária na entidade legal é representada por um cartão na seção **Contas bancárias**. O saldo atual é mostrado e você pode fazer busca detalhada em transações que compõem o valor do saldo do resumo. O valor **Transações de transição** permite que você faça uma busca detalhada nas transações que compõem o valor de resumo. As transações de transição são todas as transações pendentes que foram lançadas usando a funcionalidade de transição, mas que ainda não foram liberadas. O valor **Saldo pendente** é o saldo atual menor o de transição, ou transações pendentes.

O cartão também mostra quando a conta bancária foi reconciliada pela última vez. Essa informações é exibida apenas se a reconciliação bancária avançada for habilitada para a conta bancária.

### <a name="balance"></a>Saldo

O gráfico **Saldo** mostra as informações de histórico do saldo da conta bancária selecionada na seção **Contas bancárias** ou um resumo das informações de histórico do saldo de todas as contas bancárias na entidade legal. Essa informação está disponível para vários períodos: a semana atual, o mês atual, o ano atual, os últimos cinco anos, e todos os períodos (o histórico completo da conta bancária). 

Se você estiver exibindo o gráfico **Saldo** para uma única conta, os saldos do histórico serão exibidos na moeda da conta bancária. Se você estiver exibindo o gráfico de todas as contas bancárias na entidade legal, os saldos do histórico serão mostrados na moeda contábil.

As informações sobre quando os dados foram atualizados pela última vez aparecem na parte superior do gráfico. Você poderá atualizar os dados como necessário.

### <a name="related-information"></a>Informações Relacionadas

Na seção **Informações relacionadas**, você pode abrir a página **Diário geral** para concluir as transferências bancárias. Você também pode abrir rapidamente as páginas **Transações bancárias** e **Transações de transição**.

## <a name="analytics-view"></a>Exibição de análise

A página **Análise** fornece métricas importante sobre contas bancárias da empresa atual. As seguintes visualizações estão disponíveis na página:

-   Saldo bancário total na moeda do sistema
-   Saldo por entidade legal
-   Saldo real de hoje vs previsto na moeda da conta bancária
-   Saldo por conta bancária
-   Saldo por moeda

Você pode exibir a análise do banco em todas as empresas do espaço trabalho **Visão geral de caixa – todas as empresas**. Para obter mais informações, consulte [Conteúdo de visão geral do caixa do Power BI](Cash-Overview-Power-BI-content.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]