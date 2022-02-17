---
title: Configurar descrições padrão para o lançamento de documentos fiscais de imposto
description: Este tópico explica como configurar descrições padrão para transações de comprovante lançadas de documentos fiscais de imposto.
author: gionoder
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FBTaxAssessmentPayment_BR, FBTaxAssessmentPaymentOtherDebits_BR
audience: Application User
ms.reviewer: kfend
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.region: Brazil
ms.author: gionoder
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c30acc987903ed46a79892338767b9dc1edcce03
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075769"
---
# <a name="set-up-default-descriptions-for-posting-of-tax-fiscal-documents"></a>Configurar descrições padrão para o lançamento de documentos fiscais de imposto

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Seguir estas etapas para configurar descrições padrão para transações de comprovante lançadas de documentos fiscais de imposto.

1. Acesse **Administração da organização** \> **Configuração** \> **Descrições padrão**.
2. Selecione **Novo**.
3. No campo **Descrição**, selecionar **Documento fiscal de imposto**.
4. No campo **Linguagem**, selecionar uma linguagem.
5. No campo **Texto**, inserir o texto de descrição padrão. O texto dá suporte às seguintes variáveis de espaço reservado:

    - **%1** A data da transação.
    - **%2** – Um identificador que corresponde ao tipo de documento que está sendo lançado na contabilidade. Por exemplo, se um tipo de transação está relacionado a uma fatura, a %2 variável adiciona o número da fatura.
    - **%3** – Um identificador relacionado ao tipo de documento que está sendo lançado na contabilidade. Por exemplo, se um tipo de transação está relacionado a uma fatura, a %3 variável adiciona o número da conta do cliente.

Para obter mais informações, consulte [Configurar descrições padrão para lançamentos contábeis](../general-ledger/set-up-default-descriptions-for-automatic-posting.md#set-up-default-descriptions)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
