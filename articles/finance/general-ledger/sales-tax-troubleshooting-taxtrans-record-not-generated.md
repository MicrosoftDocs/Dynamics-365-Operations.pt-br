---
title: O registro TaxTrans não é gerado
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudar quando um registro TaxTrans não é gerado.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 969d086c77b40b59495ae0d9e631579abf5e0ec6
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686397"
---
# <a name="taxtrans-record-isnt-generated"></a>O registro TaxTrans não é gerado

[!include [banner](../includes/banner.md)]

Se você selecionar **Imposto lançado** para uma transação, mas a página **Imposto lançado** não mostrar linhas de imposto ou uma linha de imposto estiver ausente, talvez o registro **TaxTrans** não tenha sido gerado.

[![Página Imposto lançado sem itens de linha.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

Para solucionar esse problema, siga as etapas nas seguintes seções, conforme necessário.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>Verificar o imposto antes de lançar a transação

1. Antes de lançar a transação, na página **Lançar fatura**, selecione **Imposto** para verificar o cálculo.

    [![Botão Imposto na página Lançar fatura.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. Na página **Transações temporárias de imposto**, revise o resultado do cálculo. Se nenhum imposto for calculado, consulte [O imposto não é calculado ou o valor do imposto é zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>Localizar o registro TaxTrans em todos os impostos lançados

1. Acesse **Imposto** \> **Consultas e relatórios** \> **Consultas de imposto** > **Imposto lançado**.
2. No título da coluna **Comprovante**, selecione o símbolo de filtro para localizar o registro **TaxTrans**.
3. Se você encontrar os registros de impostos que está procurando, verifique a data. Se a data for diferente da data do cabeçalho do diário, crie uma solicitação de serviço da Microsoft para obter suporte adicional.

    [![Página Imposto lançado.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>Depurar para verificar detalhes

1. Para obter informações sobre como depurar e determinar se **TmpTaxWorkTrans** e **TaxUncommitted** são gerados corretamente, consulte [O valor de campo em TaxTrans está incorreto](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).
2. Se **TaxTmpWorkTrans** ou **TaxUncommitted** for gerado corretamente, adicione um ponto de interrupção em **TaxPost::SaveAndPost()** e **Tax::SaveAndPost** para depurar o motivo pelo qual **TaxTrans** não é inserido.

    [![Pontos de interrupção adicionados no código.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![Resultados de pontos de interrupção adicionados.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>Determinar se há personalização

Se você concluiu as etapas nas seções anteriores, mas não encontrou nenhum problema, determine se há personalização. Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
