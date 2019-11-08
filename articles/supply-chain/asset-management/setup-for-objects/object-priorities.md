---
title: Níveis de serviço do ativo
description: Este tópico explica níveis de serviço do ativo no Asset Management.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1e2f8d2ac0c48d4f92b15ec345ffa650b71df0b
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571015"
---
# <a name="asset-service-levels"></a><span data-ttu-id="03172-103">Níveis de serviço do ativo</span><span class="sxs-lookup"><span data-stu-id="03172-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="03172-104">Este tópico explica níveis de serviço do ativo no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="03172-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="03172-105">Os níveis de serviço de ativos estão relacionados a ativos, e são transferidos para solicitações de manutenção e ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="03172-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="03172-106">Eles são usados para calcular a prioridade de ordens de serviço durante o agendamento da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="03172-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="03172-107">Os níveis de serviço de ativo podem ser alterados, se alterações forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="03172-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="03172-108">Para obter mais informações sobre a configuração relacionadas ao cálculo de pontuações de classificação para o agendamento da ordem de serviço, consulte [Parâmetros de gerenciamento de ativos](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="03172-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="03172-109">Você deve configurar pelo menos um registro padrão para o nível de serviço de ativo.</span><span class="sxs-lookup"><span data-stu-id="03172-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="03172-110">Esse registro padrão será usado se nenhuma outra correspondência for encontrada durante o agendamento da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="03172-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="03172-111">**Exemplo 1:** o nível de serviço padrão usado caso nenhuma outra correspondência seja encontrada.</span><span class="sxs-lookup"><span data-stu-id="03172-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="03172-112">Nesse registro, você seleciona apenas um nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="03172-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="03172-113">**Exemplo 2:** um serviço de alto nível usado para agendar trabalhos para o motor de um caminhão Volvo.</span><span class="sxs-lookup"><span data-stu-id="03172-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="03172-114">Nesse registro, você seleciona um tipo de ativo relevante (por exemplo, **Motor de Caminhão**), um fabricante (**Volvo**) e um nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="03172-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="03172-115">Configurar níveis de serviço de ativo</span><span class="sxs-lookup"><span data-stu-id="03172-115">Set up asset service levels</span></span>

1. <span data-ttu-id="03172-116">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Níveis de serviço de ativo**.</span><span class="sxs-lookup"><span data-stu-id="03172-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="03172-117">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="03172-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="03172-118">Dependendo do nível de detalhes necessários para o nível de serviço do ativo, faça seleções relevantes nos campos **Local funcional**, **Tipo de ativo**, **Fabricante**, **Modelo**, **Ativo**, **Tipo de ordem de serviço** e **Nível de serviço**.</span><span class="sxs-lookup"><span data-stu-id="03172-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03172-119">Quando o nível de serviço de ativo é usado para solicitações de manutenção e ordens de serviço, o Asset Management examina todos os registros de nível de serviço de ativos para verificar se há uma possível correspondência.</span><span class="sxs-lookup"><span data-stu-id="03172-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="03172-120">Ele sempre verifica a combinação mais específica primeiro.</span><span class="sxs-lookup"><span data-stu-id="03172-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="03172-121">Ou seja, o Asset Management primeiro verifica a existência uma correspondência para o campo **Tipo de ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="03172-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="03172-122">Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Ativo** e assim em diante.</span><span class="sxs-lookup"><span data-stu-id="03172-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="03172-123">Como você pode perceber no layout da página **Níveis de serviço de ativo**, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="03172-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="03172-124">Se nenhuma correspondência for encontrada, o registro padrão que não possui nenhuma seleção nos campos é usado.</span><span class="sxs-lookup"><span data-stu-id="03172-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="03172-125">No campo **Nível de serviço**, selecione um número que indique o nível de serviço (prioridade).</span><span class="sxs-lookup"><span data-stu-id="03172-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="03172-126">Se você alterar um registro de nível de serviço de ativo na página **Níveis de serviço de ativo** depois de já tê-lo usado em uma ordem de serviço, o nível de serviço em solicitações de manutenção e ordens de serviço não será atualizado de forma correspondente.</span><span class="sxs-lookup"><span data-stu-id="03172-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>
