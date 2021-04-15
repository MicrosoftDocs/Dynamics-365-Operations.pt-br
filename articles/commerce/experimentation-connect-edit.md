---
title: Conectar um experimento e editar variações
description: Este tópico descreve como conectar um experimento em um serviço de terceiros ao Dynamics 365 Commerce e como editar variações para o experimento.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4c9c9463162f21cdaf40f1c4ed6d5ae51e97cb88
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799074"
---
# <a name="connect-an-experiment-and-edit-variations"></a><span data-ttu-id="7093b-103">Conectar um experimento e editar variações</span><span class="sxs-lookup"><span data-stu-id="7093b-103">Connect an experiment and edit variations</span></span>

<span data-ttu-id="7093b-104">Este tópico descreve como conectar seu experimento no Commerce e fazer alterações nas variações para que elas se alinhem com a hipótese.</span><span class="sxs-lookup"><span data-stu-id="7093b-104">This topic describes how to connect your experiment in Commerce and make changes to your variations so that they align with your hypothesis.</span></span> 

<span data-ttu-id="7093b-105">O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7093b-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="7093b-106">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="7093b-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="7093b-107">[ ![Jornada de usuário de experimentação - conectar e editar](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7093b-107">[ ![Experimentation user journey - Connect & Edit](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span></span>

<span data-ttu-id="7093b-108">Depois de [configurar seu experimento](experimentation-setup.md) em um serviço de terceiros, você conectará o experimento no Dynamics 365 Commerce e editará as variações do experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-108">After you've [set up your experiment](experimentation-setup.md) in a third-party service, you'll connect the experiment in Dynamics 365 Commerce and edit the experiment variations.</span></span>

## <a name="planning-considerations"></a><span data-ttu-id="7093b-109">Considerações de planejamento</span><span class="sxs-lookup"><span data-stu-id="7093b-109">Planning considerations</span></span>

<span data-ttu-id="7093b-110">Antes de conectar seu experimento no Commerce, você precisará tomar algumas decisões que afetam a forma como o Commerce gerencia o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7093b-110">Before you connect your experiment in Commerce, you'll need to make some decisions that impact the way Commerce manages your content.</span></span>

### <a name="determine-the-scope-of-your-experiment"></a><span data-ttu-id="7093b-111">Determine o escopo do seu experimento</span><span class="sxs-lookup"><span data-stu-id="7093b-111">Determine the scope of your experiment</span></span>
<span data-ttu-id="7093b-112">Ao conectar um experimento, você é solicitado a definir o escopo do experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-112">When you connect an experiment, you are prompted to define the scope of the experiment.</span></span> <span data-ttu-id="7093b-113">Os experimentos são definidos como escopo **parcial** ou escopo **inteiro**.</span><span class="sxs-lookup"><span data-stu-id="7093b-113">Experiments are defined as **partial** scope or **entire** scope.</span></span>
- <span data-ttu-id="7093b-114">Escolha **parcial** se desejar conduzir um experimento em uma parte específica de uma página.</span><span class="sxs-lookup"><span data-stu-id="7093b-114">Choose **partial** if you want to conduct an experiment on a specific portion of a page.</span></span> <span data-ttu-id="7093b-115">Se você selecionar essa opção, deverá identificar os módulos incluídos no experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-115">If you select this option, you must identify which modules are included in the experiment.</span></span> <span data-ttu-id="7093b-116">As alterações feitas nas partes da página ou no fragmento padrão que não estão relacionados ao experimento são automaticamente sincronizadas entre variações.</span><span class="sxs-lookup"><span data-stu-id="7093b-116">Changes that are made to parts of the default page or fragment that aren't related to the experiment are automatically synchronized across variations.</span></span>
- <span data-ttu-id="7093b-117">Escolha **inteiro** se desejar conduzir um experimento em uma página ou fragmento inteiro.</span><span class="sxs-lookup"><span data-stu-id="7093b-117">Choose **entire** if you want to conduct an experiment on an entire page or fragment.</span></span> <span data-ttu-id="7093b-118">Cópias separadas da página ou do fragmento padrão são criadas.</span><span class="sxs-lookup"><span data-stu-id="7093b-118">Separate copies of the default page or fragment are created.</span></span> <span data-ttu-id="7093b-119">Você não precisará selecionar quais módulos serão incluídos no experimento porque toda a superfície de edição está disponível para alteração.</span><span class="sxs-lookup"><span data-stu-id="7093b-119">You won't have to select which modules are included in the experiment because the whole editing surface is available to change.</span></span> <span data-ttu-id="7093b-120">Você pode adicionar, excluir ou reordenar os módulos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7093b-120">You can add, delete, or re-order modules as needed.</span></span> <span data-ttu-id="7093b-121">No entanto, se forem feitas alterações na página padrão ou no fragmento ao qual o experimento está associado, essas alterações precisarão ser sincronizadas manualmente em todas as variações.</span><span class="sxs-lookup"><span data-stu-id="7093b-121">However, if any changes are made to the default page or fragment that the experiment is associated with, those changes have to be manually synchronized across all variations.</span></span>

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> <span data-ttu-id="7093b-122">Se você associar seu experimento a uma página que usa um layout, só poderá criar o escopo do experimento como **inteiro**.</span><span class="sxs-lookup"><span data-stu-id="7093b-122">If you associate your experiment with a page that uses a layout, you can only scope the experiment as **entire**.</span></span>

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a><span data-ttu-id="7093b-123">Decida se deseja agendar quando seu experimento será publicado</span><span class="sxs-lookup"><span data-stu-id="7093b-123">Decide if you want to schedule when your experiment is published</span></span>
<span data-ttu-id="7093b-124">Se você deseja agendar quando seu experimento será publicado no seu site ativo, certifique-se de que o conteúdo que você deseja associar ao experimento esteja disponível em um grupo de publicação *antes* de conectar o experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-124">If you want to schedule when your experiment is published to your live site, make sure the content you want to associate with the experiment is available in a publish group *before* you connect the experiment.</span></span> 

<span data-ttu-id="7093b-125">Para obter mais informações sobre grupos de publicações, consulte [Trabalhar com grupos de publicação](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7093b-125">For more information about publish groups, refer to [Work with publish groups](publish-groups.md).</span></span>


## <a name="connect-your-experiment"></a><span data-ttu-id="7093b-126">Conectar seu experimento</span><span class="sxs-lookup"><span data-stu-id="7093b-126">Connect your experiment</span></span>
<span data-ttu-id="7093b-127">Para conectar seu experimento, você iniciará o assistente **Conectar experimento**.</span><span class="sxs-lookup"><span data-stu-id="7093b-127">To connect your experiment, you'll launch the **Connect experiment** wizard.</span></span> <span data-ttu-id="7093b-128">O assistente o conduz pelas etapas necessárias para conectar seu experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-128">The wizard walks you through the steps required to connect your experiment.</span></span> <span data-ttu-id="7093b-129">Quando você concluir o assistente, seu experimento será conectado e as variações serão criadas e estarão prontas para serem editadas.</span><span class="sxs-lookup"><span data-stu-id="7093b-129">When you complete the wizard, your experiment is connected and variations are created and ready to be edited.</span></span>

<span data-ttu-id="7093b-130">Para começar a conectar sua experiência no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7093b-130">To get started connecting your experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="7093b-131">Para iniciar o assistente **Conectar experimento**, selecione **Experimentos** no painel de navegação esquerdo e selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="7093b-131">To launch the **Connect experiment** wizard, select **Experiments** in the left navigation pane, and then select **Connect**.</span></span> <span data-ttu-id="7093b-132">Como alternativa, você pode acessar o assistente de uma página ou o editor de fragmentos editando-o e selecionando **Conectar experimento** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="7093b-132">Alternatively, you can access the wizard from a page or fragment editor by editing it and selecting **Connect experiment** on the command bar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7093b-133">Uma página pode ser conectada somente a um experimento de cada vez.</span><span class="sxs-lookup"><span data-stu-id="7093b-133">A page can only be connected to one experiment at a time.</span></span> <span data-ttu-id="7093b-134">Para conectar uma página a um experimento diferente, primeiro exclua o experimento ao qual a página está conectada no momento.</span><span class="sxs-lookup"><span data-stu-id="7093b-134">To connect a page to a different experiment, first delete the experiment that the page is currently connected to.</span></span>

1. <span data-ttu-id="7093b-135">Escolha a página ou o fragmento em que você deseja executar o experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-135">Choose the page or fragment you want to run your experiment on.</span></span>
1. <span data-ttu-id="7093b-136">Defina o escopo de experimentação como **parcial** ou **inteiro**, com base na opção feita na seção [Determinar o escopo do seu experimento](#determine-the-scope-of-your-experiment) acima.</span><span class="sxs-lookup"><span data-stu-id="7093b-136">Set the experimentation scope to **partial** or **entire**, based on the choice you made in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>
    > [!NOTE]
    > <span data-ttu-id="7093b-137">O sinalizador de recursos **Experimento em páginas ou fragmentos** deverá estar habilitado se você quiser experimentar em uma página inteira ou fragmento.</span><span class="sxs-lookup"><span data-stu-id="7093b-137">The **Experiment on pages or fragments** feature flag must be enabled if you want to experiment on a full page or fragment.</span></span> <span data-ttu-id="7093b-138">Consulte o tópico [Experimentação no Dynamics 365 Commerce](experimentation-overview.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7093b-138">Refer to the [Experimentation in Dynamics 365 Commerce](experimentation-overview.md) topic for more information.</span></span>
    
1. <span data-ttu-id="7093b-139">Na etapa final do assistente, selecione **Gerar variações e sair do assistente**.</span><span class="sxs-lookup"><span data-stu-id="7093b-139">In the final step of the wizard, select **Generate variations and exit wizard**.</span></span> <span data-ttu-id="7093b-140">As variações são criadas para o experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-140">Variations are created for the experiment.</span></span> 

## <a name="edit-your-variations"></a><span data-ttu-id="7093b-141">Editar suas variações</span><span class="sxs-lookup"><span data-stu-id="7093b-141">Edit your variations</span></span>
<span data-ttu-id="7093b-142">Quando você sair do assistente, as variações serão criadas para você.</span><span class="sxs-lookup"><span data-stu-id="7093b-142">When you exit the wizard, variations are created for you.</span></span> 

<span data-ttu-id="7093b-143">Em seguida, edite as variações para que reflitam as opções que você precisa verificar na hipótese de experimento.</span><span class="sxs-lookup"><span data-stu-id="7093b-143">Next, you'll edit the variations so they reflect the choices that you need to verify in the experiment hypothesis.</span></span> <span data-ttu-id="7093b-144">Escolha um dos procedimentos a seguir que corresponda ao escopo escolhido para seu experimento na seção [Determinar o escopo do experimento](#determine-the-scope-of-your-experiment) acima.</span><span class="sxs-lookup"><span data-stu-id="7093b-144">Choose one of following procedures that corresponds to the scope you chose for your experiment in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>

### <a name="edit-variations-for-experiments-with-partial-scope"></a><span data-ttu-id="7093b-145">Editar variações de experimentos com escopo parcial</span><span class="sxs-lookup"><span data-stu-id="7093b-145">Edit variations for experiments with partial scope</span></span>
<span data-ttu-id="7093b-146">Siga estas etapas se você tiver definido o escopo do seu experimento como **parcial** no assistente **Conectar experimento**.</span><span class="sxs-lookup"><span data-stu-id="7093b-146">Follow these steps if you defined the scope of your experiment as **partial** in the **Connect experiment** wizard.</span></span>

1. <span data-ttu-id="7093b-147">Na exibição do editor, use o menu suspenso de variações abaixo da barra de comandos para editar cada variação com base na hipótese original.</span><span class="sxs-lookup"><span data-stu-id="7093b-147">In editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> <span data-ttu-id="7093b-148">Também pode ser necessário estabelecer um controle ou uma variação de base, deixando uma das variações inalteradas.</span><span class="sxs-lookup"><span data-stu-id="7093b-148">You may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>
1. <span data-ttu-id="7093b-149">Selecione o módulo a ser experimentado, selecione as reticências (...) e, em seguida, selecione **Adicionar ao experimento**.</span><span class="sxs-lookup"><span data-stu-id="7093b-149">Select the module to be experimented on, select the ellipsis (...), and then select **Add to experiment**.</span></span>

### <a name="edit-variations-for-experiments-with-entire-scope"></a><span data-ttu-id="7093b-150">Editar variações de experimentos com escopo inteiro</span><span class="sxs-lookup"><span data-stu-id="7093b-150">Edit variations for experiments with entire scope</span></span>
<span data-ttu-id="7093b-151">Se você tiver definido o escopo do seu experimento como **inteiro** no assistente **Conectar experimento**, na exibição do editor, use o menu suspenso de variações abaixo da barra de comandos para editar cada variação com base na hipótese original.</span><span class="sxs-lookup"><span data-stu-id="7093b-151">If you defined the scope of your experiment as **entire** in the **Connect experiment** wizard, while in editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> 

> [!NOTE]
> <span data-ttu-id="7093b-152">Em qualquer um dos casos, também poderá ser necessário estabelecer um controle ou uma variação de base, deixando uma das variações inalteradas.</span><span class="sxs-lookup"><span data-stu-id="7093b-152">In either case, you may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>

## <a name="previous-step"></a><span data-ttu-id="7093b-153">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="7093b-153">Previous step</span></span>
[<span data-ttu-id="7093b-154">Configurar um experimento</span><span class="sxs-lookup"><span data-stu-id="7093b-154">Set up an experiment</span></span>](experimentation-setup.md) 


## <a name="next-step"></a><span data-ttu-id="7093b-155">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7093b-155">Next step</span></span>
[<span data-ttu-id="7093b-156">Visualizar e publicar um experimento</span><span class="sxs-lookup"><span data-stu-id="7093b-156">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]