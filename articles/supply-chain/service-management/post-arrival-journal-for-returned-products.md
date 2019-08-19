---
title: Lançar diário de entrada para produtos devolvidos
description: Lançar diário de entrada para produtos devolvidos.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63659288ab8551e458f6e92a5045c72441ff68cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743270"
---
# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="b2005-103">Lançar diário de entrada para produtos devolvidos</span><span class="sxs-lookup"><span data-stu-id="b2005-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b2005-104">Para processar uma devolução, primeiro valide a quantidade devolvida, atualize o campo de quantidade no diário de entrada de itens.</span><span class="sxs-lookup"><span data-stu-id="b2005-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="b2005-105">Em seguida, selecione um código de disposição ou indique que os itens devolvidos precisam ser inspecionados.</span><span class="sxs-lookup"><span data-stu-id="b2005-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="b2005-106">Depois de completar essas etapas, você pode lançar o diário de entrada de item para a ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="b2005-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="b2005-107">Clique em **Gerenciamento de estoque** \> **Periódico** \> **Visão geral de entrada**.</span><span class="sxs-lookup"><span data-stu-id="b2005-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="b2005-108">No filtro **Nome de instalação**, selecione **Devolver ordem**.</span><span class="sxs-lookup"><span data-stu-id="b2005-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="b2005-109">Se a lista de recebimentos for longa, use os campos na área **Variação** para restringi-la.</span><span class="sxs-lookup"><span data-stu-id="b2005-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="b2005-110">Localize a linha da ordem de devolução que deseja lançar, selecione a caixa **Selecionar para entrada** correspondente e clique em **Iniciar entrada**.</span><span class="sxs-lookup"><span data-stu-id="b2005-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="b2005-111">Clique em **Diários** \> **Mostrar entradas a partir de recebimentos** para abrir o formulário **Diário de localização**.</span><span class="sxs-lookup"><span data-stu-id="b2005-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="b2005-112">Para exibir informações detalhadas, selecione um diário e clique em <STRONG>Linhas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b2005-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="b2005-113">Faça as atualizações necessárias e clique em **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="b2005-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="b2005-114">Depois que o diário é lançado, os itens devolvidos são registrados no estoque e o formulário **Devolver ordem** indica que os itens chegaram no depósito.</span><span class="sxs-lookup"><span data-stu-id="b2005-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2005-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b2005-115">See also</span></span>

<span data-ttu-id="b2005-116">[Diário de localização (formulário)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="b2005-116">[Location journal (form)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span></span>

  


