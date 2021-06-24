---
title: Habilitar revisão de fluxo de caixa (versão prévia)
description: Este tópico explica como habilitar o recurso de previsões de fluxo de caixa no Finance Insights.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ba8acb2191291e2abed5cabf234c19fe09e6c8ff
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222549"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Habilitar revisão de fluxo de caixa (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como habilitar o recurso de previsões de fluxo de caixa no Finance Insights.

> [!NOTE]
> Para usar previsões de pagamento no fluxo de caixa, você deve configurar o recurso de previsões de pagamento de cliente conforme descrito em [Habilitar previsões de pagamento de cliente](enable-cust-paymnt-prediction.md).

1. Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente. Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita. (Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Ignore esta etapa se você estiver usando a versão 10.0.20 ou posterior, ou se você estiver usando uma implantação do Service Fabric. A equipe do Finance Insights já deve ter ativado a versão piloto para você. Se você não vir o recurso no espalho de trabalho **Gerenciamento de recurso**, ou se você tiver problemas ao tentar ativá-lo, entre em contato com <fiap@microsoft.com>.
  
2. Abra o espaço de trabalho **Gerenciamento de recursos** e siga estas etapas:

    1. Selecione **Verificar se há atualizações**.
    2. Ativar os seguintes recursos:

        - Novo controle de grade
        - Agrupamento em grades (versão prévia) 
        - Previsões de pagamento do cliente (versão preliminar)
        - Previsões de fluxo de caixa (versão preliminar)

3. Acesse **Gerenciamento de caixa e bancário \> Configuração de previsão do fluxo de caixa** e adiciona as contas de liquidez que deveriam ser incluídas nas previsões.

    > [!NOTE]
    > Se as contas de liquidez não estiverem configuradas, o fluxo de caixa não poderá ser gerado.

4. Acesse **Gerenciamento de caixa e bancário \> Configuração \> Finance Insights (versão prévia) \> Previsões de fluxo de caixa (versão prévia)** e siga estas etapas:

    1. Na guia **Previsão de fluxo de caixa**, selecione **Habilitar recurso**.
    2. Selecione **Criar modelo de previsão**.

Para obter mais informações sobre o recurso de previsão de fluxo de caixa, consulte [Previsão de fluxo de caixa](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
