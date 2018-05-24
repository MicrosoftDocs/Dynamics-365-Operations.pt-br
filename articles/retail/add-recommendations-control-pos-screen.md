---
title: "Adicionar um controle de recomendações à página de transação em um dispositivo do PDV"
description: "Este tópico descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer do layout da tela no Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: eac70614770189d1e45f347b282c94e645e95b00
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="42afc-103">Adicionar um controle de recomendações à página de transação em um dispositivo do PDV</span><span class="sxs-lookup"><span data-stu-id="42afc-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!include [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="42afc-104">Estamos removendo a versão atual do serviço de recomendação de produto, pois estamos remodelando esse recurso em um algoritmo melhor com recursos mais novos orientados ao varejo.</span><span class="sxs-lookup"><span data-stu-id="42afc-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="42afc-105">Para obter mais informações consulte [Recursos removidos ou substituídos](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="42afc-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span> 

<span data-ttu-id="42afc-106">Este tópico descreve como adicionar um controle de recomendações à tela de transação em um dispositivo do ponto de venda (PDV) usando o designer do layout da tela no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="42afc-106">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="42afc-107">Você pode exibir recomendações de produto no dispositivo do PDV ao usar o Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="42afc-107">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="42afc-108">*Recomendações* são itens nos quais o cliente pode estar interessado com base no histórico de compras, itens em sua lista de desejos e itens que outros clientes compraram online e em lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="42afc-108">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="42afc-109">Para exibir recomendações de produto, é necessário adicionar um controle à tela de transação usando o designer do layout da tela.</span><span class="sxs-lookup"><span data-stu-id="42afc-109">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="42afc-110">Abrir o designer do layout</span><span class="sxs-lookup"><span data-stu-id="42afc-110">Open Layout designer</span></span>
1.  <span data-ttu-id="42afc-111">Vá para **Varejo** &gt; **Configuração do canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="42afc-111">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="42afc-112">Use o Filtro Rápido para localizar a tela à qual você deseja adicionar o controle.</span><span class="sxs-lookup"><span data-stu-id="42afc-112">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="42afc-113">Por exemplo, filtre o campo **ID do layout da tela** usando um valor de “F2CP16:9M”.</span><span class="sxs-lookup"><span data-stu-id="42afc-113">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="42afc-114">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="42afc-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="42afc-115">Por exemplo, selecione “Nome: F2CP16:9M ID do layout da tela: F2CP16:9M”.</span><span class="sxs-lookup"><span data-stu-id="42afc-115">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="42afc-116">Clique em **Designer de layout**.</span><span class="sxs-lookup"><span data-stu-id="42afc-116">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="42afc-117">Acompanhe os avisos para iniciar o designer do layout.</span><span class="sxs-lookup"><span data-stu-id="42afc-117">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="42afc-118">Quando credenciais forem solicitadas, insira as mesmas credenciais usadas quando o designer do layout foi iniciado na página **Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="42afc-118">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="42afc-119">Ao entrar, uma página semelhante à abaixo aparecerá.</span><span class="sxs-lookup"><span data-stu-id="42afc-119">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="42afc-120">O layout será diferente dependendo as personalizações feitas para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="42afc-120">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="42afc-121">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Escolha uma opção de exibição.</span><span class="sxs-lookup"><span data-stu-id="42afc-121">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="42afc-122">Há duas opções de configurações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="42afc-122">There are two configurations options available.</span></span> <span data-ttu-id="42afc-123">Escolha a opção que funciona melhor para o armazenamento e siga as demais instruções para concluir a configuração do controle.</span><span class="sxs-lookup"><span data-stu-id="42afc-123">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="42afc-124">As duas opções são:</span><span class="sxs-lookup"><span data-stu-id="42afc-124">The two options are:</span></span>
-   <span data-ttu-id="42afc-125">As recomendações são sempre visíveis.</span><span class="sxs-lookup"><span data-stu-id="42afc-125">Recommendations are always visible.</span></span>
-   <span data-ttu-id="42afc-126">Uma guia **Recomendações** será exibida na grade à direita da tela.</span><span class="sxs-lookup"><span data-stu-id="42afc-126">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="42afc-127">Para tornar as recomendações sempre visíveis</span><span class="sxs-lookup"><span data-stu-id="42afc-127">To make recommendations always visible</span></span>

1.  <span data-ttu-id="42afc-128">Reduza a altura da área de detalhes das linhas de transação para que ela tenha a mesma altura do painel do cliente à esquerda.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="42afc-128">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="42afc-129">No menu à esquerda, arraste e solte o controle de recomendações entre a área de detalhes de linhas de transação e a grade de botões na parte inferior do centro da tela de transação.</span><span class="sxs-lookup"><span data-stu-id="42afc-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="42afc-130">Redimensione o controle para que ele caiba no espaço.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="42afc-130">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="42afc-131">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="42afc-131">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="42afc-132">No Dynamics 365 for Retail, vá para **Varejo** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="42afc-132">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="42afc-133">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="42afc-133">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="42afc-134">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="42afc-134">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="42afc-135">Para adicionar uma guia Recomendações à grade de botões no lado direito da tela</span><span class="sxs-lookup"><span data-stu-id="42afc-135">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="42afc-136">Clique com o botão direito no espaço vazio abaixo da última guia na grade de botões localizada no lado direito da página.</span><span class="sxs-lookup"><span data-stu-id="42afc-136">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="42afc-137">Clique em **Personalizar**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="42afc-137">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="42afc-138">Clique em **Nova guia**.</span><span class="sxs-lookup"><span data-stu-id="42afc-138">Click **New tab**.</span></span>
4.  <span data-ttu-id="42afc-139">Localize a nova guia que você acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="42afc-139">Find the new tab that you just added.</span></span> <span data-ttu-id="42afc-140">Talvez você precise rolar para baixo.</span><span class="sxs-lookup"><span data-stu-id="42afc-140">You may need to scroll down.</span></span>
5.  <span data-ttu-id="42afc-141">No menu suspenso **Conteúdos**, selecione **Produtos recomendados**.</span><span class="sxs-lookup"><span data-stu-id="42afc-141">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="42afc-142">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="42afc-142">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="42afc-143">No campo **Etiqueta** , digite um nome para a guia das recomendações. Por exemplo, digite “Produtos recomendados”.</span><span class="sxs-lookup"><span data-stu-id="42afc-143">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="42afc-144">No campo **Imagem**, selecione a imagem que aparecerá na guia.</span><span class="sxs-lookup"><span data-stu-id="42afc-144">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="42afc-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="42afc-145">Click **OK**.</span></span> <span data-ttu-id="42afc-146">A nova guia aparecerá na grade de botões.</span><span class="sxs-lookup"><span data-stu-id="42afc-146">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="42afc-147">Clique no **X** para salvar e sair do designer do layout.</span><span class="sxs-lookup"><span data-stu-id="42afc-147">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="42afc-148">No Dynamics 365 for Retail, vá para **Varejo** &gt; **TI de Varejo** &gt; **Agendas de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="42afc-148">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="42afc-149">Na lista, selecione **1090 Registros**.</span><span class="sxs-lookup"><span data-stu-id="42afc-149">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="42afc-150">Clique em **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="42afc-150">Click **Run now**.</span></span>


<a name="additional-resources"></a><span data-ttu-id="42afc-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="42afc-151">Additional resources</span></span>
--------

[<span data-ttu-id="42afc-152">Visão geral de recomendações de produtos personalizados</span><span class="sxs-lookup"><span data-stu-id="42afc-152">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




