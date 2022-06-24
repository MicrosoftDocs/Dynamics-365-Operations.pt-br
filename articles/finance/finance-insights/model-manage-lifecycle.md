---
title: Ciclo de vida de gerenciamento do modelo
description: Este artigo descreve maneiras de manter os modelos de aprendizado de máquina da sua organização para otimizar as previsões geradas por eles.
author: ShivamPandey-msft
ms.date: 07/16/2021
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 526916929e4bc079f9cea82d8ea9f80813e89b83
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880864"
---
# <a name="model-management-lifecycle"></a>Ciclo de vida de gerenciamento do modelo

[!include [banner](../includes/banner.md)]

Este artigo descreve maneiras de manter os modelos de aprendizado de máquina da sua organização para otimizar as previsões geradas por eles.

É recomendável treinar o modelo de AI em um ambiente de área restrita e usar soluções gerenciadas para implantá-lo em um ambiente de produção. Essa abordagem ajuda a garantir que os controles corretos estejam em vigor para gerenciar o ciclo de vida do modelo.

Como o modelo de AI se baseia na fatura disponível e nos dados do cliente, é importante que o ambiente de área restrita tenha uma cópia recente dos dados de produção. Você pode começar a treinar seu modelo seguindo as etapas em [Usar previsões de pagamento do cliente](use-customer-payment-predictions.md). Depois que o modelo tiver sido treinado novamente, avalie os resultados conforme descrito em [Avaliar o modelo de previsão de pagamento inicial do cliente](evaluate-payment-prediction.md). Use as informações no [Aperfeiçoamento do modelo de previsão](improve-model.md) para testar as combinações de recursos e filtros que podem ajudar a melhorar o modelo.

Quando estiver satisfeito com os resultados do treinamento, siga as etapas em [distribuir o modelo de IA](/ai-builder/distribute-model) para fazer a transição do modelo para seu ambiente de produção.
