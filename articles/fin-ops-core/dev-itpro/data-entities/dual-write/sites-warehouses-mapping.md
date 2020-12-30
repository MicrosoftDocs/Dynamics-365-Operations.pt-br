---
title: Sites e depósitos integrados
description: Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Dataverse.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: d192343d78f9248e4d1232d6aee1a1f800383805
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679311"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="58dc7-103">Sites e depósitos integrados</span><span class="sxs-lookup"><span data-stu-id="58dc7-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="58dc7-104">Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="58dc7-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="58dc7-105">Sites e depósitos operacionais são conceitos comuns em um aplicativo do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58dc7-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="58dc7-106">Eles são usados para modelar a cadeia de fornecedores da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="58dc7-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="58dc7-107">Modelos</span><span class="sxs-lookup"><span data-stu-id="58dc7-107">Templates</span></span>

<span data-ttu-id="58dc7-108">A integração com o Dataverse disponibiliza esses conceitos e todas as informações relacionadas no Dataverse por meio das tabelas de dados de site e depósito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="58dc7-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="58dc7-109">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58dc7-109">Finance and Operations apps</span></span> | <span data-ttu-id="58dc7-110">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="58dc7-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="58dc7-111">descrição</span><span class="sxs-lookup"><span data-stu-id="58dc7-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="58dc7-112">Sites</span><span class="sxs-lookup"><span data-stu-id="58dc7-112">Sites</span></span> | <span data-ttu-id="58dc7-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="58dc7-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="58dc7-114">Depósitos</span><span class="sxs-lookup"><span data-stu-id="58dc7-114">Warehouses</span></span> | <span data-ttu-id="58dc7-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="58dc7-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

