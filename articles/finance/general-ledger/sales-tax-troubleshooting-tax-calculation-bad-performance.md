---
title: O desempenho do cálculo de impostos afeta as transações
description: Este tópico fornece informações sobre como solucionar problemas relacionados ao desempenho do cálculo de impostos e seu efeito nas transações.
author: shtao
ms.date: 04/07/2021
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
ms.openlocfilehash: da19a83945450c2d35f95be2241b84e407860fe7808ff83934686ca2e00859bc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748945"
---
# <a name="tax-calculation-performance-affects-transactions"></a>O desempenho do cálculo de impostos afeta as transações

[!include [banner](../includes/banner.md)]

Às vezes, uma transação é afetada por problemas de desempenho que o cálculo de impostos está tendo. Para solucionar esse problema, siga as etapas nas seguintes seções, conforme necessário.

## <a name="review-the-transaction-line-count"></a>Revisar a contagem de linhas da transação

Determine se a transação tem um grande número de linhas (por exemplo, mais de várias centenas). Se não tiver, Acesse a próxima seção. Se a transação tiver várias centenas de linhas, adie o cálculo de impostos. Para obter mais informações, consulte [Habilitar o cálculo de impostos atrasados nos diários](enable-delayed-tax-calculation.md). 

Em seguida, você pode determinar se alguma das seguintes condições é atendida:

- Há transações de importação de arquivos grandes.
- Várias sessões processam o mesmo cálculo de impostos de transação ao mesmo tempo.
- A transação tem várias linhas, e as exibições são atualizadas em tempo real. Por exemplo, o campo **Valor do imposto calculado** na página **Diário geral** é atualizado em tempo real quando os campos de uma linha são alterados.

   [![Campo Valor do imposto calculado na página Comprovante de diário.](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

Se qualquer uma dessas condições for atendida, adie o cálculo de impostos.

## <a name="review-the-call-stack"></a>Revisar a pilha de chamadas

Revise a pilha de chamadas para determinar se o cálculo de impostos é chamado várias vezes. Se não for, Acesse a próxima seção. Se a pilha de chamadas for chamada várias vezes, siga estas etapas para ajudar a reduzir os tempos de cálculo de impostos.

1. Se o diário tiver considerado a transação, adie o cálculo de impostos. Para obter mais informações, consulte [Habilitar o cálculo de impostos atrasados nos diários](enable-delayed-tax-calculation.md).
2. Se a transação for uma ordem de compra e a versão do aplicativo for posterior a 10.0.15, você poderá adiar o cálculo de impostos até o cálculo final habilitando a liberação de versões para **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.

## <a name="review-the-call-stack-timeline"></a>Revisar a linha do tempo da pilha de chamadas

Revise a linha do tempo da pilha de chamadas para determinar se os seguintes problemas existem. Se existirem, habilite a liberação de versões para **TaxUncommittedDoIsolateScopeFlighting** a fim de corrigir o problema.

- A transação faz com que o sistema pare de responder até que a sessão seja finalizada. Portanto, a transação não pode calcular o resultado do imposto. A ilustração a seguir mostra a caixa de mensagem "Sessão finalizada" que você recebe.

    [![Mensagem Sessão finalizada.](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- Os métodos **TaxUncommitted** levam mais tempo do que outros métodos. Por exemplo, na ilustração a seguir, o método **TaxUncommitted::updateTaxUncommitted()** leva 43.347,42 segundos, mas outros métodos levam 0,09 segundo.

    [![Durações dos métodos.](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>Personalizar e chamar o cálculo de impostos

Ao personalizar, não chame o cálculo de impostos no método **insert()** ou **update()** para cada linha. O cálculo de impostos deve ser chamado no nível da transação.

## <a name="determine-whether-customization-exists"></a>Determinar se há personalização

Se você concluiu as etapas nas seções anteriores, mas não encontrou nenhum problema, determine se há personalização. Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
