---
title: "Atualizações de guia de remessa para devoluções"
description: Antes que os itens devolvidos possam ser recebidos no estoque, a guia de remessa da ordem ao qual pertencem deve ser atualizada.
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 7532c5b1debdb498c2d6bab129208a412387c8fa
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="9256d-103">Atualizações de guia de remessa para devoluções</span><span class="sxs-lookup"><span data-stu-id="9256d-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9256d-104">Antes que os itens devolvidos possam ser recebidos no estoque, a guia de remessa da ordem ao qual pertencem deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="9256d-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="9256d-105">Assim como o processo de atualização da fatura é a atualização da transação financeira, o processo de atualização da guia de remessa é a atualização física do registro do estoque, o que significa que ele efetua as alterações no estoque.</span><span class="sxs-lookup"><span data-stu-id="9256d-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="9256d-106">No caso de devoluções, as etapas atribuídas à ação de disposição são implementadas durante a atualização da guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="9256d-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="9256d-107">A atualização da guia de remessa pode ser processada no diário de entrada de itens ou na ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="9256d-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="9256d-108">Como parte do processo de lançamento da guia de remessa, o número de referência da guia de remessa dos documentos de remessa do cliente pode ser associado opcionalmente às linhas de ordem.</span><span class="sxs-lookup"><span data-stu-id="9256d-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="9256d-109">Essa associação é opcional e serve somente como referência.</span><span class="sxs-lookup"><span data-stu-id="9256d-109">This association is optional and for reference only.</span></span> <span data-ttu-id="9256d-110">Ela não cria nenhuma atualização transacional.</span><span class="sxs-lookup"><span data-stu-id="9256d-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="9256d-111">Se nem todos os itens de devolução esperados foram recebidos, você deverá incluir somente a quantidade recebida na atualização da guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="9256d-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="9256d-112">Deixe os itens restantes na ordem até que o resto da remessa de devolução seja recebida.</span><span class="sxs-lookup"><span data-stu-id="9256d-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="9256d-113">Se um item for devolvido da quarentena para o departamento de Remessa e Recebimento, como quando o inspetor de quarentena não sabe onde deve armazenar o item no estoque, a guia de remessa correspondente deverá ser atualizada de forma a registrar corretamente e agir no código de disposição especificado como resultado da quarentena.</span><span class="sxs-lookup"><span data-stu-id="9256d-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="9256d-114">Ao atualizar uma guia de remessa de um item devolvido que é de um contrato de venda, o compromisso do contrato de venda para esse item é atualizado automaticamente de modo a refletir as alterações na quantidade ou no valor.</span><span class="sxs-lookup"><span data-stu-id="9256d-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="9256d-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9256d-115">See also</span></span>

[<span data-ttu-id="9256d-116">Executar atualizações de fatura para devoluções</span><span class="sxs-lookup"><span data-stu-id="9256d-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  



