---
title: Ordens de serviço e ativos fixos
description: Este tópico explica as ordens de serviço e os ativos fixos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875498"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="1280f-103">Ordens de serviço e ativos fixos</span><span class="sxs-lookup"><span data-stu-id="1280f-103">Work orders and fixed assets</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="1280f-104">No Gerenciamento de Ativos, os ativos podem estar relacionados a ativos fixos, e podem criar ordens de serviço para esses ativos.</span><span class="sxs-lookup"><span data-stu-id="1280f-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="1280f-105">Se usar essa funcionalidade, você terá uma visão geral de ativos fixos, de projetos de investimento relacionados e dos custos registrados em projetos de investimento no módulo **Gerenciamento e contabilidade de projeto** e no módulo **Ativos fixos** do Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1280f-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs registered on the investment projects in the **Project management and accounting** module and the **Fixed assets** module in Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="1280f-106">O campo **Número de ativo fixo** só será preenchido no projeto de trabalho de ordem de serviço se o tipo "Investimento" for selecionado como o tipo de projeto no projeto de trabalho de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="1280f-106">The **Fixed asset number** field is only filled out on the work order job project if type "Investment" is selected as the project type on the work order job project.</span></span>

![Figura 1](media/24-work-orders.png)

<span data-ttu-id="1280f-108">O procedimento a seguir descreve a relação entre ativos, ordens de serviço, projetos de trabalho de ordem de serviço e ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="1280f-108">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="1280f-109">Você cria um ativo que relaciona a um ativo fixo, conforme mostra a figura abaixo.</span><span class="sxs-lookup"><span data-stu-id="1280f-109">You create an asset that you relate to a fixed asset, as shown in the figure below.</span></span>

![Figura 2](media/25-work-orders.png)

2. <span data-ttu-id="1280f-111">Quando configura os tipos de ordem de serviço (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Tipos de ordem de serviço**), você cria um tipo de ordem de serviço para lidar com investimentos.</span><span class="sxs-lookup"><span data-stu-id="1280f-111">When you set up work order types (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="1280f-112">Consulte também [Tipos de ordem de serviço](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="1280f-112">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![Figura 3](media/26-work-orders.png)

3. <span data-ttu-id="1280f-114">Quando configura grupos de projetos de ordem de serviço (link **Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto** > **Grupo de projetos**), você cria uma relação entre o tipo de ordem de serviço usado para investimentos no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Configuração** > **Lançamento** > **Grupos de projetos**).</span><span class="sxs-lookup"><span data-stu-id="1280f-114">When you set up work order project groups (**Asset management** > **Setup** > **Work orders** > **Project setup** > **Project group** link), you create a relation between the work order type used for investments and the project group created for investments in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![Figura 4](media/27-work-orders.png)

4. <span data-ttu-id="1280f-116">Quando cria uma ordem de serviço relacionada a um objeto de ativo fixo, você seleciona o tipo de ordem de serviço usado para lidar com investimentos, por exemplo, "Investimento".</span><span class="sxs-lookup"><span data-stu-id="1280f-116">When you create a work order that relates to a fixed asset object, you select the work order type used for handling investments, for example, "Investment".</span></span>

5. <span data-ttu-id="1280f-117">Quando a ordem de serviço for criada, o tipo de ordem de serviço relacionada é mostrado em **Todas as ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="1280f-117">When the work order is created, the related work order type is shown in **All work orders**.</span></span>

![Figura 5](media/28-work-orders.png)

6. <span data-ttu-id="1280f-119">Quando a ordem de serviço é criada, o projeto relacionado à ordem de serviço é criado em **Gerenciamento e contabilidade de projeto** > **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="1280f-119">When the work order is created, the project related to the work order is created in **Project management and accounting** > **All projects**.</span></span> <span data-ttu-id="1280f-120">Você verá informações relacionadas ao projeto clicando no link **ID do Projeto** na ordem de serviço (em **Gerenciamento de ativos**, abra a ordem de serviço na exibição Detalhes > **Detalhes da linha** Guia Rápida > guia **Geral** > campo **ID do Projeto**).</span><span class="sxs-lookup"><span data-stu-id="1280f-120">You can see project-related information by clicking the **Project ID** link on the work order (in **Asset management**, open the work order in Details view > **Line details** FastTab > **General** tab > **Project ID** field).</span></span>

![Figura 6](media/29-work-orders.png)

7. <span data-ttu-id="1280f-122">Em **Ativos fixos**, você terá uma visão geral dos projetos associados a um ativo fixo (**Ativos fixos** > **Ativos fixos** > **Ativos fixos** > clique no ativo fixo no campo **Número do ativo fixo** > exiba o conteúdo no painel **Informações relacionadas** > seção **Projetos associados**).</span><span class="sxs-lookup"><span data-stu-id="1280f-122">In **Fixed assets**, you are able to see an overview of the projects associated with a fixed asset (**Fixed assets** > **Fixed assets** > **Fixed assets** > click on the fixed asset in the **Fixed asset number** field > view the contents in the **Related information** pane > **Associated projects** section).</span></span>

