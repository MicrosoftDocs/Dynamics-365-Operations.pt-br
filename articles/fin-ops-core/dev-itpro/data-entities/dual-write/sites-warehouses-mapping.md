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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 1b9181211bbb65cdfc46e63f3cee0e9f5bc9f6a4
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173053"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="2e3bb-103">Sites e depósitos integrados</span><span class="sxs-lookup"><span data-stu-id="2e3bb-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="2e3bb-104">Este tópico descreve a integração de dados do site e do depósito entre o Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="2e3bb-105">Sites e depósitos operacionais são conceitos comuns em um aplicativo do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="2e3bb-106">Eles são usados para modelar a cadeia de fornecedores da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="2e3bb-107">Modelos</span><span class="sxs-lookup"><span data-stu-id="2e3bb-107">Templates</span></span>

<span data-ttu-id="2e3bb-108">A integração com o Common Data Service disponibiliza esses conceitos e todas as informações relacionadas no Common Data Service por meio das entidades de dados de site e depósito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="2e3bb-109">Aplicativos Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2e3bb-109">Finance and Operations apps</span></span> | <span data-ttu-id="2e3bb-110">Outros aplicativos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2e3bb-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="2e3bb-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e3bb-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="2e3bb-112">Sites</span><span class="sxs-lookup"><span data-stu-id="2e3bb-112">Sites</span></span> | <span data-ttu-id="2e3bb-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="2e3bb-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="2e3bb-114">Depósitos</span><span class="sxs-lookup"><span data-stu-id="2e3bb-114">Warehouses</span></span> | <span data-ttu-id="2e3bb-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="2e3bb-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

