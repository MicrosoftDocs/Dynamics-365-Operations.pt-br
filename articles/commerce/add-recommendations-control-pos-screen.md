---
title: Adicionar recomendações à tela de transação
description: Este tópico descreve como adicionar um controle de recomendações à tela da transação em um dispositivo de ponto de venda (PDV) usando o designer de layout de tela no Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/19/20
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a39389da0908953cbbc161f07d067ce3fc569a1b
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154123"
---
# <a name="add-recommendations-to-the-transaction-screen"></a><span data-ttu-id="42a4f-103">Adicionar recomendações à tela de transação</span><span class="sxs-lookup"><span data-stu-id="42a4f-103">Add recommendations to the transaction screen</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="42a4f-104">Este tópico descreve como adicionar um controle de recomendações à tela da transação em um dispositivo de ponto de venda (PDV) usando o designer de layout de tela no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="42a4f-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="42a4f-105">Para obter mais informações sobre recomendações de produtos, leia as  [recomendações de produtos na documentação do PDV](product.md).</span><span class="sxs-lookup"><span data-stu-id="42a4f-105">For more information about product recommendations, read the  [product recommendations on POS documentation](product.md).</span></span>


<span data-ttu-id="42a4f-106">Você pode exibir as recomendações de produtos no dispositivo do PDV ao usar o Commerce.</span><span class="sxs-lookup"><span data-stu-id="42a4f-106">You can display product recommendations on your POS device when you use Commerce.</span></span> <span data-ttu-id="42a4f-107">Para exibir recomendações de produto, é necessário adicionar um controle à tela de transação usando o designer do layout da tela.</span><span class="sxs-lookup"><span data-stu-id="42a4f-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="42a4f-108">Abrir o designer do layout</span><span class="sxs-lookup"><span data-stu-id="42a4f-108">Open Layout designer</span></span>

1. <span data-ttu-id="42a4f-109">Vá para **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-109">Go to **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="42a4f-110">Use o Filtro Rápido para localizar a tela à qual você deseja adicionar o controle.</span><span class="sxs-lookup"><span data-stu-id="42a4f-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="42a4f-111">Por exemplo, filtre o campo **ID do layout da tela** usando um valor de **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="42a4f-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="42a4f-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="42a4f-113">Por exemplo, selecione **Nome: F2CP16:9M ID do layout da tela: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="42a4f-114">Clique em **Designer de layout**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="42a4f-115">Acompanhe os avisos para iniciar o designer do layout.</span><span class="sxs-lookup"><span data-stu-id="42a4f-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="42a4f-116">Quando as credenciais forem solicitadas, insira as mesmas credenciais usadas quando o designer do layout foi iniciado na página **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="42a4f-117">Ao entrar, uma página semelhante à abaixo aparecerá.</span><span class="sxs-lookup"><span data-stu-id="42a4f-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="42a4f-118">O layout será diferente dependendo as personalizações feitas para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="42a4f-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="42a4f-119">[![Designer de layout](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="42a4f-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="42a4f-120">Escolher um opção de exibição</span><span class="sxs-lookup"><span data-stu-id="42a4f-120">Choose a display option</span></span>

<span data-ttu-id="42a4f-121">Há duas opções de configurações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="42a4f-121">There are two configurations options available.</span></span> <span data-ttu-id="42a4f-122">Escolha a opção que funciona melhor para o armazenamento e siga as demais instruções para concluir a configuração do controle.</span><span class="sxs-lookup"><span data-stu-id="42a4f-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="42a4f-123">As duas opções são:</span><span class="sxs-lookup"><span data-stu-id="42a4f-123">The two options are:</span></span>

- <span data-ttu-id="42a4f-124">As recomendações são sempre visíveis.</span><span class="sxs-lookup"><span data-stu-id="42a4f-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="42a4f-125">Uma guia **Recomendações** será exibida na grade à direita da tela.</span><span class="sxs-lookup"><span data-stu-id="42a4f-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="42a4f-126">Torne as recomendações sempre visíveis</span><span class="sxs-lookup"><span data-stu-id="42a4f-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="42a4f-127">Reduza a altura da área de detalhes das linhas de transação para que ela tenha a mesma altura do painel do cliente à esquerda.</span><span class="sxs-lookup"><span data-stu-id="42a4f-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="42a4f-128">[![Altura da área de detalhes das linhas de transação reduzida](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="42a4f-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="42a4f-129">No menu à esquerda, arraste e solte o controle de recomendações entre a área de detalhes de linhas de transação e a grade de botões na parte inferior do centro da tela de transação.</span><span class="sxs-lookup"><span data-stu-id="42a4f-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="42a4f-130">Redimensione o controle para que ele caiba no espaço.</span><span class="sxs-lookup"><span data-stu-id="42a4f-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="42a4f-131">[![Controle de recomendações adicionado ao layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="42a4f-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="42a4f-132">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="42a4f-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="42a4f-133">No Commerce, vá para **Varejo e Comércio** &gt; **TI de Varejo e Comércio** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-133">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="42a4f-134">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="42a4f-135">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="42a4f-136">Adicione uma guia Recomendações à grade de botões no lado direito da tela</span><span class="sxs-lookup"><span data-stu-id="42a4f-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="42a4f-137">Clique com o botão direito no espaço vazio abaixo da última guia na grade de botões localizada no lado direito da página.</span><span class="sxs-lookup"><span data-stu-id="42a4f-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="42a4f-138">Clique em **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-138">Click **Customize**.</span></span>

    <span data-ttu-id="42a4f-139">[![Personalização - Caixa de diálogo Controle de guias](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="42a4f-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="42a4f-140">Clique em **Nova guia**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-140">Click **New tab**.</span></span>
4. <span data-ttu-id="42a4f-141">Localize a nova guia que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="42a4f-141">Find the new tab that you just added.</span></span> <span data-ttu-id="42a4f-142">Talvez você precise rolar para baixo.</span><span class="sxs-lookup"><span data-stu-id="42a4f-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="42a4f-143">No menu suspenso **Conteúdos**, selecione **Produtos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="42a4f-144">[![Seleção de produtos recomendados no campo Conteúdo](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="42a4f-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="42a4f-145">No campo **Etiqueta**, digite um nome para a guia das recomendações. Por exemplo, digite 'Produtos recomendados'.</span><span class="sxs-lookup"><span data-stu-id="42a4f-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="42a4f-146">No campo **Imagem**, selecione a imagem que aparecerá na guia.</span><span class="sxs-lookup"><span data-stu-id="42a4f-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="42a4f-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-147">Click **OK**.</span></span> <span data-ttu-id="42a4f-148">A nova guia aparecerá na grade de botões.</span><span class="sxs-lookup"><span data-stu-id="42a4f-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="42a4f-149">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="42a4f-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="42a4f-150">No Commerce, vá para **Varejo e Comércio** &gt; **TI de Varejo e Comércio** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-150">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="42a4f-151">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="42a4f-152">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="42a4f-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42a4f-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="42a4f-153">Additional resources</span></span>

[<span data-ttu-id="42a4f-154">Visão geral de recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="42a4f-154">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="42a4f-155">Habilitar ADLS em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="42a4f-155">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="42a4f-156">Habilitar recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="42a4f-156">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="42a4f-157">Habilitar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="42a4f-157">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="42a4f-158">Cancelar recomendações personalizadas</span><span class="sxs-lookup"><span data-stu-id="42a4f-158">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="42a4f-159">Adicionar recomendações dos produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="42a4f-159">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="42a4f-160">Ajustar os resultados das recomendações de AI-ML</span><span class="sxs-lookup"><span data-stu-id="42a4f-160">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="42a4f-161">Criar manualmente recomendações selecionadas</span><span class="sxs-lookup"><span data-stu-id="42a4f-161">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="42a4f-162">Criar recomendações com dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="42a4f-162">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="42a4f-163">Perguntas frequentes sobre recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="42a4f-163">Product recommendations FAQ</span></span>](faq-recommendations.md)