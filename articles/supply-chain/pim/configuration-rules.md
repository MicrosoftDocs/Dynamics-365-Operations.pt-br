---
title: "Regras de configuração"
description: "Este artigo oferece informações gerais sobre as regras de configuração. As regras de configuração definem as relações entre os itens em uma lista de materiais (BOM) de produtos que usam a tecnologia de configuração baseada em dimensão."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: bc8e606cdc0bc5a45321c67ce9b089059f226df2
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---

# <a name="configuration-rules"></a><span data-ttu-id="dc55b-104">Regras de configuração</span><span class="sxs-lookup"><span data-stu-id="dc55b-104">Configuration rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="dc55b-105">Este artigo oferece informações gerais sobre as regras de configuração.</span><span class="sxs-lookup"><span data-stu-id="dc55b-105">This article provides general information about configuration rules.</span></span> <span data-ttu-id="dc55b-106">As regras de configuração definem as relações entre os itens em uma lista de materiais (BOM) de produtos que usam a tecnologia de configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="dc55b-106">Configuration rules define relationships between items in a bill of materials (BOM) for products that use the dimension-based configuration technology.</span></span>

<span data-ttu-id="dc55b-107">As regras de configuração ficam disponíveis quando você define modelos de configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="dc55b-107">Configuration rules are available when you define dimension-based configuration models.</span></span> <span data-ttu-id="dc55b-108">As regras de configuração são usadas para aplicar ou proibir combinações específicas do item em uma lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="dc55b-108">Configuration rules are used to either enforce or prohibit specific item combinations in a bill of materials (BOM).</span></span> <span data-ttu-id="dc55b-109">Depois que uma BOM for criada e os itens relevantes forem atribuídos aos seus respectivos grupos de configuração, uma ou mais regras de configuração poderão ser definidas.</span><span class="sxs-lookup"><span data-stu-id="dc55b-109">After a BOM has been created and the relevant items have been assigned to their respective configuration groups, one or more configuration rules can be defined.</span></span> <span data-ttu-id="dc55b-110">Se dois itens pertencem, o operador **Select** será usado para garantir a inclusão.</span><span class="sxs-lookup"><span data-stu-id="dc55b-110">If two items belong together, the **Select** operator is used to ensure inclusion.</span></span> <span data-ttu-id="dc55b-111">Se dois itens forem mutuamente exclusivos, o operador, **Cancelar seleção** será usado para garantir a exclusão.</span><span class="sxs-lookup"><span data-stu-id="dc55b-111">If two items are mutually exclusive, the **Deselect** operator is used to ensure exclusion.</span></span>  

<span data-ttu-id="dc55b-112">**Observação:** Essas informações só se aplicam aos produtos mestres que usam a tecnologia de configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="dc55b-112">**Note:** This information applies only to product masters that use the dimension-based configuration technology.</span></span>  

<span data-ttu-id="dc55b-113">As configurações existentes não são afetadas pelas alterações subsequentes às regras de configuração.</span><span class="sxs-lookup"><span data-stu-id="dc55b-113">Existing configurations aren't affected by subsequent changes to the configuration rules.</span></span> <span data-ttu-id="dc55b-114">Porém, é importante que você defina as regras antes de estabelecer uma nova configuração e que as verifique, caso presuma que as regras tenham sido alteradas.</span><span class="sxs-lookup"><span data-stu-id="dc55b-114">However, it's important that you set the rules before you define a new configuration, and that you check the rules if you think they have been changed.</span></span>  

<span data-ttu-id="dc55b-115">**Observação:** Para o método **Select**, o grupo de configuração, o número do item e a configuração resultantes são automaticamente selecionados.</span><span class="sxs-lookup"><span data-stu-id="dc55b-115">**Note:** For the **Select** method, the derived configuration group, item number, and configuration are automatically selected.</span></span> <span data-ttu-id="dc55b-116">Para o método **Cancelar seleção**, o grupo de configurações, o número do item e a configuração resultantes não podem ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="dc55b-116">For the **Deselect** method, the derived configuration group, item number, and configuration can't be selected.</span></span>

<a name="see-also"></a><span data-ttu-id="dc55b-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dc55b-117">See also</span></span>
--------

[<span data-ttu-id="dc55b-118">Configuração de produto baseada em dimensão</span><span class="sxs-lookup"><span data-stu-id="dc55b-118">Dimension-based product configuration</span></span>](dimension-based-product-configuration.md)




