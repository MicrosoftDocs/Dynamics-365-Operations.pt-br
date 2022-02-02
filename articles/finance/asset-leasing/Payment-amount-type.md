---
title: Adicionar tipos de valor de pagamento
description: Este tópico explica como configurar tipos de valor de pagamento em Arrendamento de ativos.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 037afa458277a3a07bcb937c6ec4d961d0dd5ca9
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968315"
---
# <a name="add-payment-amount-types"></a>Adicionar tipos de valor de pagamento

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar tipos de valor de pagamento em Arrendamento de ativos. Dessa forma, você pode discriminar o valor do pagamento de arrendamento em vez de adicionar o valor total da soma nas linhas do plano de pagamento.

Para adicionar tipos de valor de pagamento, siga estas etapas.

1. Acesse **Arrendamento de ativos \> Configuração \> Tipos de valor de pagamento**.
2. Selecione **Novo**.
3. Insira o novo tipo de pagamento e uma descrição.

> [!NOTE]
> Para a reavaliação do índice IFRS 16, você deve criar um tipo de valor de pagamento e marcá-lo como **Usado para a reavaliação de índice IRFS 16**. Esse tipo de valor de pagamento será usado quando o processo de reavaliação do índice for executado no catálogo IFRS 16 e considerar as alterações ocorridas por causa do processo de reavaliação do índice.
>
> Quando a opção **Detalhamento de pagamento** no arrendamento estiver definida como **Sim**, se a reavaliação do índice IFRS 16 for executada, mas não houver um tipo de pagamento para IFRS 16, o processo não será concluído.

Somente um registro pode ser marcado como **Usado para reavaliação do índice IFRS 16**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
