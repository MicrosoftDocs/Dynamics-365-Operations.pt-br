---
title: Não é possível criar um ambiente no Centro de administração do Power Apps
description: Este artigo explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft Power Apps.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73c8910900ba6486a8e60a547b07ea0c82a6cb10
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053338"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="1123f-103">Não é possível criar um ambiente no Centro de administração do Power Apps</span><span class="sxs-lookup"><span data-stu-id="1123f-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1123f-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="1123f-104">**Issue**</span></span>

- <span data-ttu-id="1123f-105">O locatário/administrador do ambiente não pode criar um ambiente no Centro de administração do Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1123f-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="1123f-106">O usuário não tem uma licença que concede o direito de criar ambientes.</span><span class="sxs-lookup"><span data-stu-id="1123f-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="1123f-107">**Solução**</span><span class="sxs-lookup"><span data-stu-id="1123f-107">**Solution**</span></span>

<span data-ttu-id="1123f-108">Verifique se a administração do locatário atribuiu uma licença do Power Apps P2 válida ao usuário que está criando o ambiente.</span><span class="sxs-lookup"><span data-stu-id="1123f-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="1123f-109">Os seguintes planos de serviço do Microsoft Dynamics fornecem permissões para criar ambientes:</span><span class="sxs-lookup"><span data-stu-id="1123f-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="1123f-110">Unidade de manutenção de estoque (SKU) de produtos geral</span><span class="sxs-lookup"><span data-stu-id="1123f-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="1123f-111">Plano de serviço do Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="1123f-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="1123f-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="1123f-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="1123f-113">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1123f-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="1123f-114">Microsoft Dynamics 365 plano Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="1123f-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="1123f-115">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1123f-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="1123f-116">Observe que várias SKUs do Microsoft Office também oferecem o direito, junto com SKUs autônomas do plano 2 do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1123f-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="1123f-117">O ponto importante é que um desses SKUs deve estar presente.</span><span class="sxs-lookup"><span data-stu-id="1123f-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="1123f-118">Acesse [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="1123f-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="1123f-119">Crie os ambientes seguindo as instruções em [Provisionar o Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="1123f-119">Create the environments by following the instructions in [Provision Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]