---
title: Imposto integrado
description: Este tópico descreve a integração de dados do imposto entre o Finance and Operations e o Common Data Service.
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
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173076"
---
# <a name="integrated-tax"></a><span data-ttu-id="3f366-103">Imposto integrado</span><span class="sxs-lookup"><span data-stu-id="3f366-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="3f366-104">Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="3f366-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="3f366-105">Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.</span><span class="sxs-lookup"><span data-stu-id="3f366-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="3f366-106">Modelos</span><span class="sxs-lookup"><span data-stu-id="3f366-106">Templates</span></span>

<span data-ttu-id="3f366-107">Os dados de imposto incluem um conjunto de mapas de entidades que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f366-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="3f366-108">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3f366-108">Finance and Operations apps</span></span> | <span data-ttu-id="3f366-109">Aplicativos controlados por modelos no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3f366-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="3f366-110">descrição</span><span class="sxs-lookup"><span data-stu-id="3f366-110">Description</span></span> |
-------------------------|---------------------------------
<span data-ttu-id="3f366-111">Códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="3f366-111">Tax codes</span></span>                   | <span data-ttu-id="3f366-112">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="3f366-112">msdyn\_taxcodes.md</span></span> | 
<span data-ttu-id="3f366-113">Grupos de impostos</span><span class="sxs-lookup"><span data-stu-id="3f366-113">Tax groups</span></span>                 | <span data-ttu-id="3f366-114">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="3f366-114">msdyn\_taxgroups.md</span></span> | 
<span data-ttu-id="3f366-115">Grupos de itens de impostos</span><span class="sxs-lookup"><span data-stu-id="3f366-115">Tax item groups</span></span>             | <span data-ttu-id="3f366-116">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="3f366-116">msdyn\_taxitemgroups.md</span></span> | 
<span data-ttu-id="3f366-117">Isenções de impostos</span><span class="sxs-lookup"><span data-stu-id="3f366-117">Tax Exemptions</span></span>             | <span data-ttu-id="3f366-118">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="3f366-118">msdyn\_taxexemptcodes.md</span></span> | 
<span data-ttu-id="3f366-119">Autoridades fiscais</span><span class="sxs-lookup"><span data-stu-id="3f366-119">Tax Authorities</span></span>             | <span data-ttu-id="3f366-120">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="3f366-120">msdyn\_taxauthorities.md</span></span> | 
<span data-ttu-id="3f366-121">Códigos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="3f366-121">Withholding tax codes</span></span>       | <span data-ttu-id="3f366-122">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="3f366-122">msdyn\_withholdingtaxcodes.md</span></span> | 
<span data-ttu-id="3f366-123">Grupos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="3f366-123">Withholding tax groups</span></span>     | <span data-ttu-id="3f366-124">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="3f366-124">msdyn\_withholdingtaxgroups.md</span></span> | 
<span data-ttu-id="3f366-125">Grupo de contas contábeis de imposto</span><span class="sxs-lookup"><span data-stu-id="3f366-125">Tax Ledger Account Group</span></span> | <span data-ttu-id="3f366-126">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="3f366-126">msdyn\_taxpostinggroups</span></span>     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

