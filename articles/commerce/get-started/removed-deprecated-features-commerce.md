---
title: Recursos removidos ou obsoletos do Dynamics 365 Commerce
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335267"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="823e8-103">Recursos removidos ou obsoletos do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="823e8-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="823e8-104">Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="823e8-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="823e8-105">Um recurso *removido* não estará mais disponível no produto.</span><span class="sxs-lookup"><span data-stu-id="823e8-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="823e8-106">Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="823e8-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="823e8-107">Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento.</span><span class="sxs-lookup"><span data-stu-id="823e8-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="823e8-108">Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="823e8-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="823e8-109">Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.</span><span class="sxs-lookup"><span data-stu-id="823e8-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="823e8-110">Recursos removidos ou substituídos na versão 10.0.10 do Commerce</span><span class="sxs-lookup"><span data-stu-id="823e8-110">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="823e8-111">Operação PDV 803 - Separação e Recebimento</span><span class="sxs-lookup"><span data-stu-id="823e8-111">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="823e8-112">**Motivo para a reprovação/remoção**</span><span class="sxs-lookup"><span data-stu-id="823e8-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="823e8-113">As operações de separação e recebimento estão sendo preteridas devido à nova reestruturação da operação.</span><span class="sxs-lookup"><span data-stu-id="823e8-113">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="823e8-114">**Substituída por outro recurso?**</span><span class="sxs-lookup"><span data-stu-id="823e8-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="823e8-115">Sim.</span><span class="sxs-lookup"><span data-stu-id="823e8-115">Yes.</span></span> <span data-ttu-id="823e8-116">Ele é substituído por duas novas operações PDV: operação de entrada (804) e operação de saída (805).</span><span class="sxs-lookup"><span data-stu-id="823e8-116">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="823e8-117">**Áreas afetadas do produto**</span><span class="sxs-lookup"><span data-stu-id="823e8-117">**Product areas affected**</span></span>         | <span data-ttu-id="823e8-118">Aplicativo de ponto de venda (PDV)</span><span class="sxs-lookup"><span data-stu-id="823e8-118">Point of sale (POS) application</span></span> |
| <span data-ttu-id="823e8-119">**Opção de implantação**</span><span class="sxs-lookup"><span data-stu-id="823e8-119">**Deployment option**</span></span>              | <span data-ttu-id="823e8-120">Todas</span><span class="sxs-lookup"><span data-stu-id="823e8-120">All</span></span> |
| <span data-ttu-id="823e8-121">**Status**</span><span class="sxs-lookup"><span data-stu-id="823e8-121">**Status**</span></span>                         | <span data-ttu-id="823e8-122">Preterido: a partir da versão 10.0.10, a operação de separação e recebimento não receberá mais nenhuma atualização de recurso nova.</span><span class="sxs-lookup"><span data-stu-id="823e8-122">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="823e8-123">Somente correções críticas de bugs serão realizadas para esta operação em versões futuras.</span><span class="sxs-lookup"><span data-stu-id="823e8-123">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="823e8-124">Todos os clientes são incentivados a mudar para as novas [operações de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) e de [saída](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), o que continuará a ser parte de nosso roteiro de produtos de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="823e8-124">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="823e8-125">Recursos removidos ou substituídos na versão 10.0.7 do Commerce</span><span class="sxs-lookup"><span data-stu-id="823e8-125">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="823e8-126">API de GetProductAvailabilities e GetAvailableInventoryNearby comerciais</span><span class="sxs-lookup"><span data-stu-id="823e8-126">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="823e8-127">**Motivo para a reprovação/remoção**</span><span class="sxs-lookup"><span data-stu-id="823e8-127">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="823e8-128">APIs novas e otimizadas foram criadas para substituir APIs GetProductAvailabilities e GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="823e8-128">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="823e8-129">**Substituída por outro recurso?**</span><span class="sxs-lookup"><span data-stu-id="823e8-129">**Replaced by another feature?**</span></span>   | <span data-ttu-id="823e8-130">Sim: ele é substituído por APIs de GetEstimatedAvailabilty e GetEstimatedProductWarehouseAvailability.</span><span class="sxs-lookup"><span data-stu-id="823e8-130">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="823e8-131">**Áreas afetadas do produto**</span><span class="sxs-lookup"><span data-stu-id="823e8-131">**Product areas affected**</span></span>         | <span data-ttu-id="823e8-132">Aplicativo SDK de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="823e8-132">e-Commerce application SDK</span></span> |
| <span data-ttu-id="823e8-133">**Opção de implantação**</span><span class="sxs-lookup"><span data-stu-id="823e8-133">**Deployment option**</span></span>              | <span data-ttu-id="823e8-134">Todas</span><span class="sxs-lookup"><span data-stu-id="823e8-134">All</span></span> |
| <span data-ttu-id="823e8-135">**Status**</span><span class="sxs-lookup"><span data-stu-id="823e8-135">**Status**</span></span>                         | <span data-ttu-id="823e8-136">Preterido: a partir da versão 10.0.7, não terão mais investimentos em engenharia feitos para GetProductAvailabilities e GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="823e8-136">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="823e8-137">As organizações que usam essas APIs em suas implantações de comércio eletrônico devem ser convertidas em novas APIs de GetEstimatedAvailability e GetEstimatedProductWarehouseAvailability e habilitar o [Recurso de cálculo de disponibilidade de produtos otimizados](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="823e8-137">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="823e8-138">Comunicados anteriores sobre recursos removidos ou obsoletos</span><span class="sxs-lookup"><span data-stu-id="823e8-138">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="823e8-139">Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="823e8-139">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
