---
title: Ordens de serviço e ativos fixos
description: Este tópico explica as ordens de serviço e os ativos fixos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c87a2b94692e279a9c2f35dc38ac87bfd9bf7d27
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626215"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="0dce5-103">Ordens de serviço e ativos fixos</span><span class="sxs-lookup"><span data-stu-id="0dce5-103">Work orders and fixed assets</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="0dce5-104">No Gerenciamento de Ativos, os ativos podem estar relacionados a ativos fixos, e podem criar ordens de serviço para esses ativos.</span><span class="sxs-lookup"><span data-stu-id="0dce5-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="0dce5-105">Se usar essa funcionalidade, você terá uma visão geral de ativos fixos, de projetos de investimento relacionados e dos custos que estão registrados em projetos de investimento nos módulos **Gerenciamento e contabilidade de projeto** e **Ativos fixos** do Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0dce5-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs that are registered on the investment projects in the **Project management and accounting** and **Fixed assets** modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="0dce5-106">O campo **Número de ativo fixo** só será configurado no projeto de trabalho de ordem de serviço se o tipo **Investimento** for selecionado como o tipo de projeto no projeto de trabalho de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0dce5-106">The **Fixed asset number** field on the work order job project is set only if **Investment** is selected as the project type on the work order job project.</span></span>

<span data-ttu-id="0dce5-107">A ilustração abaixo mostra a relação entre um projeto de investimento no módulo **Gerenciamento e contabilidade de projeto** e um projeto de trabalho de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="0dce5-107">The illustration below shows the relation between an investment project in the **Project management and accounting** module and a work order job project.</span></span>

![Figura 1](media/24-work-orders.png)

<span data-ttu-id="0dce5-109">O procedimento a seguir descreve a relação entre ativos, ordens de serviço, projetos de trabalho de ordem de serviço e ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="0dce5-109">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="0dce5-110">Você cria um ativo que será relacionado a um ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="0dce5-110">You create an asset that you relate to a fixed asset.</span></span>

![Figura 2](media/25-work-orders.png)

2. <span data-ttu-id="0dce5-112">Quando configura os tipos de ordem de serviço na página **Tipos de ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Tipos de ordem de serviço**), você cria um tipo de ordem de serviço para lidar com investimentos.</span><span class="sxs-lookup"><span data-stu-id="0dce5-112">When you set up work order types on the **Work order types** page (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="0dce5-113">Consulte também [Tipos de ordem de serviço](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="0dce5-113">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figura 3](media/26-work-orders.png)

3. <span data-ttu-id="0dce5-115">Quando configura grupos de projetos de ordem de serviço na guia **Grupo de projetos** da página **Configuração do projeto de ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto**), você cria uma relação entre o tipo de ordem de serviço que é usado para investimentos e o grupo de projetos que foi criado para investimentos na página **Grupos de projetos** no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Configuração** > **Lançamento** > **Grupos de projetos**).</span><span class="sxs-lookup"><span data-stu-id="0dce5-115">When you set up work order project groups on the **Project group** tab of the **Work order project setup** page (**Asset management** > **Setup** > **Work orders** > **Project setup**), you create a relation between the work order type that is used for investments and the project group that was created for investments on the **Project groups** page in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figura 4](media/27-work-orders.png)

4. <span data-ttu-id="0dce5-117">Ao criar uma ordem de serviço que está relacionada a um objeto de ativo fixo, você seleciona o tipo de ordem de serviço que é usado para tratar investimentos como, por exemplo, **Investimento**.</span><span class="sxs-lookup"><span data-stu-id="0dce5-117">When you create a work order that is related to a fixed asset, you select the work order type that is used to handle investments, such as **Investment**.</span></span>

5. <span data-ttu-id="0dce5-118">Quando a ordem de serviço é criada, o tipo de ordem de serviço relacionada será mostrado na página **Todas as ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="0dce5-118">When the work order is created, the related work order type is shown on the **All work orders** page.</span></span>

![Figura 5](media/28-work-orders.png)

6. <span data-ttu-id="0dce5-120">Quando a ordem de serviço é criada, o projeto que está relacionado à ordem de serviço é criado na página **Todos os projetos** no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Projetos** > **Todos os projetos**).</span><span class="sxs-lookup"><span data-stu-id="0dce5-120">When the work order is created, the project that is related to the work order is created on the **All projects** page in the **Project management and accounting** module (**Project management and accounting** > **Projects** > **All projects**).</span></span> <span data-ttu-id="0dce5-121">Para exibir as informações relacionadas ao projeto, selecione o link no campo **ID do projeto** na guia **Geral** na Guia Rápida **Detalhes da linha** na exibição de detalhes da página **Todas as ordens de serviço** no módulo **Gerenciamento de ativos** (**Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço**).</span><span class="sxs-lookup"><span data-stu-id="0dce5-121">To view project-related information, select the link in the **Project ID** field on the **General** tab on the **Line details** FastTab in the details view of the **All work orders** page in the **Asset management** module (**Asset management** > **Commom** > **Work orders** > **All work orders**).</span></span>

![Figura 6](media/29-work-orders.png)

7. <span data-ttu-id="0dce5-123">Para exibir uma visão geral dos projetos associados a um ativo fixo, selecione **Ativos fixos** > **Ativos fixos** > **Ativos fixos** e, em seguida, no campo **Número do ativo fixo**, selecione o link do ativo fixo para abrir a exibição de detalhes.</span><span class="sxs-lookup"><span data-stu-id="0dce5-123">To see an overview of the projects associated with a fixed asset, select **Fixed assets** > **Fixed assets** > **Fixed assets**, and then, in the **Fixed asset number** field, select the link for the fixed asset to open the details view.</span></span> <span data-ttu-id="0dce5-124">Expanda o painel **Informações relacionadas** do lado direito da página e selecione a Guia Rápida **Projetos associados**.</span><span class="sxs-lookup"><span data-stu-id="0dce5-124">Expand the **Related information** pane on the right side of the page, and select the **Associated projects** FastTab.</span></span>

