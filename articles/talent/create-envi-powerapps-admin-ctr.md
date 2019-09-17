---
title: Não foi possível criar um ambiente na central de administração do PowerApps
description: Este tópico explica o que fazer se o administrador não conseguir criar um ambiente no Centro de administração do Microsoft PowerApps.
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
ms.openlocfilehash: 96119ca869cbbb15ed8d8d5d0fe3b0f94b5f36cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742833"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a><span data-ttu-id="abbad-103">Não é possível criar um ambiente no Centro de administração do PowerApps</span><span class="sxs-lookup"><span data-stu-id="abbad-103">Can't create an environment in the PowerApps Admin center</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="abbad-104">**Saída**</span><span class="sxs-lookup"><span data-stu-id="abbad-104">**Issue**</span></span>

- <span data-ttu-id="abbad-105">O locatário/administrador do ambiente não pode criar um ambiente no Centro de administração do Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="abbad-105">The tenant/environment admin can't create an environment in the Microsoft PowerApps Admin center.</span></span>
- <span data-ttu-id="abbad-106">Uma licença que dá aos usuários o direito de realizar a etapa de criação de ambiente não foi atribuída diretamente ao usuário que está realizando essa etapa.</span><span class="sxs-lookup"><span data-stu-id="abbad-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="abbad-107">**Solução**</span><span class="sxs-lookup"><span data-stu-id="abbad-107">**Solution**</span></span>

<span data-ttu-id="abbad-108">Verifique se o administrador do locatário recebeu uma licença válida do PowerApps P2 diretamente ao usuário que executará a etapa da criação de ordens.</span><span class="sxs-lookup"><span data-stu-id="abbad-108">Make sure that the tenant admin has assigned a valid PowerApps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="abbad-109">Estes são os planos de serviço do Microsoft Dynamics que oferecem esse direito.</span><span class="sxs-lookup"><span data-stu-id="abbad-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="abbad-110">Unidade de manutenção de estoque (SKU) de produto geral</span><span class="sxs-lookup"><span data-stu-id="abbad-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="abbad-111">Plano de serviço do PowerApps P2</span><span class="sxs-lookup"><span data-stu-id="abbad-111">PowerApps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="abbad-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="abbad-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="abbad-113">PowerApps para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="abbad-113">PowerApps for Dynamics 365</span></span> |
| <span data-ttu-id="abbad-114">Microsoft Dynamics 365 plano Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="abbad-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="abbad-115">PowerApps para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="abbad-115">PowerApps for Dynamics 365</span></span> |

<span data-ttu-id="abbad-116">Observe que várias SKUs do Microsoft Office também oferecem o direito, junto com SKUs autônomas do plano 2 do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="abbad-116">Note that various Microsoft Office SKUs also provide the right, together with standalone PowerApps Plan 2 SKUs.</span></span> <span data-ttu-id="abbad-117">O ponto importante é que um desses SKUs deve estar presente.</span><span class="sxs-lookup"><span data-stu-id="abbad-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="abbad-118">Acesse [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="abbad-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="abbad-119">Crie os ambientes seguindo as instruções em [Talent de provisão](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="abbad-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
