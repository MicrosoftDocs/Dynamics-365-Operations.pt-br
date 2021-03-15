---
title: Confirmar Agendamentos de pagamento de arrendamento de ativo em um lote
description: Este tópico explica como confirmar vários agendamentos de pagamento em um lote.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9c680ea16e9f64107fde081c7e7763697356dcc1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971369"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Confirmar Agendamentos de pagamento de arrendamento de ativo em um lote

[!include [banner](../includes/banner.md)]

Este tópico explica como confirmar vários agendamentos de pagamento em um lote. Os planos de pagamento são confirmados em uma base de arrendamento ou por meio do processo de lote de confirmação. Uma entrada de diário pode ser lançada somente em um arrendamento com um plano de pagamento confirmado. A confirmação do plano de pagamento serve como uma aprovação final das informações financeiras para o arrendamento. Todas as alterações futuras feitas nas informações financeiras para o arrendamento, tais como pagamentos e o prazo do arrendamento, constituem um ajuste de arrendamento e devem ser processadas dessa forma.

Para confirmar vários planos de pagamento, siga estas etapas.

1. Vá para **Arrendamento de ativos \> Periódico \> Lote de confirmação**.
2. Na página **Lote de confirmação**, selecione **Lote de confirmação**.
3. Na caixa de diálogo exibida, filtre os livros que deseja confirmar.

    - Para confirmar todos os registros de um grupo de arrendamento específico, selecione o grupo no campo **Grupo de arrendamento**.
    - Para confirmar registros específicos, selecione os registros no campo **ID do registro**.
    - Para confirmar todos os registros, ative o parâmetro **Para todos os registros**.

As informações dos registros recém confirmados são mostradas na página **Registros confirmados**. Depois que os planos de pagamento são confirmados, as entradas iniciais do diário de reconhecimento podem ser lançadas com base nos arrendamentos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]