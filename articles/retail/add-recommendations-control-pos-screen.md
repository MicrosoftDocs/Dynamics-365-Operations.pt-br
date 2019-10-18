---
title: Adicionar um controle de recomendações à tela de transação em dispositivos do PDV
description: Este tópico descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer de layout de tela no Microsoft Dynamics 365 for Retail.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
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
ms.openlocfilehash: d646c8ba559ba3e8d2175911e76c57d25eff02ca
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278120"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="624b3-103">Adicionar um controle de recomendações à tela de transação em dispositivos do PDV</span><span class="sxs-lookup"><span data-stu-id="624b3-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="624b3-104">Este tópico descreve como adicionar um controle de recomendações à tela da transação em um dispositivo de ponto de venda (PDV) usando o designer de layout de tela no Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="624b3-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="624b3-105">Para obter mais informações sobre recomendações de produtos, leia as [recomendações de produtos na documentação do PDV.](product.md)</span><span class="sxs-lookup"><span data-stu-id="624b3-105">For more information about product recommendations, read the  [product recommendations on POS documentation.](product.md)</span></span>


<span data-ttu-id="624b3-106">Você pode exibir as recomendações de produtos no dispositivo do PDV ao usar o Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="624b3-106">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="624b3-107">Para exibir recomendações de produto, é necessário adicionar um controle à tela de transação usando o designer do layout da tela.</span><span class="sxs-lookup"><span data-stu-id="624b3-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="624b3-108">Abrir o designer do layout</span><span class="sxs-lookup"><span data-stu-id="624b3-108">Open Layout designer</span></span>

1. <span data-ttu-id="624b3-109">Vá para **Varejo** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="624b3-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="624b3-110">Use o Filtro Rápido para localizar a tela à qual você deseja adicionar o controle.</span><span class="sxs-lookup"><span data-stu-id="624b3-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="624b3-111">Por exemplo, filtre o campo **ID do layout da tela** usando um valor de **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="624b3-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="624b3-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="624b3-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="624b3-113">Por exemplo, selecione **Nome: F2CP16:9M ID do layout da tela: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="624b3-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="624b3-114">Clique em **Designer de layout**.</span><span class="sxs-lookup"><span data-stu-id="624b3-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="624b3-115">Acompanhe os avisos para iniciar o designer do layout.</span><span class="sxs-lookup"><span data-stu-id="624b3-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="624b3-116">Quando as credenciais forem solicitadas, insira as mesmas credenciais usadas quando o designer do layout foi iniciado na página **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="624b3-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="624b3-117">Ao entrar, uma página semelhante à abaixo aparecerá.</span><span class="sxs-lookup"><span data-stu-id="624b3-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="624b3-118">O layout será diferente dependendo as personalizações feitas para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="624b3-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="624b3-119">[![Designer de layout](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="624b3-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="624b3-120">Escolher um opção de exibição</span><span class="sxs-lookup"><span data-stu-id="624b3-120">Choose a display option</span></span>

<span data-ttu-id="624b3-121">Há duas opções de configurações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="624b3-121">There are two configurations options available.</span></span> <span data-ttu-id="624b3-122">Escolha a opção que funciona melhor para o armazenamento e siga as demais instruções para concluir a configuração do controle.</span><span class="sxs-lookup"><span data-stu-id="624b3-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="624b3-123">As duas opções são:</span><span class="sxs-lookup"><span data-stu-id="624b3-123">The two options are:</span></span>

- <span data-ttu-id="624b3-124">As recomendações são sempre visíveis.</span><span class="sxs-lookup"><span data-stu-id="624b3-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="624b3-125">Uma guia **Recomendações** será exibida na grade à direita da tela.</span><span class="sxs-lookup"><span data-stu-id="624b3-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="624b3-126">Torne as recomendações sempre visíveis</span><span class="sxs-lookup"><span data-stu-id="624b3-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="624b3-127">Reduza a altura da área de detalhes das linhas de transação para que ela tenha a mesma altura do painel do cliente à esquerda.</span><span class="sxs-lookup"><span data-stu-id="624b3-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="624b3-128">[![Altura da área de detalhes das linhas de transação reduzida](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="624b3-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="624b3-129">No menu à esquerda, arraste e solte o controle de recomendações entre a área de detalhes de linhas de transação e a grade de botões na parte inferior do centro da tela de transação.</span><span class="sxs-lookup"><span data-stu-id="624b3-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="624b3-130">Redimensione o controle para que ele caiba no espaço.</span><span class="sxs-lookup"><span data-stu-id="624b3-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="624b3-131">[![Controle de recomendações adicionado ao layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="624b3-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="624b3-132">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="624b3-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="624b3-133">No Dynamics 365 for Retail, vá para **Varejo** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="624b3-133">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="624b3-134">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="624b3-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="624b3-135">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="624b3-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="624b3-136">Adicione uma guia Recomendações à grade de botões no lado direito da tela</span><span class="sxs-lookup"><span data-stu-id="624b3-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="624b3-137">Clique com o botão direito no espaço vazio abaixo da última guia na grade de botões localizada no lado direito da página.</span><span class="sxs-lookup"><span data-stu-id="624b3-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="624b3-138">Clique em **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="624b3-138">Click **Customize**.</span></span>

    <span data-ttu-id="624b3-139">[![Personalização - Caixa de diálogo Controle de guias](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="624b3-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="624b3-140">Clique em **Nova guia**.</span><span class="sxs-lookup"><span data-stu-id="624b3-140">Click **New tab**.</span></span>
4. <span data-ttu-id="624b3-141">Localize a nova guia que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="624b3-141">Find the new tab that you just added.</span></span> <span data-ttu-id="624b3-142">Talvez você precise rolar para baixo.</span><span class="sxs-lookup"><span data-stu-id="624b3-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="624b3-143">No menu suspenso **Conteúdos**, selecione **Produtos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="624b3-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="624b3-144">[![Seleção de produtos recomendados no campo Conteúdo](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="624b3-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="624b3-145">No campo **Etiqueta**, digite um nome para a guia das recomendações. Por exemplo, digite 'Produtos recomendados'.</span><span class="sxs-lookup"><span data-stu-id="624b3-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="624b3-146">No campo **Imagem**, selecione a imagem que aparecerá na guia.</span><span class="sxs-lookup"><span data-stu-id="624b3-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="624b3-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="624b3-147">Click **OK**.</span></span> <span data-ttu-id="624b3-148">A nova guia aparecerá na grade de botões.</span><span class="sxs-lookup"><span data-stu-id="624b3-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="624b3-149">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="624b3-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="624b3-150">No Dynamics 365 for Retail, vá para **Varejo** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="624b3-150">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="624b3-151">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="624b3-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="624b3-152">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="624b3-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="624b3-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="624b3-153">Additional resources</span></span>

[<span data-ttu-id="624b3-154">recomendações de produtos no PDV</span><span class="sxs-lookup"><span data-stu-id="624b3-154">product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="624b3-155">visão geral das recomendações de produtos</span><span class="sxs-lookup"><span data-stu-id="624b3-155">product recommendations overview</span></span>](../commerce/product-recommendations.md)
