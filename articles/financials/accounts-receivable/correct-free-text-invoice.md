---
title: Corrigir uma fatura de texto livre
description: "Este artigo explica como corrigir uma nota fiscal de texto livre que foi lançada e emiti-la novamente como uma nota fiscal corrigida."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a353db68c2223d62cd8e5048f0e953ed134c0803
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="correct-a-free-text-invoice"></a>Corrigir uma fatura de texto livre

[!include[banner](../includes/banner.md)]


Este artigo explica como corrigir uma nota fiscal de texto livre que foi lançada e emiti-la novamente como uma nota fiscal corrigida.

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
> Este recurso está disponível somente se a chave de configuração **Correção de fatura de texto livre** estiver selecionada.




