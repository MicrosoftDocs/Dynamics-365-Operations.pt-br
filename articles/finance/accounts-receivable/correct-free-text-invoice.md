---
title: Corrigir uma fatura de texto livre
description: Este tópico explica como corrigir uma nota fiscal de texto livre que foi lançada e emiti-la novamente como uma fatura corrigida.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7fb535b14f4c270f914a427d09027c37b3be7b72
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716203"
---
# <a name="correct-a-free-text-invoice"></a>Corrigir uma fatura de texto livre

[!include [banner](../includes/banner.md)]

Este tópico explica como corrigir uma nota fiscal de texto livre que foi lançada e emiti-la novamente como uma fatura corrigida.

Para corrigir uma fatura de texto livre que já foi lançada, abra a fatura de texto livre lançada. Na página **Fatura**, selecione **Cancelamento** e, em seguida, selecione **Corrigir fatura**. Selecione um código de motivo, adicione comentários, e selecione a data para a nova fatura corrigida. Você pode modificar a fatura corrigida e lançá-la. 

Ao lançar a fatura corrigida, uma fatura de cancelamento será criada para um valor de crédito que é igual ao valor da fatura original. Sendo assim, o saldo combinado da fatura original e da fatura de cancelamento é igual a 0 (zero). A fatura de cancelamento é liquidada com relação à fatura original. 

Depois de lançar a fatura corrigida, você terá três faturas:

-   **Fatura original** – A fatura que inclui as informações que você está corrigindo.
-   **Fatura de cancelamento** – A fatura de crédito gerada pelo sistema, criada para cancelar a fatura que foi corrigida recentemente.
-   **Fatura corrigida** – A fatura que contém as informações da fatura corrigida.

Você pode identificar faturas de correção e cancelamento de duas maneiras:

-   A página **Todas as faturas de texto livre** inclui uma coluna de **Correção**, onde você pode ver quais faturas são faturas de cancelamento e faturas corrigidas.
-   O cabeçalho da fatura de texto livre exibe um status de **Fatura de cancelamento '\[número da fatura\]'** ou **Fatura corrigida '\[número da fatura\]'**.

> [!NOTE]
> Este recurso está disponível somente se a chave de configuração **Correção de fatura de texto livre** estiver selecionada. Para obter mais informações sobre como habilitar Chaves de configuração, consulte a seção Habilitar (ou desabilitar) chaves de configuração no tópico [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md). 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
