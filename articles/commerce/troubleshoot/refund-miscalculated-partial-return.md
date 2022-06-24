---
title: Encargos reembolsáveis calculados incorretamente com base na quantidade devolvida
description: Este artigo fornece orientações de solução de problemas que podem ajudar quando os caixas veem os encargos reembolsáveis incorretos no PDV (ponto de venda) para a quantidade de itens devolvidos.
author: gvrmohanreddy
ms.date: 03/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 7a84207f587a826b9acdfd818c64220c5327bde1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890234"
---
# <a name="refundable-charges-are-miscalculated-based-on-the-quantity-returned"></a>Encargos reembolsáveis calculados incorretamente com base na quantidade devolvida

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientações de solução de problemas que podem ajudar quando os caixas veem os encargos reembolsáveis incorretos no PDV (ponto de venda) para a quantidade de itens devolvidos.

## <a name="description"></a>Descrição

Um cliente retorna uma quantidade parcial dos itens que foram comprados para uma ordem de venda que tem encargos reembolsáveis no nível de linha. No entanto, em vez de mostrar um reembolso parcial, o PDV mostra todos os encargos como reembolsáveis.

Por exemplo, um cliente compra uma quantidade de cinco itens em $5 por item para encargos totais de $25. O cliente retorna três dos cinco itens. No entanto, o caixa é mostrado um encargo reembolsável de $25 no PDV, em vez do encargo de $15 de encargo reembolsável para os três itens que foram devolvidos.

## <a name="resolution"></a>Resolução

### <a name="turn-on-the-enable-refunding-charges-based-on-the-refunded-quantity-feature"></a>Habilite o recurso Habilitar encargos de reembolso com base na quantidade reembolsada

A partir da versão 10.0.26 do Microsoft Dynamics 365 Commerce, o recurso **Habilitar encargos de reembolso com base na quantidade reembolsada** permite que os encargos reembolsáveis em nível de linha sejam calculados com base na quantidade de itens devolvidos.

Para habilitar o recurso **Habilitar encargos de reembolso com base na quantidade reembolsada** no Commerce headquarters, siga estas etapas.

1. Abra o espaço de trabalho **Gerenciamento de recursos** (**Administrador do sistema \> Espaços de trabalho\> Gerenciamento de recursos**).
1. Na lista de recursos disponíveis, procure e selecione o recurso **Habilitar encargos de reembolso com base na quantidade reembolsada**.
1. No painel à direita, selecione **Habilitar agora**.
