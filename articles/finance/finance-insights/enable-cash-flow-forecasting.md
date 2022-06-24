---
title: Habilitar previsão de fluxo de caixa
description: Este artigo explica como ativar o recurso Previsões de fluxo de caixa no Finance Insights.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 253e3ea9c1c44573b37503f167b4cb3860683c10
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859847"
---
# <a name="enable-cash-flow-forecasting"></a>Habilitar previsão de fluxo de caixa

[!include [banner](../includes/banner.md)]

Este artigo explica como ativar o recurso Previsões de fluxo de caixa no Finance Insights.

> [!NOTE]
> Para usar previsões de pagamento no fluxo de caixa, você deve configurar o recurso de previsões de pagamento de cliente conforme descrito em [Habilitar previsões de pagamento de cliente](enable-cust-paymnt-prediction.md).
  
1. Abra o espaço de trabalho **Gerenciamento de recursos** e siga estas etapas:

    1. Selecione **Verificar se há atualizações**.
    2. Na guia **Tudo**, procure **Previsões de fluxo de caixa**. Se você não encontrar esse recurso, procure **(Versão preliminar) Previsões de fluxo de caixa**. 
    3. Ative o recurso.

2. Acesse **Gerenciamento de caixa e bancário \> Configuração de previsão do fluxo de caixa** e adiciona as contas de liquidez que deveriam ser incluídas nas previsões. Configure também a conta de liquidez para pagamentos nas guias **Contas a receber** e **Contas a pagar**. Lembre-se de recalcular a previsão de fluxo de caixa.

    > [!NOTE]
    > Se as contas de liquidez não estiverem configuradas, o fluxo de caixa não poderá ser gerado.
    >
    > Para obter mais informações sobre como configurar previsões de fluxo de caixa, consulte [Previsão de fluxo de caixa](../cash-bank-management/cash-flow-forecasting.md).

3. Acesse **Gerenciamento de caixa e bancário \> Configuração \> Finance Insights (versão prévia) \> Previsões de fluxo de caixa (versão prévia)** e siga estas etapas:

    1. Na guia **Previsão de fluxo de caixa**, selecione **Habilitar recurso**.
    2. Selecione **Criar modelo de previsão**.

> [!NOTE]
> O treinamento do modelo **Previsão de fluxo de caixa** requer dados com 100 ou mais transações que abranjam mais de um ano. É recomendável ter pelo menos dois anos de dados com mais de 1.000 transações.

Para obter mais informações sobre o recurso de previsão de fluxo de caixa, consulte [Previsão de fluxo de caixa](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
