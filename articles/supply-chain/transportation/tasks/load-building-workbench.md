---
title: Bancada de criação de carga
description: Este tópico descreve como trabalhar com a bancada de criação de carga.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1ed91adba5c7accf9a18d7a754d33b2b35b848f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974210"
---
# <a name="load-building-workbench"></a><span data-ttu-id="d8f87-103">Bancada de criação de carga</span><span class="sxs-lookup"><span data-stu-id="d8f87-103">Load building workbench</span></span>

<span data-ttu-id="d8f87-104">A bancada de criação de carga permite aplicar estratégias de criação de carga ao criar cargas.</span><span class="sxs-lookup"><span data-stu-id="d8f87-104">The load building workbench lets you apply load building strategies when you create loads.</span></span>

## <a name="create-a-load-building-strategy"></a><span data-ttu-id="d8f87-105">Elaborar uma estratégia de criação de carga</span><span class="sxs-lookup"><span data-stu-id="d8f87-105">Create a load building strategy</span></span>

<span data-ttu-id="d8f87-106">Você usa as estratégias de criação de carga para criar cargas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d8f87-106">You use load building strategies to automatically build loads.</span></span> <span data-ttu-id="d8f87-107">Esse recurso pode ser benéfico nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="d8f87-107">This capability can be beneficial in the following situations:</span></span>

- <span data-ttu-id="d8f87-108">Se você remete um conjunto específico de produtos regularmente, as estratégias de carga ajudam a poupar tempo, porque não é necessário criar a mesma carga todas as vezes.</span><span class="sxs-lookup"><span data-stu-id="d8f87-108">If you regularly ship a specific set of products, load strategies help save time, because you don't have to build the same load every time.</span></span>
- <span data-ttu-id="d8f87-109">Se você deseja evitar cargas meio cheias para maximizar a eficiência, as estratégias de carga podem ajudar a preencher cada carga o máximo possível.</span><span class="sxs-lookup"><span data-stu-id="d8f87-109">If you want to avoid half-full loads to maximize efficiency, load strategies can help fill each load as much as possible.</span></span>

<span data-ttu-id="d8f87-110">Uma classe de estratégia de criação de carga chamada `TMSLoadBuildingVolumeStrategy` fornece uma estratégia de criação de carga denominada *Estratégia de criação de carga com base no volume*.</span><span class="sxs-lookup"><span data-stu-id="d8f87-110">A load building strategy class that is named `TMSLoadBuildingVolumeStrategy` provides a load building strategy that is named *Volume-based load building strategy*.</span></span> <span data-ttu-id="d8f87-111">Essa estratégia permite usar os valores máximos especificados para a altura e o peso do modelo de carga ou substituí-los pelas configurações por meio da inserção de novos valores.</span><span class="sxs-lookup"><span data-stu-id="d8f87-111">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="d8f87-112">Essa estratégia é a única que está incluída pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="d8f87-112">This strategy is the only strategy that is included out of the box.</span></span> <span data-ttu-id="d8f87-113">(No entanto, você pode ter algumas estratégias personalizadas).</span><span class="sxs-lookup"><span data-stu-id="d8f87-113">(However, you might have some custom strategies.)</span></span>

<span data-ttu-id="d8f87-114">Para usar a estratégia pronta para uso *Estratégia de criação de carga com base no volume*, selecione-a no campo **Estratégia de criação de carga** na página **Bancada de criação de carga** (**Gerenciamento de transporte &gt; Planejamento &gt; Bancada de criação de carga**).</span><span class="sxs-lookup"><span data-stu-id="d8f87-114">To use the out-of-box *Volume-based load building strategy* strategy, select it in the **Load building strategy** field on the **Load building workbench** page (**Transportation management &gt; Planning &gt; Load building workbench**).</span></span>

<span data-ttu-id="d8f87-115">Para elaborar uma estratégia de criação de carga, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d8f87-115">To create a load building strategy, follow these steps.</span></span>

1. <span data-ttu-id="d8f87-116">Vá para **Gerenciamento de transporte &gt; Configuração &gt; Criação de carga &gt; Estratégias de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-116">Go to **Transportation management &gt; Setup &gt; Load building &gt; Load building strategies**.</span></span>
1. <span data-ttu-id="d8f87-117">No Painel de Ações, selecione **Gerar lista de classes** para verificar se você tem as versões mais recentes de todas as classes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d8f87-117">On the Action Pane, select **Generate class list** to make sure that you have the latest versions of all available classes.</span></span>
1. <span data-ttu-id="d8f87-118">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-118">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d8f87-119">Insira um nome exclusivo para a estratégia, selecione a classe de estratégia de criação de carga e insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d8f87-119">Enter a unique name for the strategy, select the load building strategy class for it, and enter a description.</span></span>
1. <span data-ttu-id="d8f87-120">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-120">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="d8f87-121">No Painel de Ações, selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-121">On the Action Pane, select **Parameters**.</span></span>
1. <span data-ttu-id="d8f87-122">Na página **Parâmetros da estratégia de criação de carga**, selecione **Capacidade de volume** na lista e, em seguida, no campo **Valor**, insira a porcentagem da capacidade de volume total da carga que deve ser aplicada para a nova estratégia de criação de carga.</span><span class="sxs-lookup"><span data-stu-id="d8f87-122">On the **Load building strategy parameters** page, select **Volume capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total volume capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="d8f87-123">Selecione **Capacidade de peso** na lista e, em seguida, no campo **Valor**, insira a porcentagem da capacidade de peso total da carga que deve ser aplicada para a nova estratégia de criação de carga.</span><span class="sxs-lookup"><span data-stu-id="d8f87-123">Select **Weight capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total weight capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="d8f87-124">Feche a página **Parâmetros da estratégia de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-124">Close the **Load building strategy parameters** page.</span></span>
1. <span data-ttu-id="d8f87-125">Feche a página **Estratégias de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-125">Close the **Load building strategies** page.</span></span>

<span data-ttu-id="d8f87-126">Agora você pode atribuir a estratégia de criação de carga a um modelo de criação de carga.</span><span class="sxs-lookup"><span data-stu-id="d8f87-126">You can now assign the load building strategy to a load building template.</span></span> <span data-ttu-id="d8f87-127">Como alternativa, você pode usá-la diretamente na bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="d8f87-127">Alternatively, you can use it directly in the load planning workbench.</span></span>

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a><span data-ttu-id="d8f87-128">Usar uma estratégia de criação de carga na bancada de criação de carga</span><span class="sxs-lookup"><span data-stu-id="d8f87-128">Use a load building strategy in the load building workbench</span></span>

1. <span data-ttu-id="d8f87-129">Vá para **Gerenciamento de transporte &gt; Planejamento &gt; Bancada de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-129">Go to **Transportation management &gt; Planning &gt; Load building workbench**.</span></span>
1. <span data-ttu-id="d8f87-130">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="d8f87-130">Follow one of these steps:</span></span>

    - <span data-ttu-id="d8f87-131">Selecione uma estratégia no campo **Estratégia de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-131">Select a strategy in the **Load building strategy** field.</span></span>
    - <span data-ttu-id="d8f87-132">Se você definiu um modelo de criação de carga e atribuiu a estratégia de criação de carga a ele, no Painel de Ações, na guia **Gerenciar modelos**, selecione **Aplicar modelo**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-132">If you've defined a load building template and assigned the load building strategy to it, on the Action Pane, on the **Manage templates** tab, select **Apply template**.</span></span> <span data-ttu-id="d8f87-133">Em seguida, na caixa de diálogo suspensa **Aplicar modelo de criação de carga**, selecione um modelo no campo **Nome do modelo de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-133">Then, in the **Apply load building template** drop-down dialog box, select a template in the **Load building template name** field.</span></span>

1. <span data-ttu-id="d8f87-134">Na FastTab **Sequência de modelos de carga**, selecione um ou mais [modelos de carga](load-template.md).</span><span class="sxs-lookup"><span data-stu-id="d8f87-134">On the **Load templates sequence** FastTab, select one or more [load templates](load-template.md).</span></span> <span data-ttu-id="d8f87-135">A bancada tentará ajustar a carga nesses tipos de contêineres, na sequência especificada aqui.</span><span class="sxs-lookup"><span data-stu-id="d8f87-135">The workbench will try to fit the load into these types of containers, in the sequence that is specified here.</span></span> <span data-ttu-id="d8f87-136">Normalmente, você deve colocar os contêineres menores no topo da lista para garantir que o menor contêiner possível seja selecionado primeiro.</span><span class="sxs-lookup"><span data-stu-id="d8f87-136">Typically, you should put the smallest containers at the top of the list to ensure that the smallest possible container is selected first.</span></span>
1. <span data-ttu-id="d8f87-137">No Painel de Ações, selecione **Propor cargas**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-137">On the Action Pane, select **Propose loads**.</span></span>
1. <span data-ttu-id="d8f87-138">Revise as cargas propostas e as linhas de cargas propostas.</span><span class="sxs-lookup"><span data-stu-id="d8f87-138">Review the proposed loads and proposed load lines.</span></span>
1. <span data-ttu-id="d8f87-139">No Painel de Ações, selecione **Criar cargas** para criar cargas com base nas linhas do documento de origem na FastTab **Linhas de cargas propostas**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-139">On the Action Pane, select **Create loads** to create loads that are based on the source document lines on the **Proposed load lines** FastTab.</span></span>
1. <span data-ttu-id="d8f87-140">Feche a página **Bancada de criação de carga**.</span><span class="sxs-lookup"><span data-stu-id="d8f87-140">Close the **Load building workbench** page.</span></span>
