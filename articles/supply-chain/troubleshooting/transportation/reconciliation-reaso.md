---
title: Você só pode adicionar a conta principal como a conta de crédito para fins de reconciliação
description: Quando você configura um motivo de reconciliação no Gerenciamento de transporte, você só pode adicionar a conta principal como conta de crédito.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026255"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a>Você só pode adicionar a conta principal como a conta de crédito para fins de reconciliação

Número da base de dados de conhecimento: 4603538

## <a name="symptoms"></a>Sintomas

Quando você configura um motivo de reconciliação no Gerenciamento de transporte, você só pode adicionar a conta principal como conta de crédito. Não é possível adicionar um centro de custo ou qualquer outra dimensão como conta de crédito. No entanto, a conta de débito permite que você selecione outras dimensões.

## <a name="resolution"></a>Resolução

Se a reconciliação não for feita para pagar o fornecedor, e sim para creditar uma conta principal específica, o sistema não permitirá que você selecione uma dimensão financeira para a conta de crédito quando você configurar o motivo da reconciliação.

Se a estrutura de conta exigir um valor de dimensão financeira específico para a conta de crédito principal, o diário do fornecedor resultante não poderá ser postado automaticamente, pois o valor de dimensão financeira está ausente. Portanto, você deve primeiro especificar a conta de crédito usando a página **Diário de fatura**.

Como um valor de dimensão é obrigatório para a conta de crédito, o diário de fatura do fornecedor não pode ser postado automaticamente. Você deve postá-lo manualmente após adicionar manualmente o valor de dimensão à conta principal para a linha de crédito.
