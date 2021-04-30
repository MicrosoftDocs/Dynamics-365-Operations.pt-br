---
title: Reclassificar a parte de curto prazo de uma responsabilidade com arrendamento
description: Este tópico explica como criar uma entrada de diário mensal para reclassificar uma parte da responsabilidade com arrendamento como um curto prazo.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ae5aebab507479775626579e8b08d68001326a06
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881557"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a><span data-ttu-id="c1d5e-103">Reclassificar a parte de curto prazo de uma responsabilidade com arrendamento</span><span class="sxs-lookup"><span data-stu-id="c1d5e-103">Reclassify the short-term portion of lease liability</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1d5e-104">Este tópico explica como criar uma entrada de diário mensal para reclassificar uma parte da responsabilidade com arrendamento como um curto prazo.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-104">This topic explains how to create a monthly journal entry to reclassify a portion of the lease liability as short-term.</span></span> <span data-ttu-id="c1d5e-105">Quando a agenda selecionada no processo em lote é **Reclassificação de responsabilidade com arrendamento de curto prazo**, uma entrada de diário é criada.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-105">When the schedule that is selected in the batch process is **Short-term lease liability reclass**, a journal entry is created.</span></span> <span data-ttu-id="c1d5e-106">Essa entrada é usada para lançar a parte atual da responsabilidade com arrendamento no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-106">This entry is used to post the current portion of the lease liability on the last day of the month.</span></span> <span data-ttu-id="c1d5e-107">Ao mesmo tempo, uma entrada de estorno é lançada no primeiro dia do mês seguinte.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-107">At the same time, a reversal entry is posted as of the first day of the next month.</span></span>

<span data-ttu-id="c1d5e-108">A parte de curto prazo da responsabilidade com arrendamento é mostrada no plano de amortização de passivo.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-108">The short-term portion of the lease liability is shown on the liability amortization schedule.</span></span> <span data-ttu-id="c1d5e-109">Quando a entrada de diário é lançada, a coluna **Diário de reclassificação de passivos** é disponibilizada e a ID do diário também é preenchida na agenda.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-109">When the journal entry is posted, the **Liability reclass journal created** column becomes available, and the journal ID is also filled in on the schedule.</span></span>

<span data-ttu-id="c1d5e-110">Para criar e lançar a entrada do diário de reclassificação de passivos de curto prazo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-110">To create and post the short-term liability reclassification journal entry, follow these steps.</span></span>

1. <span data-ttu-id="c1d5e-111">Vá para **Arrendamento de ativos \> Periódico \> Criação de diário em lote**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-111">Go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span>
2. <span data-ttu-id="c1d5e-112">Na caixa de diálogo **Criação de diário de lotes**, no campo **Selecionar agenda**, selecione **Reclassificação de responsabilidade com arrendamento de curto prazo**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-112">In the **Batch journal creation** dialog box, in the **Select schedule** field, select **Short-term lease liability reclass**.</span></span>
3. <span data-ttu-id="c1d5e-113">No campo **Grupo de arrendamento**, selecione um grupo de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-113">In the **Lease group** field, select a lease group.</span></span> <span data-ttu-id="c1d5e-114">Como alternativa, no campo **ID do Registro**, selecione a ID do registro.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-114">Alternatively, in the **Book ID** field, select the book ID.</span></span>
4. <span data-ttu-id="c1d5e-115">Ative o parâmetro **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-115">Turn on the **Post** parameter.</span></span> <span data-ttu-id="c1d5e-116">Como alternativa, se a entrada tiver de ser criada mas não lançada, deixe esse parâmetro desativado.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-116">Alternatively, if the entry should be created but not posted, leave this parameter turned off.</span></span>
5. <span data-ttu-id="c1d5e-117">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-117">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
