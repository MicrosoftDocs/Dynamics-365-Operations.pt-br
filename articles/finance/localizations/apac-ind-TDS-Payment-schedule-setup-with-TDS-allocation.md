---
title: Configurar agendas de pagamento com alocação de TDS
description: Este tópico explica como configurar planos de pagamento com alocação de Imposto Deduzido na Origem (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 31ecf2e6fa4d3d37c3d5332dc1d5592bf1a99bad
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408081"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>Configurar agendas de pagamento com alocação de TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar planos de pagamento com alocação de Imposto Deduzido na Origem (TDS).

1. Acesse **Contas a pagar \> Configurar pagamento \> Planos de pagamento**.

    [![Página Planos de pagamento.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. No Painel de Ações, selecione **Novo** para criar um plano de pagamento e insira os detalhes necessários.
3. No campo **Alocação**, selecione o método a ser usado para alocar o pagamento para o plano de pagamentos:

    - Total
    - Valor fixo
    - Quantidade fixa
    - Especificado

    O campo **Alocação de imposto retido na fonte** mostra o método de alocação de TDS para o plano de pagamento. Se você selecionar **Total** no campo **Alocação**, o campo **Alocação de imposto retido na fonte** será automaticamente definido como **Total**. Se você selecionar **Valor fixo**, **Quantidade fixa** ou **Especificado** no campo **Alocação**, o campo **Alocação de imposto retido na fonte** é automaticamente definido como **Proporcionalmente**.

    > [!NOTE]
    > Se o campo **Alocação de imposto retido na fonte** for definido como **Total**, as prestações de pagamento são calculadas com base no valor bruto, que inclui o valor do TDS. Se o campo **Alocação de imposto retido na fonte** for definido como **Proporcionalmente**, as prestações de pagamento são calculadas com base no valor líquido da fatura após a dedução do valor do TDS.

4. Insira os outros detalhes necessários e feche a página.
