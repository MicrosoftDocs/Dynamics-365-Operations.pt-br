---
title: "Monitorar o estoque de consignação usando a colaboração de fornecedor"
description: "Este procedimento mostra como usar a colaboração de fornecedor para ver as informações sobre o nível de estoque de produtos que você fez na remessa com um cliente."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 567be29bd9989b3471b22d5a970ed0e51e4549ec
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a><span data-ttu-id="8241f-103">Monitorar o estoque de consignação usando a colaboração de fornecedor</span><span class="sxs-lookup"><span data-stu-id="8241f-103">Monitor consignment inventory using vendor collaboration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8241f-104">Este procedimento mostra como usar a colaboração de fornecedor para ver as informações sobre o nível de estoque de produtos que você fez na remessa com um cliente.</span><span class="sxs-lookup"><span data-stu-id="8241f-104">This procedure shows how to use vendor collaboration to see information about the stock level of product that you have placed in consignment with a customer.</span></span> <span data-ttu-id="8241f-105">Também é possível monitorar o consumo de estoque quando o cliente tem a propriedade do estoque.</span><span class="sxs-lookup"><span data-stu-id="8241f-105">You can also monitor the consumption of the stock when the customer takes ownership of the inventory.</span></span> <span data-ttu-id="8241f-106">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="8241f-106">You can use this procedure in the USMF demo data company.</span></span> <span data-ttu-id="8241f-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="8241f-107">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="view-consumed-inventory"></a><span data-ttu-id="8241f-108">Exibir estoque consumido</span><span class="sxs-lookup"><span data-stu-id="8241f-108">View consumed inventory</span></span>
1. <span data-ttu-id="8241f-109">Vá para Colaboração do fornecedor > Estoque de consignação > Produtos recebidos de estoque de consignação.</span><span class="sxs-lookup"><span data-stu-id="8241f-109">Go to Vendor collaboration > Consignment inventory > Products received from consignment inventory.</span></span>
    * <span data-ttu-id="8241f-110">A lista mostra as linhas do recebimento de produtos geradas quando a propriedade do estoque foi alterada de remessa do fornecedor para o cliente.</span><span class="sxs-lookup"><span data-stu-id="8241f-110">The list shows the product receipt lines that were generated when ownership of the consignment inventory was changed from the vendor to the customer.</span></span> <span data-ttu-id="8241f-111">Pode ser necessário rolar à direita para consultar as quantidades e outras informações.</span><span class="sxs-lookup"><span data-stu-id="8241f-111">You might have to scroll to the right to see quantities and other information.</span></span> <span data-ttu-id="8241f-112">Você pode usar informações nesta lista para gerar notas fiscais para o cliente.</span><span class="sxs-lookup"><span data-stu-id="8241f-112">You can use the information in this list to generate invoices for your customer.</span></span> <span data-ttu-id="8241f-113">Você também pode exportar os dados para o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="8241f-113">You can also export the data to Microsoft Excel.</span></span>   
2. <span data-ttu-id="8241f-114">Clique em Visualizar ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="8241f-114">Click View purchase order.</span></span>
3. <span data-ttu-id="8241f-115">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="8241f-115">Expand the Line details section.</span></span>
    * <span data-ttu-id="8241f-116">A linha é marcada como a remessa e, na seção do cabeçalho que mostra a ordem de compra tiver um status de recebimento.</span><span class="sxs-lookup"><span data-stu-id="8241f-116">The line is marked as Consignment, and the header section shows that the purchase order has a status of Received.</span></span>  
4. <span data-ttu-id="8241f-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8241f-117">Close the page.</span></span>

## <a name="view-on-hand-inventory"></a><span data-ttu-id="8241f-118">Exibir estoque disponível</span><span class="sxs-lookup"><span data-stu-id="8241f-118">View on-hand inventory</span></span>
1. <span data-ttu-id="8241f-119">Vá para Colaboração do fornecedor > Estoque de consignação > Estoque de consignação disponível.</span><span class="sxs-lookup"><span data-stu-id="8241f-119">Go to Vendor collaboration > Consignment inventory > On-hand consignment inventory.</span></span>
    * <span data-ttu-id="8241f-120">Disponível a página de remessa de estoque mostra o estoque que você possui em depósito de cliente.</span><span class="sxs-lookup"><span data-stu-id="8241f-120">The On-hand consignment inventory page shows the stock that you own at the customer’s warehouse.</span></span> <span data-ttu-id="8241f-121">Você pode mostrar dimensões adicionais, como o site e o depósito, clique na guia dimensões de exibição.</span><span class="sxs-lookup"><span data-stu-id="8241f-121">You can show additional dimensions, such as the site and warehouse, by clicking the Display dimensions tab.</span></span>   

