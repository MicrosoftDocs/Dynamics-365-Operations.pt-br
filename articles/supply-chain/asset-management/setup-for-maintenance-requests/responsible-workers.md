---
title: Funcionários de manutenção responsáveis
description: Este tópico explica como configurar funcionários de manutenção responsáveis no Asset Management.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 113ee2b45c569c7dae3609f1027e31c4e5e5c54a
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3890072"
---
# <a name="responsible-maintenance-workers"></a><span data-ttu-id="cd396-103">Funcionários de manutenção responsáveis</span><span class="sxs-lookup"><span data-stu-id="cd396-103">Responsible maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="cd396-104">Os funcionários de manutenção responsáveis podem ser relacionados a tipos de ativo, ativos, locais funcionais, categorias de tipo de trabalho de manutenção, tipos de trabalho de manutenção, variações de tipo de trabalho de manutenção e comércios.</span><span class="sxs-lookup"><span data-stu-id="cd396-104">Responsible maintenance workers can be related to asset types, assets, functional locations, maintenance job type categories, maintenance job types, maintenance job type variants, and trades.</span></span> <span data-ttu-id="cd396-105">Eles podem ser usados em ordens de trabalho e em solicitações de manutenção para indicar uma preferência sobre os funcionários de manutenção que devem ser responsáveis por uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="cd396-105">They can be used on work orders and maintenance requests to indicate a preference about the maintenance workers who should be responsible for a work order.</span></span> <span data-ttu-id="cd396-106">(No entanto, esses funcionários de manutenção não são necessariamente os mesmos funcionários agendados para a realização da ordem de serviço). O uso dessa funcionalidade é opcional.</span><span class="sxs-lookup"><span data-stu-id="cd396-106">(However, those maintenance workers aren't necessarily the same workers who are scheduled to carry out the work order.) Use of this functionality is optional.</span></span> <span data-ttu-id="cd396-107">Por exemplo, pode ser usado para selecionar funcionários ou grupos de responsáveis para tipos de trabalho ou áreas de trabalho específicos.</span><span class="sxs-lookup"><span data-stu-id="cd396-107">For example, it can be used to select responsible workers or worker groups for specific work types or work areas.</span></span>

<span data-ttu-id="cd396-108">Durante o ciclo de vida da ordem de serviço ou um ciclo de vida de solicitação de manutenção, os funcionários de manutenção responsáveis podem ser alterados ou atualizados.</span><span class="sxs-lookup"><span data-stu-id="cd396-108">During a work order lifecycle or a maintenance request lifecycle, responsible maintenance workers can be changed or updated.</span></span> <span data-ttu-id="cd396-109">Essa alteração ou atualização pode ser relacionada a, por exemplo, uma alteração no estado de ciclo de vida de solicitação de manutenção ou o estado de ciclo de vida da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="cd396-109">This change or update might be related to, for example, a change in the maintenance request lifecycle state or the work order lifecycle state.</span></span>

<span data-ttu-id="cd396-110">A configuração na página **Funcionários de manutenção responsáveis** *não* é usada durante o agendamento da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="cd396-110">The setup on the **Responsible maintenance workers** page is *not* used during work order scheduling.</span></span>

> [!NOTE]
> <span data-ttu-id="cd396-111">No Asset Management, você também pode configurar os funcionários de manutenção *preferidos* que podem ser alocados a ordens de serviço durante o agendamento de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="cd396-111">In Asset Management, you can also set up *preferred* maintenance workers who might be allocated to work orders during work order scheduling.</span></span>

<span data-ttu-id="cd396-112">Antes de configurar funcionários de manutenção responsáveis, você deverá configurar os funcionários e grupos de funcionários de manutenção que devem estar disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="cd396-112">Before you can set up responsible maintenance workers, you must set up the workers and maintenance worker groups that should be available for selection.</span></span> <span data-ttu-id="cd396-113">Para obter informações sobre como configurar funcionários e grupos de funcionários de manutenção, consulte [Funcionários de manutenção e grupos de funcionários](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="cd396-113">For information about how to set up workers and maintenance worker groups, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-responsible-maintenance-workers"></a><span data-ttu-id="cd396-114">Configurar funcionários de manutenção responsáveis</span><span class="sxs-lookup"><span data-stu-id="cd396-114">Set up responsible maintenance workers</span></span>

1. <span data-ttu-id="cd396-115">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhadores** \> **Funcionários de manutenção responsáveis**.</span><span class="sxs-lookup"><span data-stu-id="cd396-115">Select **Asset management** \> **Setup** \> **Workers** \> **Responsible maintenance workers**.</span></span>
2. <span data-ttu-id="cd396-116">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="cd396-116">Select **New** to create a record.</span></span>
3. <span data-ttu-id="cd396-117">Primeiro, crie uma configuração de funcionário de manutenção responsável ou grupo de funcionários de manutenção responsáveis, onde você definirá somente o campo **Grupo de funcionários de manutenção responsáveis** e/ou o campo **Funcionário responsável**.</span><span class="sxs-lookup"><span data-stu-id="cd396-117">First create a default responsible maintenance worker or responsible maintenance worker group setup, where you set only the **Responsible maintenance worker group** field and/or the **Responsible worker** field.</span></span> <span data-ttu-id="cd396-118">Deixe os demais campos em branco.</span><span class="sxs-lookup"><span data-stu-id="cd396-118">Leave the remaining fields blank.</span></span> <span data-ttu-id="cd396-119">Essa configuração padrão será usada durante o agendamento da ordem de serviço caso nenhuma outra combinação mais específica corresponda ao conteúdo da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="cd396-119">This default setup will be used during work order scheduling if no other, more specific combination matches the contents of the work order.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cd396-120">Durante a criação de uma solicitação de manutenção, quando um funcionário de manutenção responsável ou grupo de funcionários de manutenção responsáveis for disponibilizado para seleção na página **Todas as solicitações de manutenção**, o Asset Management examina todos os registros de funcionário de manutenção responsável para verificar se há uma correspondência possível.</span><span class="sxs-lookup"><span data-stu-id="cd396-120">During creation of a maintenance request, when a responsible maintenance worker or responsible maintenance worker group is made available for selection on the **All maintenance requests** page, Asset Management goes through all responsible maintenance worker records to check for a possible match.</span></span> <span data-ttu-id="cd396-121">Ele sempre verifica a combinação mais específica primeiro.</span><span class="sxs-lookup"><span data-stu-id="cd396-121">It always checks the most specific combination first.</span></span> <span data-ttu-id="cd396-122">Ou seja, o Asset Management primeiro verifica a existência uma correspondência para o campo **Comércio**.</span><span class="sxs-lookup"><span data-stu-id="cd396-122">In other words, Asset Management first checks for a match for the **Trade** field.</span></span> <span data-ttu-id="cd396-123">Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Variação de tipo de trabalho de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="cd396-123">If no match is found, it checks for a match for the **Maintenance job type variant** field.</span></span> <span data-ttu-id="cd396-124">Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Variação de tipo de trabalho de manutenção** e assim em diante.</span><span class="sxs-lookup"><span data-stu-id="cd396-124">If no match is found, it checks for a match for the **Maintenance job type** field, and so on.</span></span> <span data-ttu-id="cd396-125">Como você pode perceber no layout da página, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência (primeiro **Comércio**, então **Variação de tipo de trabalho de manutenção**, **Tipo de trabalho de manutenção**, **Categoria de tipo de trabalho de manutenção**, **Local funcional**, **Ativo** e, por fim, **Tipo de ativo**).</span><span class="sxs-lookup"><span data-stu-id="cd396-125">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match (first **Trade**, then **Maintenance job type variant**, then **Maintenance job type**, then **Maintenance job type category**, then **Functional location**, then **Asset**, and finally **Asset type**).</span></span> <span data-ttu-id="cd396-126">Se nenhuma correspondência for encontrada, o registro padrão que não possui nenhuma seleção nos sete campos é usado.</span><span class="sxs-lookup"><span data-stu-id="cd396-126">If no match is found, the default record that has no selections in those seven fields is used.</span></span>

<span data-ttu-id="cd396-127">A ilustração a seguir mostra um exemplo da página **Funcionários de manutenção responsáveis**.</span><span class="sxs-lookup"><span data-stu-id="cd396-127">The following illustration shows an example of the **Responsible maintenance workers** page.</span></span>

![Página de funcionários de manutenção responsáveis](media/08-setup-for-requests.png)
