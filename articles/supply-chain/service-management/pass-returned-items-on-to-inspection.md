---
title: Passar itens devolvidos para inspeção
description: Ao registrar um item devolvido, determine que o item deve ser enviado para inspeção antes de ser devolvido ao estoque ou descartado de alguma outra maneira.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04b27a5560b6126fde3028f653a89059bb765844
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254956"
---
# <a name="pass-returned-items-on-to-inspection"></a><span data-ttu-id="44ff6-103">Passar itens devolvidos para inspeção</span><span class="sxs-lookup"><span data-stu-id="44ff6-103">Pass returned items on to inspection</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="44ff6-104">Ao registrar um item devolvido, você pode determinar que o item deve ser enviado para inspeção antes de ser devolvido ao estoque ou descartado de alguma outra maneira.</span><span class="sxs-lookup"><span data-stu-id="44ff6-104">When registering a returned item, you may determine that an item should be sent for inspection before it is returned to inventory or disposed of in some other way.</span></span>

1.  <span data-ttu-id="44ff6-105">Clique em **Gerenciamento de estoque** \> **Diários** \> **Chegada de item** \> **Chegada de item**.</span><span class="sxs-lookup"><span data-stu-id="44ff6-105">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>
    
    <span data-ttu-id="44ff6-106">\-ou-</span><span class="sxs-lookup"><span data-stu-id="44ff6-106">\-or-</span></span>
    
    <span data-ttu-id="44ff6-107">Clique em **Gerenciamento de estoque** \> **Diários** \> **Chegada de item** \> **Entrada de produção**.</span><span class="sxs-lookup"><span data-stu-id="44ff6-107">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Production input**.</span></span>

2.  <span data-ttu-id="44ff6-108">No formulário **Diário de localização**, registre o recebimento de um item normalmente.</span><span class="sxs-lookup"><span data-stu-id="44ff6-108">On the **Location journal** form, register the receipt of an item as usual.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="44ff6-109">Para obter informações sobre como registrar o recebimento de itens devolvidos, consulte <A href="register-the-receipt-of-returned-items.md">Registrar o recebimento de itens devolvidos</A></span><span class="sxs-lookup"><span data-stu-id="44ff6-109">For information about registering the receipt of returned items, see <A href="register-the-receipt-of-returned-items.md">Register the receipt of returned items</A></span></span></P>



3.  <span data-ttu-id="44ff6-110">Na guia **Valores padrão**, na área **Modo de manuseio**, selecione a caixa **Gerenciamento de quarentena**.</span><span class="sxs-lookup"><span data-stu-id="44ff6-110">On the **Default values** tab, in the **Mode of handling** area, select the **Quarantine management** box.</span></span>

<span data-ttu-id="44ff6-111">Isso informará ao sistema para criar uma ordem de quarentena e a pessoa ou o departamento que realiza inspeções responderá a essa ordem usando o formulário **Ordem de quarentena**.</span><span class="sxs-lookup"><span data-stu-id="44ff6-111">This will prompt the system to create a quarantine order, and the person or department that performs inspections will respond to this order using the **Quarantine order** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="44ff6-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="44ff6-112">See also</span></span>

[<span data-ttu-id="44ff6-113">Submeter itens devolvidos à inspeção</span><span class="sxs-lookup"><span data-stu-id="44ff6-113">Take returned items through inspection</span></span>](take-returned-items-through-inspection.md)

[<span data-ttu-id="44ff6-114">Especificar o destino dos itens devolvidos</span><span class="sxs-lookup"><span data-stu-id="44ff6-114">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]