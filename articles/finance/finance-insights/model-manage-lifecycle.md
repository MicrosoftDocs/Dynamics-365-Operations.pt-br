---
title: Ciclo de vida de gerenciamento de modelos (versão preliminar)
description: Este tópico descreve maneiras de manter os modelos de aprendizado de máquina da sua organização para otimizar as previsões geradas por eles.
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: d5566bde97a2e60d050f4a7b499b554df4848bf9
ms.sourcegitcommit: f6050b444e636ba662c00d0443c94a99f8ea0b0d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309781"
---
# <a name="model-management-lifecycle-preview"></a>Ciclo de vida de gerenciamento de modelos (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve maneiras de manter os modelos de aprendizado de máquina da sua organização para otimizar as previsões geradas por eles.

É recomendável treinar o modelo de AI em um ambiente de área restrita e usar soluções gerenciadas para implantá-lo em um ambiente de produção. Essa abordagem ajuda a garantir que os controles corretos estejam em vigor para gerenciar o ciclo de vida do modelo.

Como o modelo de AI se baseia na fatura disponível e nos dados do cliente, é importante que o ambiente de área restrita tenha uma cópia recente dos dados de produção. Você pode começar a treinar seu modelo seguindo as etapas em [Usar previsões de pagamento do cliente](use-customer-payment-predictions.md). Depois que o modelo tiver sido treinado novamente, avalie os resultados conforme descrito em [Avaliar o modelo de previsão de pagamento inicial do cliente](evaluate-payment-prediction.md). Use as informações no [Aperfeiçoamento do modelo de previsão](improve-model.md) para testar as combinações de recursos e filtros que podem ajudar a melhorar o modelo.

Quando estiver satisfeito com os resultados do treinamento, siga as etapas em [distribuir o modelo de IA](https://docs.microsoft.com/ai-builder/distribute-model) para fazer a transição do modelo para seu ambiente de produção.
