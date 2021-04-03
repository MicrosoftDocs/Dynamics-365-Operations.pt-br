---
title: Estão faltando produtos e categorias após a cópia do ambiente
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando produtos e categorias estiverem faltando depois que um local for copiado entre ambientes ou no mesmo ambiente.
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
ms.openlocfilehash: 35f2cbd98a91149395f40bf821c1d5d7e58eaf77
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585203"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="0eac7-103">Estão faltando produtos e categorias após a cópia do ambiente</span><span class="sxs-lookup"><span data-stu-id="0eac7-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0eac7-104">Este tópico fornece orientações de solução de problemas que podem ajudar quando produtos e categorias estiverem faltando depois que um local for copiado entre ambientes ou no mesmo ambiente.</span><span class="sxs-lookup"><span data-stu-id="0eac7-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="0eac7-105">descrição</span><span class="sxs-lookup"><span data-stu-id="0eac7-105">Description</span></span>

<span data-ttu-id="0eac7-106">Depois que um site é copiado de um ambiente para outro, ou no mesmo ambiente, os produtos e as categorias estão faltando no site.</span><span class="sxs-lookup"><span data-stu-id="0eac7-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="0eac7-107">Os produtos e as categorias estarão faltando na vitrine de comércio eletrônico e na guia **Produtos** no construtor de sites do Commerce.</span><span class="sxs-lookup"><span data-stu-id="0eac7-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="0eac7-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="0eac7-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="0eac7-109">Mapear o número da unidade operacional do canal para um site recém copiado no construtor de sites do Commerce</span><span class="sxs-lookup"><span data-stu-id="0eac7-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="0eac7-110">Para mapear o número da unidade operacional (OUN) do canal para um site recém copiado no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0eac7-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="0eac7-111">Selecione o site recém copiado.</span><span class="sxs-lookup"><span data-stu-id="0eac7-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="0eac7-112">Em **Configurações do site**, selecione **Canais**.</span><span class="sxs-lookup"><span data-stu-id="0eac7-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="0eac7-113">Ao lado do nome do canal, selecione as reticências (**...**) e selecione **Alterar canal da loja online**.</span><span class="sxs-lookup"><span data-stu-id="0eac7-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="0eac7-114">Na caixa de diálogo **Alterar canal da loja online**, selecione o canal a ser mapeado para o site recém copiado e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0eac7-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="0eac7-115">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="0eac7-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0eac7-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0eac7-116">Additional resources</span></span>

[<span data-ttu-id="0eac7-117">Associar um site do Dynamics 365 Commerce a um canal online</span><span class="sxs-lookup"><span data-stu-id="0eac7-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
