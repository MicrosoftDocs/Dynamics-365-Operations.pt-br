---
title: Ativos de vários níveis
description: Este tópico explica como criar e excluir ativos de vários níveis.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a69fd8b7d81700a62ae96d679372b1d6c8a70bbf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253197"
---
# <a name="multi-level-assets"></a><span data-ttu-id="46e21-103">Ativos de vários níveis</span><span class="sxs-lookup"><span data-stu-id="46e21-103">Multi-level assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="46e21-104">Este tópico explica como criar e excluir ativos de vários níveis.</span><span class="sxs-lookup"><span data-stu-id="46e21-104">This topic explains how to create and delete multi-level assets.</span></span> <span data-ttu-id="46e21-105">É possível criar ativos e subativos relacionados em uma estrutura de árvore hierárquica.</span><span class="sxs-lookup"><span data-stu-id="46e21-105">You can create assets and related sub-assets in a hierarchical tree structure.</span></span> <span data-ttu-id="46e21-106">Dessa forma, você pode mostrar as relações e dependências entre os ativos.</span><span class="sxs-lookup"><span data-stu-id="46e21-106">In this way, you can show relations and dependencies among assets.</span></span> <span data-ttu-id="46e21-107">Os trabalhos de manutenção podem ser relacionados a todos os níveis da estrutura de árvore.</span><span class="sxs-lookup"><span data-stu-id="46e21-107">Maintenance jobs can be related to all levels of the tree structure.</span></span> <span data-ttu-id="46e21-108">Também é possível criar estatísticas para um nível individual ou como uma soma de todos os níveis do ativo.</span><span class="sxs-lookup"><span data-stu-id="46e21-108">Statistics can also be created for an individual level or as a sum of all sub-asset levels.</span></span>

<span data-ttu-id="46e21-109">Na página da lista **Todos os ativos** (**Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos**), a coluna **Ativo** lista os ativos em ordem hierárquica.</span><span class="sxs-lookup"><span data-stu-id="46e21-109">On the **All Assets** list page (**Asset management** \> **Common** \> **Assets** \> **All assets**), the **Asset** column lists assets in hierarchical order.</span></span> <span data-ttu-id="46e21-110">A coluna **Responsável** mostra o responsável relacionado.</span><span class="sxs-lookup"><span data-stu-id="46e21-110">The **Parent** column shows the related parent.</span></span> <span data-ttu-id="46e21-111">Além disso, se os ativos e subativos já tiverem sido criados, a seção **Árvore de ativos** no painel **Informações relacionadas** mostrará os ativos em uma estrutura de árvore.</span><span class="sxs-lookup"><span data-stu-id="46e21-111">Additionally, if assets and sub-assets have already been created, the **Asset tree** section in the **Related information** pane shows the assets in a tree structure.</span></span>

<span data-ttu-id="46e21-112">Para obter informações sobre como criar um ativo, consulte [Criar um ativo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="46e21-112">For information about how to create an asset, see [Create an asset](../objects/create-an-object.md).</span></span> <span data-ttu-id="46e21-113">Para criar um subativo, selecione o ativo pai no campo **Ativo pai** da FastTab **Geral**.</span><span class="sxs-lookup"><span data-stu-id="46e21-113">To create a sub-asset, select the parent asset in the **Parent** field on the **General** FastTab.</span></span>

## <a name="copy-an-asset-or-asset-structure"></a><span data-ttu-id="46e21-114">Copiar um ativo ou uma estrutura de ativos</span><span class="sxs-lookup"><span data-stu-id="46e21-114">Copy an asset or asset structure</span></span>

<span data-ttu-id="46e21-115">Se sua empresa tiver diversas estruturas semelhantes de ativos, você poderá usar a função Copiar em Gerenciamento de ativos para criá-las rapidamente.</span><span class="sxs-lookup"><span data-stu-id="46e21-115">If your company has several similar asset structures, you can use the Copy function in Asset Management to quickly create them.</span></span>

1. <span data-ttu-id="46e21-116">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="46e21-116">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="46e21-117">Na página da lista **Todos os ativos**, selecione o ativo a ser copiado.</span><span class="sxs-lookup"><span data-stu-id="46e21-117">On the **All assets** list page, select the asset to copy.</span></span> <span data-ttu-id="46e21-118">Por exemplo, se você quiser copiar a estrutura de ativos inteira, incluindo os subativos, selecione um ativo pai.</span><span class="sxs-lookup"><span data-stu-id="46e21-118">For example, if you want to copy the whole asset structure, including sub-assets, select a parent asset.</span></span>
3. <span data-ttu-id="46e21-119">Selecione **Copiar ativo**.</span><span class="sxs-lookup"><span data-stu-id="46e21-119">Select **Copy asset**.</span></span> <span data-ttu-id="46e21-120">Na seção **Copiar de**, o campo **Ativo** é definido como o ativo selecionado na página da lista.</span><span class="sxs-lookup"><span data-stu-id="46e21-120">In the **Copy from** section, the **Asset** field is set to the asset that you selected on the list page.</span></span>
4. <span data-ttu-id="46e21-121">Na seção **Copiar para**, no campo **Ativo**, insira o nome do novo ativo.</span><span class="sxs-lookup"><span data-stu-id="46e21-121">In the **Copy to** section, in the **Asset** field, enter the name of the new asset.</span></span>
5. <span data-ttu-id="46e21-122">Caso o ativo que você está criando deva fazer parte de uma estrutura de ativos existente, na seção **Ativo pai**, no campo **Ativo**, selecione uma ID do ativo pai.</span><span class="sxs-lookup"><span data-stu-id="46e21-122">If the asset that you're creating should be part of an existing asset structure, in the **Parent asset** section, in the **Asset** field, select a parent ID.</span></span>
6. <span data-ttu-id="46e21-123">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="46e21-123">Select **OK**.</span></span> <span data-ttu-id="46e21-124">A nova estrutura de ativos será exibida na página **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="46e21-124">The new asset structure is shown on the **All assets** list page.</span></span> <span data-ttu-id="46e21-125">Todos os atributos de ativo, planos de serviço e rounds de manutenção relacionados ao ativo que você copiou serão transferidos para o novo ativo ou estrutura de ativos.</span><span class="sxs-lookup"><span data-stu-id="46e21-125">All asset attributes, maintenance plans, and maintenance rounds that are related to the asset that you copied are transferred to the new asset or asset structure.</span></span>

<span data-ttu-id="46e21-126">Ao copiar uma estrutura de ativos, os subativos da nova estrutura terão o mesmo nome dos subativos que você copiou.</span><span class="sxs-lookup"><span data-stu-id="46e21-126">When you copy an asset structure, the sub-assets in the new structure have the same name as the sub-assets that you copied.</span></span> <span data-ttu-id="46e21-127">Após concluir o procedimento de cópia, você poderá alterar facilmente o nome e outras configurações de um ativo.</span><span class="sxs-lookup"><span data-stu-id="46e21-127">After the copy procedure is completed, you can easily change the name and other settings for an asset.</span></span> <span data-ttu-id="46e21-128">Selecione o ativo na página **Todos os ativos**, e selecione o botão **Editar**.</span><span class="sxs-lookup"><span data-stu-id="46e21-128">Select the asset on the **All assets** list page, and then select the **Edit** button.</span></span>

> [!NOTE]
> <span data-ttu-id="46e21-129">Quando você copia um ativo ou uma estrutura de ativos, o estado do ciclo de vida dos novos ativos é redefinido para o estado que você definiu como o estado inicial do ciclo de vida dos ativos.</span><span class="sxs-lookup"><span data-stu-id="46e21-129">When you copy an asset or asset structure, the lifecycle state of the new assets is reset to whatever state you defined as the initial lifecycle state for assets.</span></span> <span data-ttu-id="46e21-130">O local funcional é redefinido para o local funcional padrão.</span><span class="sxs-lookup"><span data-stu-id="46e21-130">The functional location is reset to the default functional location.</span></span>

## <a name="delete-an-asset-or-asset-structure"></a><span data-ttu-id="46e21-131">Excluir um ativo ou uma estrutura de ativos</span><span class="sxs-lookup"><span data-stu-id="46e21-131">Delete an asset or asset structure</span></span>

<span data-ttu-id="46e21-132">Se um ativo tiver subativos relacionados, você só poderá excluí-lo se nenhuma solicitação de manutenção, ordem de trabalho, registro de falha ou avaliação de condição estiver registrado em qualquer um dos ativos.</span><span class="sxs-lookup"><span data-stu-id="46e21-132">If an asset has related sub-assets, you can delete it only if no maintenance requests, work order jobs, fault registrations, or condition assessments are registered on any of the assets.</span></span>

1. <span data-ttu-id="46e21-133">Na página da lista **Todos os ativos**, selecione o ativo a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="46e21-133">On the **All assets** list page, select the asset to delete.</span></span>
2. <span data-ttu-id="46e21-134">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="46e21-134">Select **Delete**.</span></span>

> [!NOTE]
> <span data-ttu-id="46e21-135">Se você não conseguir excluir um ativo usando este procedimento, outra maneira de excluir é configurar um estado do ciclo de vida do ativo pra essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="46e21-135">If you can't delete an asset by using this procedure, another way to handle deletion is to set up an asset lifecycle state for this purpose.</span></span> <span data-ttu-id="46e21-136">Por exemplo, é possível configurar um estado do ciclo de vida **Sucateado** ou **Excluído** na página **Estados do ciclo de vida do ativo**.</span><span class="sxs-lookup"><span data-stu-id="46e21-136">For example, you can set up a **Scrapped** or **Deleted** lifecycle state on the **Asset lifecycle states** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]