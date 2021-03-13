---
title: Não é possível criar um ambiente no Centro de administração do Power Apps
description: Este artigo explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft Power Apps.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 664c644c9b34e3489b4134040e165d26202dbd38
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111485"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="941dd-103">Não é possível criar um ambiente no Centro de administração do Power Apps</span><span class="sxs-lookup"><span data-stu-id="941dd-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="941dd-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="941dd-104">**Issue**</span></span>

- <span data-ttu-id="941dd-105">O locatário/administrador do ambiente não pode criar um ambiente no Centro de administração do Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="941dd-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="941dd-106">O usuário não tem uma licença que concede o direito de criar ambientes.</span><span class="sxs-lookup"><span data-stu-id="941dd-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="941dd-107">**Solução**</span><span class="sxs-lookup"><span data-stu-id="941dd-107">**Solution**</span></span>

<span data-ttu-id="941dd-108">Verifique se a administração do locatário atribuiu uma licença do Power Apps P2 válida ao usuário que está criando o ambiente.</span><span class="sxs-lookup"><span data-stu-id="941dd-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="941dd-109">Os seguintes planos de serviço do Microsoft Dynamics fornecem permissões para criar ambientes:</span><span class="sxs-lookup"><span data-stu-id="941dd-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="941dd-110">Unidade de manutenção de estoque (SKU) de produtos geral</span><span class="sxs-lookup"><span data-stu-id="941dd-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="941dd-111">Plano de serviço do Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="941dd-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="941dd-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="941dd-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="941dd-113">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="941dd-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="941dd-114">Microsoft Dynamics 365 plano Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="941dd-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="941dd-115">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="941dd-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="941dd-116">Observe que várias SKUs do Microsoft Office também oferecem o direito, junto com SKUs autônomas do plano 2 do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="941dd-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="941dd-117">O ponto importante é que um desses SKUs deve estar presente.</span><span class="sxs-lookup"><span data-stu-id="941dd-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="941dd-118">Acesse [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="941dd-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="941dd-119">Crie os ambientes seguindo as instruções em [Provisionar o Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="941dd-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
