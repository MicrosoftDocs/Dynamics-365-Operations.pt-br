---
title: Configurar períodos de liquidação de imposto retido na fonte para o tipo de imposto TDS
description: Este tópico explica como configurar períodos de liquidação do Imposto Deduzido na Origem (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3807d0588dad4963b9607b9b0feffeb5a9e9c9ef
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726827"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Configurar períodos de liquidação de imposto retido na fonte para o tipo de imposto TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar períodos de liquidação do Imposto Deduzido na Origem (TDS).

1. Acesse **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Períodos de liquidação de imposto retido na fonte**.

    [![Página Períodos de liquidação de imposto retido na fonte.](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)

2. No campo **Tipo de imposto**, selecione **TDS** para configurar períodos de liquidação de imposto retido na fonte para o tipo de imposto TDS.
3. Selecione **Novo** para criar uma linha.
4. No campo **Período de liquidação**, informe um nome para o período de liquidação de TDS.
5. No campo **Descrição**, insira uma descrição.
6. No campo **Autoridade do imposto retido na fonte**, selecione a autoridade de TDS para a qual você está definindo o período de liquidação de TDS.
7. Na FastTAb **Geral**, no campo **Intervalo do período**, selecione o tipo de intervalo do período para o período de liquidação de TDS.
8. No campo **Número de unidades**, especifique o número de unidades para o tipo de intervalo do período.
9. Na FastTab **Períodos**, no campo **Data inicial**, selecione a data inicial para o período de liquidação de TDS. No campo de **Data final**, selecione a data final.
10. Para criar um período de liquidação de TDS subsequente para um período existente, com base nas unidades de intervalo e de período, selecione **Novo período**.
11. Para exibir os detalhes da liquidação de TDS durante a execução para um período de liquidação específico, selecione **Pagamentos de imposto retido na fonte** para abrir a página **Pagamento de imposto retido na fonte**.

    > [!NOTE]
    > Para executar o processo de liquidação de TDS periódico, Acesse **Contabilidade \> Periódico \> Imposto retido na fonte \> Pagamento de imposto retido na fonte**.

    [![Página Pagamento do imposto retido na fonte.](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)

12. Feche a página.
