---
title: Configurar descrições padrão para o lançamento de documentos fiscais de imposto
description: Este artigo explica como configurar descrições padrão para transações de comprovante lançadas de documentos fiscais de imposto.
author: gionoder
ms.date: 03/18/2022
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
ms.openlocfilehash: 282107d402bf47ff2c3b4756dbcd50ca8c456afc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896226"
---
# <a name="set-up-default-descriptions-for-posting-of-tax-fiscal-documents"></a>Configurar descrições padrão para o lançamento de documentos fiscais de imposto

[!include [banner](../includes/banner.md)]

Seguir estas etapas para configurar descrições padrão para transações de comprovante lançadas de documentos fiscais de imposto.

1. Vá para **Administração da organização** > **Configuração** > **Descrições padrão**.
2. Selecione **Novo**.
3. No campo **Descrição**, selecionar **Documento fiscal de imposto**.
4. No campo **Linguagem**, selecionar uma linguagem.
5. No campo **Texto**, inserir o texto de descrição padrão. O texto dá suporte às seguintes variáveis de espaço reservado:

    - **%1** A data da transação.
    - **%2** – Um identificador que corresponde ao tipo de documento que está sendo lançado na contabilidade. Por exemplo, se um tipo de transação está relacionado a uma fatura, a %2 variável adiciona o número da fatura.
    - **%3** – Um identificador relacionado ao tipo de documento que está sendo lançado na contabilidade. Por exemplo, se um tipo de transação está relacionado a uma fatura, a %3 variável adiciona o número da conta do cliente.

Para obter mais informações, consulte [Configurar descrições padrão para lançamentos contábeis](../general-ledger/set-up-default-descriptions-for-automatic-posting.md#set-up-default-descriptions)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
