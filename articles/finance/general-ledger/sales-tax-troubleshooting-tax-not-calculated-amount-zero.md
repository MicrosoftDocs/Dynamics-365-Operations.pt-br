---
title: O imposto não é calculado ou o valor do imposto é zero
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudar quando o valor do imposto for 0 (zero) ou o imposto não for calculado.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 45aa5931b5d958dd32bd165b414957fa7b366d077cef67621221ce19b56b67d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772794"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>O imposto não é calculado ou o valor do imposto é zero

[!include [banner](../includes/banner.md)]

Uma transação pode ter um valor de linha diferente de 0 (zero), mas o imposto não é calculado ou o valor do imposto calculado é 0. Para solucionar esse problema, siga as etapas nas seguintes seções, conforme necessário.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>Verificar se os códigos de imposto foram selecionados corretamente pela transação

Se a transação não selecionar os códigos de imposto corretos ou se não selecionar nenhum código de imposto, os impostos não serão calculados nela. Siga estas etapas para verificar se os códigos de imposto foram selecionados corretamente pela transação. 

1. Na linha de transação, na FastTab **Detalhes da linha**, na guia **Configuração**, na seção **Imposto**, verifique se os grupos de impostos corretos foram selecionados nos campos **Grupo de impostos do item** e **Grupo de impostos**. Se os grupos de impostos corretos não tiverem sido selecionados, selecione-os.

    [![Campos Grupo de impostos do item e Grupo de impostos.](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Grupos de impostos**.
3. Selecione o grupo de impostos apropriado e, na FastTab **Configuração**, anote o código do imposto no campo **Código do imposto**.

    [![Página Grupos de impostos.](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Grupos de impostos do item**.
5. Selecione o grupo de impostos do item apropriado e, na FastTab **Configuração**, verifique se o código de imposto no campo **Código do imposto** corresponde ao código de imposto do grupo de impostos.

    [![Página Grupos de impostos do item.](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. Se os códigos de imposto não corresponderem, atualize o código do imposto de um dos grupos.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>Verificar se os códigos de imposto selecionados não estão isentos e se eles têm o valor correto da taxa de imposto

Se os códigos de imposto estiverem isentos ou se a taxa de imposto for 0 (zero), o resultado do cálculo do imposto será 0. Siga estas etapas para determinar se os códigos de imposto selecionados estão isentos e para verificar se a taxa de imposto correta foi aplicada a eles.

1. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Grupos de impostos**.
2. Selecione o grupo de impostos apropriado e, na FastTab **Configuração**, verifique se a caixa de seleção **Isento** está desmarcada. Se estiver marcada, desmarque-a.

    [![Caixa de seleção Isento na página Grupos de impostos.](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Códigos de imposto**.
4. Selecione o código de imposto apropriado e verifique se o valor da taxa de imposto no campo **Valor** não é 0 (zero). Se for 0, atualize o campo para que seja definido como a taxa de imposto correta.

    [![Campo Valor na página Valores do código de imposto.](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>Determinar se zero é o valor correto do imposto

Em alguns cenários, um valor de imposto 0 (zero) é correto. Siga estas etapas para determinar se 0 é o valor correto do imposto para a sua transação.

1. Acesse **Contabilidade** \> **Configuração do razão** \> **Parâmetros da contabilidade**.
2. Na guia **Imposto**, no campo **Método de cálculo**, verifique se o **Total** foi selecionado.

    [![Campo Método de cálculo na página Parâmetros da contabilidade.](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Códigos de imposto**.
4. Selecione o código de imposto apropriado, selecione **Cálculo** \> **Base marginal** e verifique se a base marginal está definida como **Valor líquido do saldo da fatura** ou **Total da fatura incluindo outros valores de imposto**. Para obter mais informações, consulte o [Total da fatura incluindo outros valores de imposto](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).
5. Se os valores corretos foram definidos nas etapas 2 e 4, determine se o valor total da transação é 0 (zero). Se o valor total for 0, um valor de imposto igual a 0 será o resultado esperado. Como o cálculo do imposto se baseia no valor total do saldo da fatura e esse valor não é linha por linha, o valor do imposto 0 será alocado a cada linha após o cálculo do imposto.

## <a name="determine-whether-customization-exists"></a>Determinar se há personalização

Se você concluiu as etapas nas seções anteriores, mas não encontrou nenhum problema, determine se há personalização. Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
