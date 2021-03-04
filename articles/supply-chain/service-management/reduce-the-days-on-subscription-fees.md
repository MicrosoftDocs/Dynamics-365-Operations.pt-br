---
title: Reduzir os dias em taxas de subscrição
description: Para reduzir o número de dias de uma taxa de subscrição existente, você pode criar uma nova transação e remover o período que não deverá mais fazer parte do intervalo da taxa de subscrição.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 141975e0a3218b18b67d22e04f6f6e8da332ed3d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421928"
---
# <a name="reduce-the-days-on-subscription-fees"></a>Reduzir os dias em taxas de subscrição 

[!include [banner](../includes/banner.md)]


Para reduzir o número de dias de uma taxa de subscrição existente, você pode criar uma nova transação e remover o período que não deverá mais fazer parte do intervalo da taxa de subscrição.

## <a name="reduce-the-days-on-a-subscription-fee"></a>Reduzir os dias de uma taxa de subscrição

1.  Clique em **Gerenciamento de serviço** \> **Comum** \> **Subscrições de serviço** \> **Todas as subscrições de serviço**. Selecione a subscrição no serviço e, no Painel de Ação, clique em **Taxas de subscrição**.

2.  No campo **Tipo de subscrição**, selecione **Dias de redução**.

3.  Use os campos **Data inicial** e **Data final** para definir o intervalo de datas da taxa de subscrição que você deseja remover do período dessa taxa e clique em **OK**.

Para exibir a transação criada, no formulário **Inscrição**, clique em **Transações de taxa**.

## <a name="example"></a>Exemplo

Se o período de uma transação de subscrição for de 1 a 31 de janeiro, e você desejar reduzi-lo em 10 dias, crie uma nova transação na qual o período de redução seja de 1 a 10 de janeiro. (Esse período também poderia ser de 5 a 15 de janeiro, ou qualquer outro período de dez dias).

Além disso, se o campo **Data inicial** do período de redução for igual a 21 de janeiro (31 menos 10), você poderá definir o campo **Data final** como qualquer data após 31 de janeiro, e 10 dias ainda serão removidos do período da transação a taxa.

## <a name="see-also"></a>Consulte também

[Exemplo de dias de redução](reduction-days-example.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]