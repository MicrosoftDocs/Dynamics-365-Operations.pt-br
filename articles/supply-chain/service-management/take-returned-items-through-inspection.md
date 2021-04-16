---
title: Submeter itens devolvidos à inspeção
description: Submeter itens devolvidos à inspeção.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d782e9bf4793e2c6d1ef8b334d3bfc3bb729ad31
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824314"
---
# <a name="take-returned-items-through-inspection"></a><span data-ttu-id="53e55-103">Submeter itens devolvidos à inspeção</span><span class="sxs-lookup"><span data-stu-id="53e55-103">Take returned items through inspection</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="53e55-104">Clique em **Gerenciamento de estoque** \> **Periódico** \> **Gerenciamento de qualidade** \> **Ordens de quarentena**.</span><span class="sxs-lookup"><span data-stu-id="53e55-104">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="53e55-105">Localize a linha da ordem que corresponde ao item devolvido que está sendo inspecionado.</span><span class="sxs-lookup"><span data-stu-id="53e55-105">Locate the order line that corresponds to the returned item that you are inspecting.</span></span>

    > [!NOTE]
    > <P><span data-ttu-id="53e55-106">Uma ordem de quarentena pode ser associada apenas a um único número de item.</span><span class="sxs-lookup"><span data-stu-id="53e55-106">A quarantine order can be associated with just a single item number.</span></span> <span data-ttu-id="53e55-107">Se 10 itens com números de item diferentes forem devolvidos em uma única remessa e enviados para quarentena, 10 ordens de quarentena separadas serão criadas.</span><span class="sxs-lookup"><span data-stu-id="53e55-107">If 10 items that have different item numbers are returned in a single shipment and sent to quarantine, 10 individual quarantine orders are created.</span></span></P>

3.  <span data-ttu-id="53e55-108">Depois de examinar o item, faça uma seleção no campo **Código de disposição** para indicar o que deve ser feito com o item e como tratar a transação financeira relacionada.</span><span class="sxs-lookup"><span data-stu-id="53e55-108">After examining the item, make a selection in the **Disposition code** field to indicate what should be done with the item and how to handle the related financial transaction.</span></span> <span data-ttu-id="53e55-109">Exemplos incluem devolver item ao estoque e o reembolsar o cliente, transformar o item em sucata e enviar uma substituição para o cliente, ou devolver o item ao cliente sem crédito.</span><span class="sxs-lookup"><span data-stu-id="53e55-109">Examples include returning the item to stock and refunding the customer, scrapping the item and sending a replacement to the customer, or returning the item to the customer without credit.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="53e55-110">Se vários itens devolvidos em um único lote de número de itens não puderem receber o mesmo código de disposição, você deverá dividir a ordem de quarentena (<STRONG>Funções</STRONG> &gt; <STRONG>Dividir</STRONG>) para atribuir um código de disposição diferente para cada sub-lote.</span><span class="sxs-lookup"><span data-stu-id="53e55-110">If multiple returned items in a single item number batch cannot be assigned the same disposition code, you must split the quarantine order (<STRONG>Functions</STRONG> &gt; <STRONG>Split</STRONG>) to assign a different disposition code to each sub-batch.</span></span></P>


4.  <span data-ttu-id="53e55-111">Quando tiver terminado a inspeção, clique em **Relatório de conclusão** para liberar os itens devolvidos e criar uma entrada no diário de entrada de itens.</span><span class="sxs-lookup"><span data-stu-id="53e55-111">When you are finished with the inspection, click **Report as finished** to release the returned items and create an item arrival journal entry.</span></span> <span data-ttu-id="53e55-112">A pessoa ou o departamento que receber os itens processará o diário para os itens a serem devolvidos para o estoque.</span><span class="sxs-lookup"><span data-stu-id="53e55-112">The person or department that receives the items then processes the journal for the items to be returned to inventory.</span></span>
    
    <span data-ttu-id="53e55-113">–ou–</span><span class="sxs-lookup"><span data-stu-id="53e55-113">–or–</span></span>
    
    <span data-ttu-id="53e55-114">Termine a ordem de quarentena e mova os itens diretamente para o estoque usando uma das funções de **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="53e55-114">End the quarantine order, and move the items back into inventory directly by using one of the **Inventory** functions.</span></span>

5.  <span data-ttu-id="53e55-115">Feche o formulário para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="53e55-115">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="53e55-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="53e55-116">See also</span></span>

[<span data-ttu-id="53e55-117">Especificar o destino dos itens devolvidos</span><span class="sxs-lookup"><span data-stu-id="53e55-117">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]