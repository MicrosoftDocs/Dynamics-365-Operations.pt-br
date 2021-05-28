---
title: O comprovante não é gerado
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudar quando um comprovante deve ser gerado, mas não é.
author: qire
ms.date: 04/13/2021
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
ms.openlocfilehash: ba23b597b1d7d283b99638fb7d5d91da00afb09c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018748"
---
# <a name="voucher-isnt-generated"></a><span data-ttu-id="5bc87-103">O comprovante não é gerado</span><span class="sxs-lookup"><span data-stu-id="5bc87-103">Voucher isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5bc87-104">Se um comprovante deve ser gerado, mas a página **Transações de comprovante** não mostrar nenhum comprovante, siga as etapas nas seções a seguir, conforme necessário, para solucionar esse problema.</span><span class="sxs-lookup"><span data-stu-id="5bc87-104">If a voucher should be generated, but the **Voucher transactions** page doesn't show any vouchers, follow the steps in the following sections as required to troubleshoot this issue.</span></span>

<span data-ttu-id="5bc87-105">[![Página Transações de comprovante que não tem comprovantes](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="5bc87-105">[![Voucher transactions page that has no vouchers](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)</span></span>

## <a name="check-the-tax-applicability"></a><span data-ttu-id="5bc87-106">Verificar a aplicabilidade do imposto</span><span class="sxs-lookup"><span data-stu-id="5bc87-106">Check the tax applicability</span></span>

1. <span data-ttu-id="5bc87-107">Vá para **Imposto** \> **Tarefas periódicas** \> **Entradas no diário-razão auxiliar ainda não transferidas**.</span><span class="sxs-lookup"><span data-stu-id="5bc87-107">Go to **Tax** \> **Periodic tasks** \> **Subledger journal entries not yet transferred**.</span></span>
2. <span data-ttu-id="5bc87-108">Se houver um registro de diário, selecione-o e, em seguida, selecione **Transferir agora**.</span><span class="sxs-lookup"><span data-stu-id="5bc87-108">If there is a journal record, select it, and then select **Transfer now**.</span></span>

    <span data-ttu-id="5bc87-109">[![Botão Transferir agora na página Entradas no diário-razão auxiliar ainda não transferidas](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="5bc87-109">[![Transfer now button on the Subledger journal entries not yet transferred page](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)</span></span>

3. <span data-ttu-id="5bc87-110">Abra a página **Transações de comprovante** novamente para ver se o comprovante foi gerado.</span><span class="sxs-lookup"><span data-stu-id="5bc87-110">Open the **Voucher transactions** page again to see whether the voucher was generated.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="5bc87-111">Determinar se há personalização</span><span class="sxs-lookup"><span data-stu-id="5bc87-111">Determine whether customization exists</span></span>

<span data-ttu-id="5bc87-112">Se você concluiu as etapas na seção anterior, mas não encontrou nenhum problema, determine se há personalização.</span><span class="sxs-lookup"><span data-stu-id="5bc87-112">If you've completed the steps in the previous section but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="5bc87-113">Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.</span><span class="sxs-lookup"><span data-stu-id="5bc87-113">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
