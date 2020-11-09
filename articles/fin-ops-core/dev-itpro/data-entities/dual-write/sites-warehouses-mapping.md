---
title: Sites e depósitos integrados
description: Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Common Data Service.
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
ms.openlocfilehash: d5c2030160f6025c9de63b2c29215364f5f87e6f
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997615"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="786f6-103">Sites e depósitos integrados</span><span class="sxs-lookup"><span data-stu-id="786f6-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="786f6-104">Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="786f6-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="786f6-105">Sites e depósitos operacionais são conceitos comuns em um aplicativo do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="786f6-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="786f6-106">Eles são usados para modelar a cadeia de fornecedores da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="786f6-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="786f6-107">Modelos</span><span class="sxs-lookup"><span data-stu-id="786f6-107">Templates</span></span>

<span data-ttu-id="786f6-108">A integração com o Common Data Service disponibiliza esses conceitos e todas as informações relacionadas no Common Data Service por meio das entidades de dados de site e depósito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="786f6-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="786f6-109">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="786f6-109">Finance and Operations apps</span></span> | <span data-ttu-id="786f6-110">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="786f6-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="786f6-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="786f6-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="786f6-112">Sites</span><span class="sxs-lookup"><span data-stu-id="786f6-112">Sites</span></span> | <span data-ttu-id="786f6-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="786f6-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="786f6-114">Depósitos</span><span class="sxs-lookup"><span data-stu-id="786f6-114">Warehouses</span></span> | <span data-ttu-id="786f6-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="786f6-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

