---
title: Mover, substituir e instalar ativos
description: Este tópico explica como mover, substituir e instalar ativos no Asset Management.
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
ms.openlocfilehash: c0e6306698d351d33cae627e3741ad9a2eb6d893
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783081"
---
# <a name="move-replace-and-install-assets"></a><span data-ttu-id="66e2a-103">Mover, substituir e instalar ativos</span><span class="sxs-lookup"><span data-stu-id="66e2a-103">Move, replace, and install assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="66e2a-104">Este tópico explica como mover, substituir e instalar ativos no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="66e2a-104">This topic explains how to move, replace, and install assets in Asset Management.</span></span> <span data-ttu-id="66e2a-105">Você pode criar ativos individuais sem relações com outros ativos, ou pode criar uma estrutura de ativos com um ativo pai (ativo de nível superior) e ativos secundários relacionados (subativos).</span><span class="sxs-lookup"><span data-stu-id="66e2a-105">You can create individual assets that have no relations to other assets, or you can create an asset structure that includes a parent asset (top-level asset) and related child assets (sub-assets).</span></span> <span data-ttu-id="66e2a-106">No Asset Management, há três abordagens para mover e alterar o local de um ativo:</span><span class="sxs-lookup"><span data-stu-id="66e2a-106">In Asset Management, there are three approaches to moving and changing the location of an asset:</span></span>

- <span data-ttu-id="66e2a-107">**Mover** – mova um ativo para outra estrutura de ativos ou para outro local na mesma estrutura de ativos.</span><span class="sxs-lookup"><span data-stu-id="66e2a-107">**Move** – Move an asset either to another asset structure or to another location in the same asset structure.</span></span>
- <span data-ttu-id="66e2a-108">**Substituir** – remova temporariamente um ativo de uma estrutura de ativos para que ele possa ser reparado ou reformado, e então adicione o ativo reformado de volta à estrutura de ativos.</span><span class="sxs-lookup"><span data-stu-id="66e2a-108">**Replace** – Temporarily remove an asset from an asset structure so that it can be repaired or refurbished, and then add the refurbished asset back to the asset structure later.</span></span> <span data-ttu-id="66e2a-109">Como alternativa, substitua permanentemente um ativo usado por um novo ativo.</span><span class="sxs-lookup"><span data-stu-id="66e2a-109">Alternatively, permanently replace a used asset with a new asset.</span></span>
- <span data-ttu-id="66e2a-110">**Instalar** – instale um ativo pai e quaisquer ativos secundários relacionados em um local funcional.</span><span class="sxs-lookup"><span data-stu-id="66e2a-110">**Install** – Install a parent asset and any related child assets on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="66e2a-111">O ativo que você mover, substituir ou instalar pode estar relacionado a outro local funcional.</span><span class="sxs-lookup"><span data-stu-id="66e2a-111">The asset that you move, replace, or install might be related to another functional location.</span></span> <span data-ttu-id="66e2a-112">Nesse caso, o ativo poderá usar dimensões financeiras do local funcional.</span><span class="sxs-lookup"><span data-stu-id="66e2a-112">In that case, the asset might use financial dimensions of the functional location.</span></span> <span data-ttu-id="66e2a-113">Na página **Tipos de local funcional**, você configura a manipulação de dimensões financeiras em locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="66e2a-113">On the **Functional location types** page, you set up the handling of financial dimensions on functional locations.</span></span>

## <a name="move-asset"></a><span data-ttu-id="66e2a-114">Mover ativo</span><span class="sxs-lookup"><span data-stu-id="66e2a-114">Move asset</span></span>

<span data-ttu-id="66e2a-115">Use a função **Mover ativo** para mover um ativo para outra estrutura de ativos ou para outro local na mesma estrutura de ativos.</span><span class="sxs-lookup"><span data-stu-id="66e2a-115">Use the **Move asset** function to move an asset either to another asset structure or to another location in the same asset structure.</span></span> <span data-ttu-id="66e2a-116">Você também pode mover um ativo para fora da estrutura de ativos para que ele se torne um ativo autônomo sem nenhuma relação de estrutura.</span><span class="sxs-lookup"><span data-stu-id="66e2a-116">You can also move an asset out of an asset structure so that it becomes a standalone asset that has no structure relations.</span></span>

> [!NOTE]
> <span data-ttu-id="66e2a-117">Não use essa função se os ativos estiverem sendo reparados ou substituídos temporariamente.</span><span class="sxs-lookup"><span data-stu-id="66e2a-117">Don't use this function if assets are being repaired or temporarily replaced.</span></span> <span data-ttu-id="66e2a-118">Em seu lugar, use a funcionalidade **Substituir ativo**, que será descrita posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="66e2a-118">Instead, use the **Replace asset** functionality that is described later in this topic.</span></span>

1. <span data-ttu-id="66e2a-119">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-119">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="66e2a-120">Na lista, selecione o ativo a ser movido.</span><span class="sxs-lookup"><span data-stu-id="66e2a-120">In the list, select the asset to move.</span></span> <span data-ttu-id="66e2a-121">Se o ativo tiver ativos secundários, você também os moverá.</span><span class="sxs-lookup"><span data-stu-id="66e2a-121">If the asset has child assets, you also move those assets.</span></span>
3. <span data-ttu-id="66e2a-122">Selecione **Mover ativo**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-122">Select **Move asset**.</span></span>
4. <span data-ttu-id="66e2a-123">Para mover o ativo para que se torne parte de uma estrutura de ativos, selecione o novo ativo pai no campo **Ativo pai**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-123">To move the asset so that it becomes part of an asset structure, select the new parent asset in the **Parent asset** field.</span></span> <span data-ttu-id="66e2a-124">Se você estiver movendo um ativo secundário, e se quiser torná-lo um ativo autônomo sem nenhuma relação de estrutura, deixe o campo **Ativo pai** em branco.</span><span class="sxs-lookup"><span data-stu-id="66e2a-124">If you're moving a child asset, and you want to make it a standalone asset that has no structure relations, leave the **Parent asset** field blank.</span></span>
5. <span data-ttu-id="66e2a-125">Por padrão, o campo **Efetivação** é definido como a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="66e2a-125">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="66e2a-126">Entretanto, você pode selecionar data e hora diferentes a partir das quais a movimentação do ativo será válida.</span><span class="sxs-lookup"><span data-stu-id="66e2a-126">However, you can select a different date and time that the asset move is valid from.</span></span>
6. <span data-ttu-id="66e2a-127">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-127">Select **OK**.</span></span>

## <a name="replace-asset"></a><span data-ttu-id="66e2a-128">Substituir ativo</span><span class="sxs-lookup"><span data-stu-id="66e2a-128">Replace asset</span></span>

<span data-ttu-id="66e2a-129">Use a função **Substituir ativo** em conjunto com reparos, restauração ou substituição permanente de um ativo esgotado por um novo ativo.</span><span class="sxs-lookup"><span data-stu-id="66e2a-129">Use the **Replace asset** function in connection with repairs, refurbishment, or permanent replacement of a worn-out asset by a new asset.</span></span> <span data-ttu-id="66e2a-130">Essa função é usada para substituir ativos secundários em uma estrutura de ativos.</span><span class="sxs-lookup"><span data-stu-id="66e2a-130">This function is used to replace child assets in an asset structure.</span></span> <span data-ttu-id="66e2a-131">Para ativos pai (isto é, ativos que não têm um ativo pai), essa substituição é feita em um local funcional.</span><span class="sxs-lookup"><span data-stu-id="66e2a-131">For parent assets (that is, assets that don't currently have a parent asset), this replacement is done on a functional location.</span></span> <span data-ttu-id="66e2a-132">Para obter mais informações sobre como substituir ativos pai em um local funcional, consulte [Instalar ativos em locais funcionais](../functional-locations/install-objects-on-functional-locations.md).</span><span class="sxs-lookup"><span data-stu-id="66e2a-132">For more information about how to replace parent assets on a functional location, see [Install assets on functional locations](../functional-locations/install-objects-on-functional-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="66e2a-133">Se uma oficina estiver relacionada ao departamento de produção, você poderá criar locais funcionais como **Reparo**, **Sucata** e **Armazenamento** para controlar o reparo e a substituição de ativos.</span><span class="sxs-lookup"><span data-stu-id="66e2a-133">If a repair shop is related to your production department, you can create functional locations such as **Repair**, **Scrap**, and **Storage** to handle the repair and replacement of assets.</span></span>

1. <span data-ttu-id="66e2a-134">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-134">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="66e2a-135">Na lista, selecione o ativo secundário a ser substituído.</span><span class="sxs-lookup"><span data-stu-id="66e2a-135">In the list, select the child asset to replace.</span></span> <span data-ttu-id="66e2a-136">Se o ativo tiver ativos secundários, você também os substituirá.</span><span class="sxs-lookup"><span data-stu-id="66e2a-136">If the asset has child assets, you also replace those assets.</span></span>
3. <span data-ttu-id="66e2a-137">Selecione **Substituir ativo**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-137">Select **Replace asset**.</span></span>

    <span data-ttu-id="66e2a-138">O campo **Alteração de estrutura** mostra a data e a hora mais recentes em que o ativo selecionado e os ativos secundários relacionados foram movidos na estrutura de ativos.</span><span class="sxs-lookup"><span data-stu-id="66e2a-138">The **Structure change** field shows the last date and time that the selected asset and related child assets were moved in the asset structure.</span></span>

4. <span data-ttu-id="66e2a-139">Na seção **Ativo selecionado**, no campo **Local funcional de destino**, selecione o local funcional para o qual o ativo será movido.</span><span class="sxs-lookup"><span data-stu-id="66e2a-139">In the **Selected asset** section, in the **Target functional location** field, select the functional location to move the asset to.</span></span> <span data-ttu-id="66e2a-140">Por exemplo, selecione o local **Reparo** ou **Sucata**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-140">For example, select the **Repair** or **Scrap** location.</span></span>

    <span data-ttu-id="66e2a-141">Na seção **Ativo pai**, o campo **Efetivação** mostra a data e a hora mais recentes em que o ativo pai e os ativos secundários relacionados foram instalados ou movidos no local funcional atual.</span><span class="sxs-lookup"><span data-stu-id="66e2a-141">In the **Parent asset** section, the **Effective** field shows the last date and time that the parent asset and related child assets were installed or moved on the current functional location.</span></span>

5. <span data-ttu-id="66e2a-142">Na seção **Novo ativo**, no campo **Ativo**, selecione o ativo a ser inserido como substituto temporário ou permanente para o ativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="66e2a-142">In the **New asset** section, in the **Asset** field, select the asset to insert as a temporary or permanent replacement for the selected asset.</span></span> <span data-ttu-id="66e2a-143">Esse ativo pode estar localizado em outro local funcional, como **Armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-143">This asset might currently be located on another functional location, such as **Storage**.</span></span>
7. <span data-ttu-id="66e2a-144">Na seção **Efetivo a partir de**, o campo **Efetivação** é definido como a data e hora atuais por padrão.</span><span class="sxs-lookup"><span data-stu-id="66e2a-144">In the **Effective from** section, the **Effective** field is set to the current date and time by default.</span></span> <span data-ttu-id="66e2a-145">Entretanto, você pode selecionar data e hora diferentes a partir das quais a substituição do ativo será válida.</span><span class="sxs-lookup"><span data-stu-id="66e2a-145">However, you can select a different date and time that the asset replacement is valid from.</span></span>
8. <span data-ttu-id="66e2a-146">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-146">Select **OK**.</span></span>

## <a name="install-asset"></a><span data-ttu-id="66e2a-147">Instalar ativo</span><span class="sxs-lookup"><span data-stu-id="66e2a-147">Install asset</span></span>

<span data-ttu-id="66e2a-148">Use a função **Instalar ativo** para instalar uma estrutura de ativos em um local funcional.</span><span class="sxs-lookup"><span data-stu-id="66e2a-148">Use the **Install asset** function to install an asset structure on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="66e2a-149">Sempre selecione um ativo pai.</span><span class="sxs-lookup"><span data-stu-id="66e2a-149">Always select a parent asset.</span></span> <span data-ttu-id="66e2a-150">O ativo pai e os ativos secundários relacionados serão movidos para o local funcional selecionado.</span><span class="sxs-lookup"><span data-stu-id="66e2a-150">The parent asset and related child assets will be moved to the selected functional location.</span></span>

1. <span data-ttu-id="66e2a-151">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-151">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="66e2a-152">Na lista, selecione o ativo pai para instalar em outro local funcional.</span><span class="sxs-lookup"><span data-stu-id="66e2a-152">In the list, select the parent asset to install on another functional location.</span></span>
3. <span data-ttu-id="66e2a-153">Selecione **Instalar ativo**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-153">Select **Install asset**.</span></span>

    <span data-ttu-id="66e2a-154">A seção **Atributos** mostra os atributos de ativo configurados no ativo pai.</span><span class="sxs-lookup"><span data-stu-id="66e2a-154">The **Attributes** section shows the asset attributes that are set up on the parent asset.</span></span>

4. <span data-ttu-id="66e2a-155">No campo **Local funcional**, selecione o novo local.</span><span class="sxs-lookup"><span data-stu-id="66e2a-155">In the **Functional location** field, select the new location.</span></span>
5. <span data-ttu-id="66e2a-156">Por padrão, o campo **Efetivação** é definido como a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="66e2a-156">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="66e2a-157">Entretanto, você pode selecionar data e hora diferentes a partir das quais a instalação na estrutura de ativos será válida.</span><span class="sxs-lookup"><span data-stu-id="66e2a-157">However, you can select a different date and time that the installation on the asset structure is valid from.</span></span>
6. <span data-ttu-id="66e2a-158">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="66e2a-158">Select **OK**.</span></span>
