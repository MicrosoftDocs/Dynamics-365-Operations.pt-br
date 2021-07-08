---
title: O número de fórmula selecionado não é aprovado para um pedido de lote
description: Ao tentar firmar uma ordem planejada, você recebe uma mensagem de erro que afirma que o número da fórmula selecionado não é aprovado para uma ordem de lote.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4f993c92ca0a2f8f79e4b0e0eda43904529163f8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294007"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a>O número de fórmula selecionado não é aprovado para um pedido de lote

Código de erro: PRO2614

## <a name="symptoms"></a>Sintomas

Ao tentar firmar uma ordem planejada, você recebe a seguinte mensagem de erro:

> O número de fórmula selecionado não é aprovado para uma ordem de lote.

## <a name="cause"></a>Causa

O sistema valida a operação de firmamento para garantir que uma fórmula aprovada esteja disponível para o item ativo. Você provavelmente deve aprovar a fórmula.

## <a name="resolution"></a>Resolução

Para aprovar uma fórmula, siga estas etapas.

1. Vá para **Gerenciamento de informações sobre produtos \> Lista de materiais e fórmulas \> Fórmulas**.
1. Selecione a fórmula relevante.
1. No Painel de Ação, na guia **Fórmula**, no grupo **Manter**, selecione **Aprovar fórmula**.
1. Na caixa de diálogo **Aprovar lista de materiais ou fórmula**, selecione um aprovador e selecione **OK**.
