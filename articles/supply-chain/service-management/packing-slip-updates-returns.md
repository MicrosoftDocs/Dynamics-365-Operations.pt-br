---
title: Atualizações de guia de remessa para devoluções
description: Antes que os itens devolvidos possam ser recebidos no estoque, a guia de remessa da ordem ao qual pertencem deve ser atualizada.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a9b5c7e5726c36aa963e5750c63df20c1e2e6c35
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810693"
---
# <a name="packing-slip-updates-for-returns"></a><span data-ttu-id="15efe-103">Atualizações de guia de remessa para devoluções</span><span class="sxs-lookup"><span data-stu-id="15efe-103">Packing slip updates for returns</span></span>  

[!include [banner](../includes/banner.md)]


<span data-ttu-id="15efe-104">Antes que os itens devolvidos possam ser recebidos no estoque, a guia de remessa da ordem ao qual pertencem deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="15efe-104">Before returned items can be received into inventory, the packing slip for the order to which they belong must be updated.</span></span> <span data-ttu-id="15efe-105">Assim como o processo de atualização da fatura é a atualização da transação financeira, o processo de atualização da guia de remessa é a atualização física do registro do estoque, o que significa que ele efetua as alterações no estoque.</span><span class="sxs-lookup"><span data-stu-id="15efe-105">Just as the invoice update process is the update to the financial transaction, the packing slip update process is the physical update of the inventory record, which means that it commits the changes to inventory.</span></span> <span data-ttu-id="15efe-106">No caso de devoluções, as etapas atribuídas à ação de disposição são implementadas durante a atualização da guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="15efe-106">In the case of returns, the steps that are assigned to the disposition action are implemented during the packing slip update.</span></span>

<span data-ttu-id="15efe-107">A atualização da guia de remessa pode ser processada no diário de entrada de itens ou na ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="15efe-107">The packing slip update can be processed in either the item arrival journal or the return order.</span></span>

<span data-ttu-id="15efe-108">Como parte do processo de lançamento da guia de remessa, o número de referência da guia de remessa dos documentos de remessa do cliente pode ser associado opcionalmente às linhas de ordem.</span><span class="sxs-lookup"><span data-stu-id="15efe-108">As part of the process for posting packing slips, the packing slip reference number from the customer’s shipping documents can be associated with the order lines.</span></span> <span data-ttu-id="15efe-109">Essa associação é opcional e serve somente como referência.</span><span class="sxs-lookup"><span data-stu-id="15efe-109">This association is optional and for reference only.</span></span> <span data-ttu-id="15efe-110">Ela não cria nenhuma atualização transacional.</span><span class="sxs-lookup"><span data-stu-id="15efe-110">It does not create any transactional updates.</span></span>

<span data-ttu-id="15efe-111">Se nem todos os itens de devolução esperados foram recebidos, você deverá incluir somente a quantidade recebida na atualização da guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="15efe-111">If not all of the expected return items have arrived, you should include only the quantity that has been received in the packing slip update.</span></span> <span data-ttu-id="15efe-112">Deixe os itens restantes na ordem até que o resto da remessa de devolução seja recebida.</span><span class="sxs-lookup"><span data-stu-id="15efe-112">Leave the remaining items on the order until the rest of the return shipment has arrived.</span></span>

<span data-ttu-id="15efe-113">Se um item for devolvido da quarentena para o departamento de Remessa e Recebimento, como quando o inspetor de quarentena não sabe onde deve armazenar o item no estoque, a guia de remessa correspondente deverá ser atualizada de forma a registrar corretamente e agir no código de disposição especificado como resultado da quarentena.</span><span class="sxs-lookup"><span data-stu-id="15efe-113">If an item is sent back from quarantine to the Shipping and Receiving department, such as when the quarantine inspector does not know where to store the item in inventory, the corresponding packing slip must be updated to correctly register and act on the disposition code that is specified as a result of the quarantine.</span></span>

<span data-ttu-id="15efe-114">Ao atualizar uma guia de remessa de um item devolvido que é de um contrato de venda, o compromisso do contrato de venda para esse item é atualizado automaticamente de modo a refletir as alterações na quantidade ou no valor.</span><span class="sxs-lookup"><span data-stu-id="15efe-114">When you update a packing slip for a returned item that is from a sales agreement, the sales agreement commitment for that item is automatically updated to reflect the change in the quantity or the amount.</span></span> 

## <a name="see-also"></a><span data-ttu-id="15efe-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="15efe-115">See also</span></span>

[<span data-ttu-id="15efe-116">Executar atualizações de fatura para devoluções</span><span class="sxs-lookup"><span data-stu-id="15efe-116">Perform invoice updates for returns</span></span>](perform-invoice-updates-for-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]