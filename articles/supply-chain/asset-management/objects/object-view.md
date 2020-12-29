---
title: Exibir ativo
description: Este tópico descreve a exibição de ativos no Asset Management.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc4cd9ada9c1f64b434cd657eb5f5654c1328ef4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422318"
---
# <a name="asset-view"></a><span data-ttu-id="88ace-103">Exibir ativo</span><span class="sxs-lookup"><span data-stu-id="88ace-103">Asset view</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="88ace-104">Este tópico descreve a exibição de ativos no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="88ace-104">This topic describes the asset view in Asset Management.</span></span> <span data-ttu-id="88ace-105">A página **Exibição de ativos** mostra os ativos e locais funcionais em uma exibição de árvore.</span><span class="sxs-lookup"><span data-stu-id="88ace-105">The **Asset view** page shows active assets and functional locations in a tree view.</span></span> <span data-ttu-id="88ace-106">Portanto, você pode obter com facilidade uma visão geral das relações de ativos a locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="88ace-106">Therefore, you can easily get an overview of asset relations to functional locations.</span></span> <span data-ttu-id="88ace-107">Além disso, você pode exibir informações detalhadas sobre locais funcionais, ativos e listas de materiais (BOMs) relacionadas.</span><span class="sxs-lookup"><span data-stu-id="88ace-107">Additionally, you can view detailed information about functional locations, assets, and related bills of materials (BOMs).</span></span> <span data-ttu-id="88ace-108">Você também pode obter uma rápida visão geral de solicitações de manutenção ativa e ordens de serviço relacionadas a um ativo.</span><span class="sxs-lookup"><span data-stu-id="88ace-108">You can also get a quick overview of active maintenance requests and work orders that are related to an asset.</span></span>

1. <span data-ttu-id="88ace-109">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Exibição de ativos**.</span><span class="sxs-lookup"><span data-stu-id="88ace-109">Select **Asset management** \> **Common** \> **Assets** \> **Asset view**.</span></span>
2. <span data-ttu-id="88ace-110">Para alterar a exibição mostrada na página, selecione um novo valor no campo **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="88ace-110">To change the view that is shown on the page, select a new value in the **View** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="88ace-111">A exibição padrão que é mostrada quando você abre a página **Exibição de ativos** depende do valor selecionado no campo **Exibir** na guia **Ativos** da página **Parâmetros de gerenciamento de ativos** (**Gerenciamento de ativos** \> **Configuração** \> **Parâmetros de gerenciamento de ativos**).</span><span class="sxs-lookup"><span data-stu-id="88ace-111">The default view that is shown when you open the **Asset view** page depends on the value that is selected in the **View** field on the **Assets** tab of the **Asset management parameters** page (**Asset management** \> **Setup** \> **Asset management parameters**).</span></span>

<span data-ttu-id="88ace-112">No lado direito da página, as Guias Rápidas mostram detalhes de exibição selecionada.</span><span class="sxs-lookup"><span data-stu-id="88ace-112">On the right side of the page, FastTabs shows details of the selected view.</span></span>

<span data-ttu-id="88ace-113">A trilha de navegação que aparece acima da exibição de árvore mostra a seleção atual na exibição de árvore.</span><span class="sxs-lookup"><span data-stu-id="88ace-113">The breadcrumb trail that appears above the tree view shows the current selection in the tree view.</span></span> <span data-ttu-id="88ace-114">Essa trilha de navegação usa o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="88ace-114">This breadcrumb trail uses the following format:</span></span>

<span data-ttu-id="88ace-115">ID de local funcional/ID de local funcional (se houver mais de um local funcional) \> ID do Ativo/ID do Ativo (se houver mais de um ativo) - número de item.</span><span class="sxs-lookup"><span data-stu-id="88ace-115">Functional location ID / Functional location ID (if there is more than one functional location) \> Asset ID / Asset ID (if there is more than one asset) - Item number.</span></span>

<span data-ttu-id="88ace-116">Se tiver selecionado um ativo na exibição de árvore, você poderá selecionar **Solicitações ativos** ou **Ordens de serviço ativas** para exibir as solicitações de manutenção ou ordens de serviço relacionadas ao ativo.</span><span class="sxs-lookup"><span data-stu-id="88ace-116">If you've selected an asset in the tree view, you can select **Active requests** or **Active work orders** to view the maintenance requests or work orders that are related to the asset.</span></span> <span data-ttu-id="88ace-117">Você também pode selecionar **Abrir** \> **Localização funcional**, **Ativo** ou **BOM de ativos** para abrir a exibição relacionada.</span><span class="sxs-lookup"><span data-stu-id="88ace-117">You can also select **Open** \> **Functional location**, **Asset**, or **Asset BOM** to open the related view.</span></span>

<span data-ttu-id="88ace-118">A opção **Locais funcionais de ativo** que você pode selecionar no campo **Exibir** também está disponível em uma pesquisa de ativos onde você pode selecionar um ativo.</span><span class="sxs-lookup"><span data-stu-id="88ace-118">The **Asset functional locations** option that you can select in the **View** field is also available in any asset lookup where you can select an asset.</span></span> <span data-ttu-id="88ace-119">O modo de exibição de árvore é mostrado em uma guia **Exibição de ativos**, por exemplo, onde você [cria um ativo](../objects/create-an-object.md), cria uma solicitação de manutenção ou cria uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="88ace-119">The tree view is shown on an **Asset view** tab, for example, where you [create an asset](../objects/create-an-object.md), create a maintenance request, or create a work order.</span></span>
