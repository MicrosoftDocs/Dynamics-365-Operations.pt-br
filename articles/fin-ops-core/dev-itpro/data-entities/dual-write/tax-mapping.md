---
title: Imposto integrado
description: Este tópico descreve a integração de dados do imposto entre o Finance and Operations e o Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a7992520b57b4c19b6dc8e13bd8e9ffc87b40f5a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750633"
---
# <a name="integrated-tax"></a><span data-ttu-id="aa7a7-103">Imposto integrado</span><span class="sxs-lookup"><span data-stu-id="aa7a7-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="aa7a7-104">Os dados de configuração de imposto definem a configuração para os impostos indiretos (IVA, GST, imposto) e imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="aa7a7-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="aa7a7-105">Eles descrevem as regras de cálculo de impostos, taxa de imposto, contabilidade de imposto, liquidação e outros conceitos.</span><span class="sxs-lookup"><span data-stu-id="aa7a7-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="aa7a7-106">Modelos</span><span class="sxs-lookup"><span data-stu-id="aa7a7-106">Templates</span></span>

<span data-ttu-id="aa7a7-107">Os dados de imposto incluem um conjunto de mapas de tabelas que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="aa7a7-107">Tax data includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="aa7a7-108">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="aa7a7-108">Finance and Operations apps</span></span> | <span data-ttu-id="aa7a7-109">Aplicativos controlados por modelos no Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="aa7a7-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="aa7a7-110">descrição</span><span class="sxs-lookup"><span data-stu-id="aa7a7-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="aa7a7-111">Grupo de impostos do item</span><span class="sxs-lookup"><span data-stu-id="aa7a7-111">Item sales tax group</span></span> | <span data-ttu-id="aa7a7-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="aa7a7-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="aa7a7-113">Autoridades do imposto</span><span class="sxs-lookup"><span data-stu-id="aa7a7-113">Sales tax authorities</span></span> | <span data-ttu-id="aa7a7-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="aa7a7-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="aa7a7-115">CDS de entidade de código de isenção de imposto</span><span class="sxs-lookup"><span data-stu-id="aa7a7-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="aa7a7-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="aa7a7-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="aa7a7-117">Grupos de impostos</span><span class="sxs-lookup"><span data-stu-id="aa7a7-117">Sales tax groups</span></span> | <span data-ttu-id="aa7a7-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="aa7a7-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="aa7a7-119">Grupos de lançamentos contábeis de imposto V2</span><span class="sxs-lookup"><span data-stu-id="aa7a7-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="aa7a7-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="aa7a7-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="aa7a7-121">Códigos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="aa7a7-121">Withholding tax codes</span></span> | <span data-ttu-id="aa7a7-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="aa7a7-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="aa7a7-123">Grupos de impostos retidos na fonte</span><span class="sxs-lookup"><span data-stu-id="aa7a7-123">Withholding tax groups</span></span> | <span data-ttu-id="aa7a7-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="aa7a7-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]