---
title: "Uso de catálogos externos para compras eletrônicas de PunchOut"
description: "Este tópico explica como você pode usar catálogos externos para criar e enviar requisições."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 0734db6f777de2bcd6ea024c9255f589c155e44f
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a><span data-ttu-id="5daee-103">Uso de catálogos externos para compras eletrônicas de PunchOut</span><span class="sxs-lookup"><span data-stu-id="5daee-103">Use external catalogs for PunchOut eProcurement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5daee-104">Ao usar catálogos externos para PunchOut e-procurement, você não precisa manter informações sobre os produtos de seus fornecedores em seus próprios dados mestre.</span><span class="sxs-lookup"><span data-stu-id="5daee-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="5daee-105">Em vez disso, o carrinho de compras no site de um fornecedor é convertido em linhas de requisição que possuem as informações corretas do produto.</span><span class="sxs-lookup"><span data-stu-id="5daee-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="5daee-106">Você deve evitar manter as descrições e os preços dos produtos dos seus fornecedores nos dados mestre do seu próprio produto.</span><span class="sxs-lookup"><span data-stu-id="5daee-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="5daee-107">Em vez disso, use catálogos externos para PunchOut e-procurement.</span><span class="sxs-lookup"><span data-stu-id="5daee-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="5daee-108">Então, quando os funcionários criam requisições, eles podem "ir" ao site do catálogo externo de um fornecedor (em outras palavras, eles saem do seu sistema e vão para o site do fornecedor).</span><span class="sxs-lookup"><span data-stu-id="5daee-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="5daee-109">Os produtos que são adicionados ao carrinho de compras no site do fornecedor podem então ser convertidos em linhas de requisição.</span><span class="sxs-lookup"><span data-stu-id="5daee-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="5daee-110">Portanto, você obtém as informações corretas do produto: identificação do produto, nome, preço e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="5daee-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="5daee-111">Para usar catálogos externos, um funcionário deverá criar uma requisição na página **Minhas requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="5daee-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="5daee-112">O funcionário que cria uma requisição é referido como o preparador da requisição.</span><span class="sxs-lookup"><span data-stu-id="5daee-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="5daee-113">Como preparador, você pode completar as seguintes tarefas.</span><span class="sxs-lookup"><span data-stu-id="5daee-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="5daee-114">Use a ação de linha **Catálogos externos** para abrir uma página que inclui todos catálogos externos disponíveis para o solicitante especificado, a entidade legal de compra, e a unidade operacional de recebimento.</span><span class="sxs-lookup"><span data-stu-id="5daee-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="5daee-115">Dependendo das suas permissões, altere o solicitante, a entidade legal de compra, e a unidade operacional de recebimento.</span><span class="sxs-lookup"><span data-stu-id="5daee-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="5daee-116">Uma alteração nesses valores pode alterar a lista de catálogos externos que estão disponíveis para um solicitante.</span><span class="sxs-lookup"><span data-stu-id="5daee-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="5daee-117">Os catálogos externos disponíveis dependem das políticas de compra ativas atuais para a entidade legal de compra ou a unidade operacional de recebimento.</span><span class="sxs-lookup"><span data-stu-id="5daee-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="5daee-118">Essas políticas podem permitir ou impedir o acesso a categorias específicas de aquisição.</span><span class="sxs-lookup"><span data-stu-id="5daee-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="5daee-119">Portanto, a lista de catálogos externos que são mapeados para essas categorias de compras pode ser afetada.</span><span class="sxs-lookup"><span data-stu-id="5daee-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="5daee-120">Para obter mais informações sobre as políticas, consulte [Políticas de compra](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5daee-120">For more information about policies, see [Purchasing policies](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="5daee-121">Para encontrar catálogos externos para categorias de contratos específicos, insira texto no campo de pesquisa do catálogo.</span><span class="sxs-lookup"><span data-stu-id="5daee-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="5daee-122">Para adicionar produtos do catálogo externo de um fornecedor no site do fornecedor, clique no catálogo externo.</span><span class="sxs-lookup"><span data-stu-id="5daee-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="5daee-123">Em seguida, adicione produtos ao carrinho de compras e confira. As linhas do carrinho de compras serão transferidas para o Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5daee-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="5daee-124">Se houver várias opções para categorias de compras, selecione a categoria de compras correta antes de adicionar as linhas à requisição.</span><span class="sxs-lookup"><span data-stu-id="5daee-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="5daee-125">Depois que as linhas foram adicionadas a uma requisição, você pode adicionar mais linhas sem usar catálogos externos.</span><span class="sxs-lookup"><span data-stu-id="5daee-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="5daee-126">Alternativamente, você pode continuar a usar catálogos externos para adicionar linhas.</span><span class="sxs-lookup"><span data-stu-id="5daee-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="5daee-127">Quando a requisição está pronta, use a ação **Fluxo de trabalho** > **Enviar** para enviar para a aprovação.</span><span class="sxs-lookup"><span data-stu-id="5daee-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

