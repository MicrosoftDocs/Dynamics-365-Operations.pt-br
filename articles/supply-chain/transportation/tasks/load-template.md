---
title: Modelos de carga
description: Este tópico descreve como configurar modelos de carga e como associar um modelo de carga a uma nova carga.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 175c8017b14cc298cdaa00031f8450015a747786
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831497"
---
# <a name="load-templates"></a><span data-ttu-id="f0d71-103">Modelos de carga</span><span class="sxs-lookup"><span data-stu-id="f0d71-103">Load templates</span></span>

<span data-ttu-id="f0d71-104">Ao criar uma carga, você pode atribuir um modelo de carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-104">When you create a new load, you can assign a load template.</span></span> <span data-ttu-id="f0d71-105">O modelo de carga contém informações sobre equipamentos e medidas como altura, largura, profundidade e volume da carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-105">The load template contains information about equipment, and about measures such as the height, width, depth, and volume of the load.</span></span>

<span data-ttu-id="f0d71-106">Este tópico descreve como configurar modelos de carga e como associar um modelo de carga a uma nova carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-106">This topic describes how to set up load templates, and how to associate a load template with a new load.</span></span>

## <a name="set-up-a-load-template"></a><span data-ttu-id="f0d71-107">Configurar um modelo de carga</span><span class="sxs-lookup"><span data-stu-id="f0d71-107">Set up a load template</span></span>

1. <span data-ttu-id="f0d71-108">Vá para **Gerenciamento de transporte \> Configuração \> Criação de carga \> Modelo de carga**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-108">Go to **Transportation management \> Setup \> Load Building \> Load template**.</span></span>
1. <span data-ttu-id="f0d71-109">No Painel de Ações, selecione **Novo** para adicionar um novo modelo ou **Editar** para editar um modelo existente.</span><span class="sxs-lookup"><span data-stu-id="f0d71-109">On the Action Pane, select **New** to add a new template or **Edit** to edit an existing template.</span></span>
1. <span data-ttu-id="f0d71-110">Na linha do modelo novo ou existente, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="f0d71-110">In the row for the new or existing template, set the following fields:</span></span>

    - <span data-ttu-id="f0d71-111">**ID do modelo de carga** – Insira um identificador exclusivo (ID) para o modelo de carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-111">**Load template ID** – Enter a unique identifier (ID) for the load template.</span></span>
    - <span data-ttu-id="f0d71-112">**Equipamento** – Selecione o equipamento que deve ser usado para remeter a carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-112">**Equipment** – Select the equipment that should be used to ship the load.</span></span>
    - <span data-ttu-id="f0d71-113">**Altura da carga**, **Largura da carga** e **Profundidade da carga** – Insira as dimensões da carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-113">**Load height**, **Load width**, and **Load depth** – Enter the dimensions of the load.</span></span>
    - <span data-ttu-id="f0d71-114">**Volume de carga máximo permitido** e **Peso de carga máximo permitido** – Insira o volume e o peso máximo permitido da carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-114">**Max. allowed load volume** and **Max. allowed load weight** – Enter the maximum allowed volume and weight of the load.</span></span>
    - <span data-ttu-id="f0d71-115">**Peso bruto máximo permitido** – Insira o peso bruto máximo permitido da carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-115">**Maximum allowed gross weight** – Enter the maximum allowed gross weight of the load.</span></span> <span data-ttu-id="f0d71-116">O peso bruto de uma carga inclui a tara e o peso de carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-116">A load's gross weight includes both its tare weight and its loading weight.</span></span>
    - <span data-ttu-id="f0d71-117">**Número máximo de peças de frete permitido** – Insira o número máximo de peças de frete que a carga pode conter.</span><span class="sxs-lookup"><span data-stu-id="f0d71-117">**Maximum number of freight pieces allowed** – Enter the maximum number of freight pieces that the load can contain.</span></span>
    - <span data-ttu-id="f0d71-118">**Empilhar a carga sobre o piso** – Marque esta caixa de seleção para empilhar a carga sobre o piso.</span><span class="sxs-lookup"><span data-stu-id="f0d71-118">**Stack load on floor** – Select this check box to use floor loading.</span></span> <span data-ttu-id="f0d71-119">Em um cenário de carga sobre o piso, as caixas são empilhadas do piso ao teto e de parede a parede dentro do contêiner para maximizar a capacidade.</span><span class="sxs-lookup"><span data-stu-id="f0d71-119">In a floor loading scenario, boxes are stacked floor to ceiling and wall to wall inside the container, to maximize capacity.</span></span>

1. <span data-ttu-id="f0d71-120">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-120">On the Action Pane, select **Save**.</span></span>

## <a name="associate-a-load-template-with-a-new-load"></a><span data-ttu-id="f0d71-121">Associar um modelo de carga a uma nova carga</span><span class="sxs-lookup"><span data-stu-id="f0d71-121">Associate a load template with a new load</span></span>

1. <span data-ttu-id="f0d71-122">Vá para **Gerenciamento de transporte \> Planejamento \> Bancada de planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-122">Go to **Transportation management \> Planning \> Load planning workbench**.</span></span>
1. <span data-ttu-id="f0d71-123">Na parte superior da página, selecione uma das guias a seguir, dependendo do tipo de documento de origem para o qual você está criando uma carga: **Remessas**, **Linhas de venda**, **Linhas de transferência** ou **Linhas de ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-123">In the upper part of the page, select one of the following tabs, depending on the type of source document that you're creating a load for: **Shipments**, **Sales lines**, **Transfer lines**, or **Purchase order lines**.</span></span> 
1. <span data-ttu-id="f0d71-124">Selecione o documento específico para o qual planejar a carga.</span><span class="sxs-lookup"><span data-stu-id="f0d71-124">Select the specific document to plan the load for.</span></span>
1. <span data-ttu-id="f0d71-125">No Painel de Ação, na guia **Oferta e demanda** , no grupo **Adicionar** , selecione **Para nova carga**.</span><span class="sxs-lookup"><span data-stu-id="f0d71-125">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span>
1. <span data-ttu-id="f0d71-126">Na caixa de diálogo **Modelo de carga**, no campo **ID do modelo de carga**, selecione o modelo a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="f0d71-126">In the **Load template** dialog box, in the **Load template ID** field, select the template to apply.</span></span>
1. <span data-ttu-id="f0d71-127">Selecione **OK** para aplicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="f0d71-127">Select **OK** to apply the template.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]