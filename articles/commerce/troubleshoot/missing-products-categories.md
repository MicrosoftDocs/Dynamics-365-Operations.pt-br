---
title: Estão faltando produtos e categorias após a cópia do ambiente
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando produtos e categorias estiverem faltando depois que um local for copiado entre ambientes ou no mesmo ambiente.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022389"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="fe785-103">Estão faltando produtos e categorias após a cópia do ambiente</span><span class="sxs-lookup"><span data-stu-id="fe785-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fe785-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando produtos e categorias estiverem faltando depois que um local for copiado entre ambientes ou no mesmo ambiente.</span><span class="sxs-lookup"><span data-stu-id="fe785-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="fe785-105">descrição</span><span class="sxs-lookup"><span data-stu-id="fe785-105">Description</span></span>

<span data-ttu-id="fe785-106">Depois que um site é copiado de um ambiente para outro, ou no mesmo ambiente, os produtos e as categorias estão faltando no site.</span><span class="sxs-lookup"><span data-stu-id="fe785-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="fe785-107">Os produtos e as categorias estarão faltando na vitrine de comércio eletrônico e na guia **Produtos** no construtor de sites do Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe785-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="fe785-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="fe785-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="fe785-109">Mapear o número da unidade operacional do canal para um site recém copiado no construtor de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="fe785-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="fe785-110">Para mapear o número da unidade operacional (OUN) do canal para um site recém copiado no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fe785-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="fe785-111">Selecione o site recém copiado.</span><span class="sxs-lookup"><span data-stu-id="fe785-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="fe785-112">Em **Configurações do site**, selecione **Canais**.</span><span class="sxs-lookup"><span data-stu-id="fe785-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="fe785-113">Ao lado do nome do canal, selecione as reticências (**...**) e selecione **Alterar canal da loja online**.</span><span class="sxs-lookup"><span data-stu-id="fe785-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="fe785-114">Na caixa de diálogo **Alterar canal da loja online**, selecione o canal a ser mapeado para o site recém copiado e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe785-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="fe785-115">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="fe785-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fe785-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="fe785-116">Additional resources</span></span>

[<span data-ttu-id="fe785-117">Associar um site do Dynamics 365 Commerce a um canal online</span><span class="sxs-lookup"><span data-stu-id="fe785-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
