---
title: "Adicionar um controle de recomendações à página de transação em um dispositivo do PDV"
description: "Este tópico descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer do layout da tela no Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 7f8522110c0d7d5277b0b3f3c7b21d8605d43f2c
ms.contentlocale: pt-br
ms.lasthandoff: 06/29/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="9efb3-103">Adicionar um controle de recomendações à página de transação em um dispositivo do PDV</span><span class="sxs-lookup"><span data-stu-id="9efb3-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="9efb3-104">Este tópico descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer do layout da tela no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="9efb3-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="9efb3-105">Você pode exibir recomendações de produto no dispositivo do PDV ao usar o Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="9efb3-105">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="9efb3-106">*Recomendações* são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="9efb3-106">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="9efb3-107">Para exibir recomendações de produto, é necessário adicionar um controle à tela de transação usando o designer do layout da tela.</span><span class="sxs-lookup"><span data-stu-id="9efb3-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="9efb3-108">Abrir o designer do layout</span><span class="sxs-lookup"><span data-stu-id="9efb3-108">Open Layout designer</span></span>
1.  <span data-ttu-id="9efb3-109">Vá para **Varejo** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="9efb3-110">Use o Filtro Rápido para localizar a tela à qual você deseja adicionar o controle.</span><span class="sxs-lookup"><span data-stu-id="9efb3-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="9efb3-111">Por exemplo, filtre o campo **ID do layout da tela** usando um valor de “F2CP16:9M”.</span><span class="sxs-lookup"><span data-stu-id="9efb3-111">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="9efb3-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="9efb3-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="9efb3-113">Por exemplo, selecione “Nome: F2CP16:9M ID do layout da tela: F2CP16:9M”.</span><span class="sxs-lookup"><span data-stu-id="9efb3-113">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="9efb3-114">Clique em **Designer de layout**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-114">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="9efb3-115">Acompanhe os avisos para iniciar o designer do layout.</span><span class="sxs-lookup"><span data-stu-id="9efb3-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="9efb3-116">Quando credenciais forem solicitadas, insira as mesmas credenciais usadas quando o designer do layout foi iniciado na página **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="9efb3-117">Ao entrar, uma página semelhante à abaixo aparecerá.</span><span class="sxs-lookup"><span data-stu-id="9efb3-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="9efb3-118">O layout será diferente dependendo as personalizações feitas para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9efb3-118">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="9efb3-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Escolha uma opção de exibição.</span><span class="sxs-lookup"><span data-stu-id="9efb3-119">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="9efb3-120">Há duas opções de configurações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9efb3-120">There are two configurations options available.</span></span> <span data-ttu-id="9efb3-121">Escolha a opção que funciona melhor para o armazenamento e siga as demais instruções para concluir a configuração do controle.</span><span class="sxs-lookup"><span data-stu-id="9efb3-121">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="9efb3-122">As duas opções são:</span><span class="sxs-lookup"><span data-stu-id="9efb3-122">The two options are:</span></span>
-   <span data-ttu-id="9efb3-123">As recomendações são sempre visíveis.</span><span class="sxs-lookup"><span data-stu-id="9efb3-123">Recommendations are always visible.</span></span>
-   <span data-ttu-id="9efb3-124">Uma guia **Recomendações** será exibida na grade à direita da tela.</span><span class="sxs-lookup"><span data-stu-id="9efb3-124">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="9efb3-125">Para tornar as recomendações sempre visíveis</span><span class="sxs-lookup"><span data-stu-id="9efb3-125">To make recommendations always visible</span></span>

1.  <span data-ttu-id="9efb3-126">Reduza a altura da área de detalhes das linhas de transação para que ela tenha a mesma altura do painel do cliente à esquerda.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="9efb3-126">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="9efb3-127">No menu à esquerda, arraste e solte o controle de recomendações entre a área de detalhes de linhas de transação e a grade de botões na parte inferior do centro da tela de transação.</span><span class="sxs-lookup"><span data-stu-id="9efb3-127">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="9efb3-128">Redimensione o controle para que ele caiba no espaço.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="9efb3-128">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="9efb3-129">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="9efb3-129">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="9efb3-130">No Dynamics 365 for Retail, vá para **Varejo** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-130">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="9efb3-131">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-131">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="9efb3-132">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-132">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="9efb3-133">Para adicionar uma guia Recomendações à grade de botões no lado direito da tela</span><span class="sxs-lookup"><span data-stu-id="9efb3-133">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="9efb3-134">Clique com o botão direito no espaço vazio abaixo da última guia na grade de botões localizada no lado direito da página.</span><span class="sxs-lookup"><span data-stu-id="9efb3-134">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="9efb3-135">Clique em **Personalizar**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="9efb3-135">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="9efb3-136">Clique em **Nova guia**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-136">Click **New tab**.</span></span>
4.  <span data-ttu-id="9efb3-137">Localize a nova guia que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="9efb3-137">Find the new tab that you just added.</span></span> <span data-ttu-id="9efb3-138">Talvez você precise rolar para baixo.</span><span class="sxs-lookup"><span data-stu-id="9efb3-138">You may need to scroll down.</span></span>
5.  <span data-ttu-id="9efb3-139">No menu suspenso **Conteúdos**, selecione **Produtos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-139">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="9efb3-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="9efb3-140">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="9efb3-141">No campo **Etiqueta**, digite um nome para a guia de recomendações.</span><span class="sxs-lookup"><span data-stu-id="9efb3-141">In the **Label** field, type a name for the recommendations tab.</span></span> <span data-ttu-id="9efb3-142">Por exemplo, digite “Produtos recomendados”.</span><span class="sxs-lookup"><span data-stu-id="9efb3-142">For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="9efb3-143">No campo **Imagem**, selecione a imagem que aparecerá na guia.</span><span class="sxs-lookup"><span data-stu-id="9efb3-143">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="9efb3-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-144">Click **OK**.</span></span> <span data-ttu-id="9efb3-145">A nova guia aparecerá na grade de botões.</span><span class="sxs-lookup"><span data-stu-id="9efb3-145">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="9efb3-146">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="9efb3-146">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="9efb3-147">No Dynamics 365 for Retail, vá para **Varejo** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-147">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="9efb3-148">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-148">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="9efb3-149">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="9efb3-149">Click **Run now**.</span></span>


<a name="see-also"></a><span data-ttu-id="9efb3-150">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9efb3-150">See also</span></span>
--------

[<span data-ttu-id="9efb3-151">Visão geral de recomendações de produto personalizado</span><span class="sxs-lookup"><span data-stu-id="9efb3-151">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




