---
title: Imposto integrado
description: Este tópico descreve a integração de dados de impostos entre o Finance and Operations e o Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 86e74086a5a74c7af5f2572d1a653a1658d729c0
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853850"
---
# <a name="integrated-tax"></a><span data-ttu-id="096e6-103">Imposto integrado</span><span class="sxs-lookup"><span data-stu-id="096e6-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="096e6-104">Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="096e6-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="096e6-105">Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.</span><span class="sxs-lookup"><span data-stu-id="096e6-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="096e6-106">Modelos</span><span class="sxs-lookup"><span data-stu-id="096e6-106">Templates</span></span>

<span data-ttu-id="096e6-107">Os dados de imposto incluem um conjunto de mapas de entidades que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="096e6-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="096e6-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="096e6-108">Finance and Operations</span></span>   | <span data-ttu-id="096e6-109">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="096e6-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="096e6-110">Códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="096e6-110">Tax codes</span></span>                  | <span data-ttu-id="096e6-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="096e6-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="096e6-112">Grupos de impostos</span><span class="sxs-lookup"><span data-stu-id="096e6-112">Tax groups</span></span>               | <span data-ttu-id="096e6-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="096e6-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="096e6-114">Grupos de itens de impostos</span><span class="sxs-lookup"><span data-stu-id="096e6-114">Tax item groups</span></span>          | <span data-ttu-id="096e6-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="096e6-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="096e6-116">Isenções de impostos</span><span class="sxs-lookup"><span data-stu-id="096e6-116">Tax Exemptions</span></span>           | <span data-ttu-id="096e6-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="096e6-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="096e6-118">Autoridades fiscais</span><span class="sxs-lookup"><span data-stu-id="096e6-118">Tax Authorities</span></span>          | <span data-ttu-id="096e6-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="096e6-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="096e6-120">Códigos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="096e6-120">Withholding tax codes</span></span>      | <span data-ttu-id="096e6-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="096e6-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="096e6-122">Grupos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="096e6-122">Withholding tax groups</span></span>   | <span data-ttu-id="096e6-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="096e6-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="096e6-124">Grupo de contas contábeis de imposto</span><span class="sxs-lookup"><span data-stu-id="096e6-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="096e6-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="096e6-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

