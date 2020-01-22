---
title: Não é possível criar um ambiente no Centro de administração do Power Apps
description: Este tópico explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7a66b7624655aaf976aaa63b2626f65c54d0ea38
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898797"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="8174a-103">Não é possível criar um ambiente no Centro de administração do Power Apps</span><span class="sxs-lookup"><span data-stu-id="8174a-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="8174a-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="8174a-104">**Issue**</span></span>

- <span data-ttu-id="8174a-105">O locatário/administrador do ambiente não pode criar um ambiente no Centro de administração do Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8174a-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="8174a-106">Uma licença que dá aos usuários o direito de realizar a etapa de criação de ambiente não foi atribuída diretamente ao usuário que está realizando essa etapa.</span><span class="sxs-lookup"><span data-stu-id="8174a-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="8174a-107">**Solução**</span><span class="sxs-lookup"><span data-stu-id="8174a-107">**Solution**</span></span>

<span data-ttu-id="8174a-108">Verifique se o administrador de locatários atribuiu uma licença válida do Power Apps P2 diretamente para o usuário que executará a etapa da criação do ambiente.</span><span class="sxs-lookup"><span data-stu-id="8174a-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="8174a-109">Estes são os planos de serviço do Microsoft Dynamics que oferecem esse direito.</span><span class="sxs-lookup"><span data-stu-id="8174a-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="8174a-110">Unidade de manutenção de estoque (SKU) de produto geral</span><span class="sxs-lookup"><span data-stu-id="8174a-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="8174a-111">Plano de serviço do Power Apps P2</span><span class="sxs-lookup"><span data-stu-id="8174a-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="8174a-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="8174a-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="8174a-113">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8174a-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="8174a-114">Microsoft Dynamics 365 plano Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="8174a-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="8174a-115">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8174a-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="8174a-116">Observe que várias SKUs do Microsoft Office também oferecem o direito, junto com SKUs autônomas do plano 2 do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8174a-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="8174a-117">O ponto importante é que um desses SKUs deve estar presente.</span><span class="sxs-lookup"><span data-stu-id="8174a-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="8174a-118">Acesse [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="8174a-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="8174a-119">Crie os ambientes seguindo as instruções em [Talent de provisão](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="8174a-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
