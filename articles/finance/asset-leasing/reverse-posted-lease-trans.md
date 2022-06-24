---
title: Reverter transações de arrendamento lançadas
description: Este artigo explica como reverter uma transação de arrendamento lançada. Qualquer transação criada por meio do Arrendamento de ativos pode ser revertida.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseTransactions
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4f23b6cca6ddf4da7a0232a5bc61785dbd451d55
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908057"
---
# <a name="reverse-posted-lease-transactions"></a>Reverter transações de arrendamento lançadas

[!include [banner](../includes/banner.md)]

Qualquer transação criada por meio do Arrendamento de ativos pode ser revertida. As transações revertidas por meio de Arrendamento de ativo atualizam os dados do arrendamento. Portanto, eles também atualizam os valores de transporte da responsabilidade com arrendamento e do ativo de direito de uso (DDU).

Para criar uma transação de reversão para um arrendamento, siga estas etapas.

1. Na página **Transações de ativo** ou na página **Transações de passivo**, selecione a transação e, em seguida, selecione **Reverter transação**.
2. Na caixa de diálogo exibida, você pode editar a data em que a entrada de reversão será lançada. Por padrão, o campo de **Data** é definido como a data de lançamento da transação selecionada. A entrada de reversão não pode ser lançada antes da data de lançamento original da transação selecionada.
3. Selecione **OK**. Uma entrada de diário é lançada para reverter a entrada selecionada. A reversão é mostrada na página **Transações de ativo** ou **Transações de passivo** e o total líquido do saldo atual mostrado na página é atualizado.

Quando você seleciona o **Rastreamento da reversão**, é exibida uma caixa de diálogo mostrando as transações originais e as transações revertidas, juntamente com um número vinculado, que é conhecido como um *número de rastreamento*. Para que os estornos possam ser mais fáceis de compreender e para aprimorar a visibilidade, você também pode rastrear estornos usando as agendas de arrendamento.

O campo **Número do diário mais recente** na página **Agenda** mostra os números do diário de transações. Quando uma transação é revertida, esse campo é atualizado com o número do diário de uma transação de reversão. Além disso, a caixa de seleção **Revertida** é marcada para indicar que a transação foi revertida e o campo **Lançada** é selecionado.

## <a name="revoke-a-reversed-transaction"></a>Revogar uma transação revertida

Para revogar uma transação revertida, siga estas etapas.

1. Na página **Agenda** ou na página **Transações**, selecione a transação original.
2. Siga uma destas etapas:

    - Se você tiver selecionado a transação na página **Agenda**, siga as etapas para criar um diário em [Criar entradas de diário mensal em um lote](create-monthly-journals-batch.md). Você deve lançar o diário manualmente.
    - Se você tiver selecionado a transação na página **Transações**, selecione **Reverter transação**. Você receberá uma mensagem informando que a revogação é uma revogação de uma reversão anterior e que é possível editar a data de lançamento dessa revogação. No entanto, as validações gerais de negócios afetam as datas que podem ser inseridas no campo **Data**. 

3. Selecione **OK**. Uma entrada de diário é lançada para reverter a entrada selecionada. A reversão é mostrada na página **Transações** e o saldo líquido atual total é restaurado para o que era antes da primeira reversão. Portanto, o impacto que a reversão tinha nos saldos é negado.

Quando você seleciona **Rastreamento da reversão**, é exibida uma caixa de diálogo mostrando as transações originais e as transações revertidas, juntamente com um número vinculado, que é conhecido como um número de rastreamento.

Você também pode rastrear as revogações usando a página **Agendas** apropriadas. O campo **Reverter** é limpo, enquanto o campo **Lançado no diário** é selecionado. Além disso, o campo **Número do diário mais recente** é atualizado com o número do diário da transação de revogação e o campo **Número do diário** é atualizado com o número do diário de estorno.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
