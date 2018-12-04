---
title: "Configurar denominações de pagamento à vista para o PDV (ponto de venda)"
description: "Denominações de pagamento à vista para moedas e notas podem ser definidas no back office que será usado pelos caixas, vendedores e gerentes da loja no PDV."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: afc53754c3ff5b1afed2380369cf8280cfffc5e4
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a>Configurar denominações de pagamento à vista para o PDV (ponto de venda)

[!include [banner](includes/banner.md)]

Denominações de pagamento à vista para moedas e notas podem ser definidas no back office que será usado pelos caixas, vendedores e gerentes da loja no PDV. Essas denominações podem ser usadas para ajudar na contagem de dinheiro para declarações de meios de pagamento no fim do dia ou para finalizar uma venda rapidamente.

## <a name="define-denominations"></a>Definir denominações
As denominações são configuradas por loja em **Configurar** > **Opção de declaração de pagamento à vista na página de propriedade da loja**. 

![denominações de pagamento à vista](./media/image1-denomination.png)

Para definir uma denominação:
1. Clique em **Novo**.
1. Especifique o tipo (moeda ou nota).
1. Especifique o valor.

![denominações de pagamento à vista](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Configurar o perfil de funcionalidade
Ao pagar em dinheiro no PDV, o usuário pode usar as denominações de nota para inserir rapidamente o valor pago pelo cliente. No perfil da funcionalidade, você pode configurar as duas opções para mostrar a denominação no PDV.

**Maior ou igual ao valor devido**: por padrão, o PDV só mostrará as denominações de notas maiores do que o valor devido, o que permite o pagamento em um toque. Por exemplo, se o valor devido fosse de US$ 7,50, o PDV mostraria as seguintes denominações: US$ 10, US$ 20, US$ 50 e US$ 100. Ao tocar em qualquer um desses valores, o pagamento será feito automaticamente para esse valor. As notas de US$ 1 e US$ 5 não são mostradas, pois esses valores são menores que o valor devido.

**Todas as denominações**: selecione esta opção para sempre mostrar todas as denominações de nota no PDV, independentemente do valor devido. Isso significa que o usuário poderá usar uma combinação de notas para atingir o valor devido. Por exemplo, se o valor devido for US$ 25,00, o usuário poderá usar notas de US$ 20 e US$ 5 para concluir a venda.

