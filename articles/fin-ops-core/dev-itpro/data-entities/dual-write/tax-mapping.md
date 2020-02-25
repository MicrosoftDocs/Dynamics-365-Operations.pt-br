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
ms.openlocfilehash: 0d32a5f7859f0200da823a73d94b9a6b2a9c8e7d
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019636"
---
# <a name="integrated-tax"></a><span data-ttu-id="dd710-103">Imposto integrado</span><span class="sxs-lookup"><span data-stu-id="dd710-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="dd710-104">Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="dd710-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="dd710-105">Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.</span><span class="sxs-lookup"><span data-stu-id="dd710-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="dd710-106">Modelos</span><span class="sxs-lookup"><span data-stu-id="dd710-106">Templates</span></span>

<span data-ttu-id="dd710-107">Os dados de imposto incluem um conjunto de mapas de entidades que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="dd710-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="dd710-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dd710-108">Finance and Operations</span></span>   | <span data-ttu-id="dd710-109">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="dd710-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="dd710-110">Códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="dd710-110">Tax codes</span></span>                  | <span data-ttu-id="dd710-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="dd710-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="dd710-112">Grupos de impostos</span><span class="sxs-lookup"><span data-stu-id="dd710-112">Tax groups</span></span>               | <span data-ttu-id="dd710-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="dd710-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="dd710-114">Grupos de itens de impostos</span><span class="sxs-lookup"><span data-stu-id="dd710-114">Tax item groups</span></span>          | <span data-ttu-id="dd710-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="dd710-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="dd710-116">Isenções de impostos</span><span class="sxs-lookup"><span data-stu-id="dd710-116">Tax Exemptions</span></span>           | <span data-ttu-id="dd710-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="dd710-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="dd710-118">Autoridades fiscais</span><span class="sxs-lookup"><span data-stu-id="dd710-118">Tax Authorities</span></span>          | <span data-ttu-id="dd710-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="dd710-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="dd710-120">Códigos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="dd710-120">Withholding tax codes</span></span>      | <span data-ttu-id="dd710-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="dd710-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="dd710-122">Grupos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="dd710-122">Withholding tax groups</span></span>   | <span data-ttu-id="dd710-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="dd710-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="dd710-124">Grupo de contas contábeis de imposto</span><span class="sxs-lookup"><span data-stu-id="dd710-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="dd710-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="dd710-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

