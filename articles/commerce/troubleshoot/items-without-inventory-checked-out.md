---
title: Pode ocorrer a finalização da compra para itens sem estoque
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando os clientes podem adicionar itens de indisponibilidade de estoque ao seu carrinho de compras e prosseguir para finalização da compra.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6df9c77248c7f4e16765b98327fe5838f0fce7e4
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585193"
---
# <a name="items-without-inventory-can-be-checked-out"></a><span data-ttu-id="98118-103">Pode ocorrer a finalização da compra para itens sem estoque</span><span class="sxs-lookup"><span data-stu-id="98118-103">Items without inventory can be checked out</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="98118-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando os clientes podem adicionar itens de indisponibilidade de estoque ao seu carrinho de compras e prosseguir para finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="98118-104">This topic provides troubleshooting guidance that can help when customers can add out-of-stock items to their cart and proceed to checkout.</span></span>

## <a name="description"></a><span data-ttu-id="98118-105">descrição</span><span class="sxs-lookup"><span data-stu-id="98118-105">Description</span></span>

<span data-ttu-id="98118-106">Os usuários podem adicionar um item ao seu carrinho, mesmo que não haja estoque disponível na loja e, em seguida, prosseguir para a página de finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="98118-106">Users can add an item to their cart, even though there is no on-hand inventory in the store, and then proceed to the checkout page.</span></span>

## <a name="resolution"></a><span data-ttu-id="98118-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="98118-107">Resolution</span></span>

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a><span data-ttu-id="98118-108">Habilitar a propriedade Mostrar Erros de Estoque Insuficiente no construtor de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="98118-108">Enable the Show Out Of Stock Errors property in Commerce site builder</span></span>

<span data-ttu-id="98118-109">Para ativar a propriedade **Mostrar Erros de Estoque Insuficiente** no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="98118-109">To enable the **Show Out Of Stock Errors** property in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="98118-110">Selecione o site no qual você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="98118-110">Select the site that you're working on.</span></span>
1. <span data-ttu-id="98118-111">No painel de navegação à esquerda, selecione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="98118-111">In the left navigation, select **Pages**.</span></span>
1. <span data-ttu-id="98118-112">Selecione **CartPage** para abri-la.</span><span class="sxs-lookup"><span data-stu-id="98118-112">Select **CartPage** to open it.</span></span>
1. <span data-ttu-id="98118-113">Selecione o slot **Carrinho 1**, selecione **Editar** e, no painel Propriedades, marque a caixa de seleção **Mostrar Erros de Estoque Insuficiente**.</span><span class="sxs-lookup"><span data-stu-id="98118-113">Select the **Cart 1** slot, select **Edit**, and then, in the properties pane, select the **Show Out Of Stock Errors** check box.</span></span>
1. <span data-ttu-id="98118-114">Salve e publique a página.</span><span class="sxs-lookup"><span data-stu-id="98118-114">Save and publish the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98118-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="98118-115">Additional resources</span></span>

[<span data-ttu-id="98118-116">Aplicar configurações de estoque</span><span class="sxs-lookup"><span data-stu-id="98118-116">Apply inventory settings</span></span>](../inventory-settings.md)

[<span data-ttu-id="98118-117">Calcular disponibilidade de estoque para canais de varejo</span><span class="sxs-lookup"><span data-stu-id="98118-117">Calculate inventory availability for retail channels</span></span>](../calculated-inventory-retail-channels.md)

[<span data-ttu-id="98118-118">Configurar buffers de estoque e níveis de estoque</span><span class="sxs-lookup"><span data-stu-id="98118-118">Configure inventory buffers and inventory levels</span></span>](../inventory-buffers-levels.md)
