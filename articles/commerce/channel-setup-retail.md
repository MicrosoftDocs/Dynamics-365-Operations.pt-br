---
title: Configurar um canal de varejo
description: Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8ac01f36912fa5e8a09bb4f324ef272cec737aa1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002372"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="8138a-103">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="8138a-103">Set up a retail channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8138a-104">Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8138a-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8138a-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="8138a-105">Overview</span></span>

<span data-ttu-id="8138a-106">O Dynamics 365 Commerce oferece suporte a vários canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="8138a-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="8138a-107">Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais).</span><span class="sxs-lookup"><span data-stu-id="8138a-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="8138a-108">Cada canal de loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe.</span><span class="sxs-lookup"><span data-stu-id="8138a-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="8138a-109">Você deve configurar todos esses elementos para poder criar um canal de loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="8138a-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="8138a-110">Antes de criar um canal de varejo, certifique-se de seguir os [pré-requisitos do canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="8138a-110">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="8138a-111">Criar e configurar um novo canal de varejo</span><span class="sxs-lookup"><span data-stu-id="8138a-111">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="8138a-112">No painel de navegação, vá para **Módulos \> Canais \> Lojas \> Todas as lojas**.</span><span class="sxs-lookup"><span data-stu-id="8138a-112">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="8138a-113">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8138a-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8138a-114">No campo **Nome**, forneça um nome para o novo canal.</span><span class="sxs-lookup"><span data-stu-id="8138a-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="8138a-115">No campo **Número da loja**, forneça um número de loja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8138a-115">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="8138a-116">O número pode ser alfanumérico e ter no máximo 10 caracteres.</span><span class="sxs-lookup"><span data-stu-id="8138a-116">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="8138a-117">Na lista suspensa **Entidade legal**, insira a entidade legal apropriada.</span><span class="sxs-lookup"><span data-stu-id="8138a-117">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="8138a-118">Na lista suspensa **Depósito**, insira o depósito apropriado.</span><span class="sxs-lookup"><span data-stu-id="8138a-118">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="8138a-119">No campo **Fuso horário da loja**, selecione o fuso horário apropriado.</span><span class="sxs-lookup"><span data-stu-id="8138a-119">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="8138a-120">Na lista suspensa **Grupo de impostos**, selecione um grupo de impostos apropriado para a loja.</span><span class="sxs-lookup"><span data-stu-id="8138a-120">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="8138a-121">No campo **Moeda**, selecione a moeda apropriada.</span><span class="sxs-lookup"><span data-stu-id="8138a-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="8138a-122">No campo **Catálogo de endereços do cliente**, forneça um catálogo de endereços válido.</span><span class="sxs-lookup"><span data-stu-id="8138a-122">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="8138a-123">No campo **Cliente padrão**, forneça um cliente padrão válido.</span><span class="sxs-lookup"><span data-stu-id="8138a-123">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="8138a-124">No campo **Perfil de funcionalidade**, selecione um perfil de funcionalidade se aplicável.</span><span class="sxs-lookup"><span data-stu-id="8138a-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="8138a-125">No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.</span><span class="sxs-lookup"><span data-stu-id="8138a-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="8138a-126">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8138a-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8138a-127">A imagem a seguir mostra a criação de um novo canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="8138a-127">The following image shows the creation of a new retail channel.</span></span>

![Novo canal de varejo](media/channel-setup-retail-1.png)

<span data-ttu-id="8138a-129">A imagem a seguir mostra um exemplo de canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="8138a-129">The following image shows an example retail channel.</span></span>

![Exemplo de canal de varejo](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="8138a-131">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="8138a-131">Other settings</span></span>

<span data-ttu-id="8138a-132">Existem várias outras configurações opcionais que podem ser definidas nas seções **Demonstrativo/fechamento** e **Diversos** conforme as necessidades da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="8138a-132">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="8138a-133">Além disso, consulte [Layouts de tela para o ponto de venda (PDV)](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json) para obter informações sobre como configurar o layout de tela padrão na seção **Layout da tela** e [Configurar e instalar Retail Hardware Station](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation) para obter informações de configuração sobre a seção **Estações de hardware**.</span><span class="sxs-lookup"><span data-stu-id="8138a-133">In addition, see [Screen layouts for the point of sale (POS)](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="8138a-134">A imagem a seguir mostra um exemplo de configuração da instalação de canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="8138a-134">The following image shows an example retail channel setup configuration.</span></span>

![Exemplo de configuração de canal de varejo](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="8138a-136">Outras configurações de canal</span><span class="sxs-lookup"><span data-stu-id="8138a-136">Additional channel set up</span></span>

<span data-ttu-id="8138a-137">Existem outros itens que precisam ser configurados para um canal e que podem ser encontrados no **Painel de ação** da seção **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="8138a-137">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="8138a-138">Outras tarefas necessárias para a configuração do canal online incluem configurar métodos de pagamento, declaração de valores em caixa, modos de entrega, conta de receita/despesa, seções, a atribuição de grupo de orçamento e cofres.</span><span class="sxs-lookup"><span data-stu-id="8138a-138">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="8138a-139">A imagem a seguir mostra várias opções adicionais de configuração de canal de varejo na guia **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="8138a-139">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Configurar o canal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="8138a-141">Configurar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="8138a-141">Set up payment methods</span></span>

<span data-ttu-id="8138a-142">Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.</span><span class="sxs-lookup"><span data-stu-id="8138a-142">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="8138a-143">No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="8138a-143">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="8138a-144">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8138a-144">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8138a-145">No painel de navegação, selecione o método de pagamento desejado.</span><span class="sxs-lookup"><span data-stu-id="8138a-145">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="8138a-146">Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.</span><span class="sxs-lookup"><span data-stu-id="8138a-146">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="8138a-147">Defina as configurações adicionais necessárias para o tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="8138a-147">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="8138a-148">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8138a-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8138a-149">A imagem a seguir mostra um exemplo de método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="8138a-149">The following image shows an example of a cash payment method.</span></span>

![Exemplo de métodos de pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="8138a-151">Configurar a declaração de valores em caixa</span><span class="sxs-lookup"><span data-stu-id="8138a-151">Set up cash declaration</span></span>

1. <span data-ttu-id="8138a-152">No painel de ação, selecione a guia **Configurar** e, depois, **Declaração de valores em caixa**.</span><span class="sxs-lookup"><span data-stu-id="8138a-152">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="8138a-153">No painel de ação, selecione **Novo**e crie todas as denominações aplicáveis de **Moeda** e **Nota**.</span><span class="sxs-lookup"><span data-stu-id="8138a-153">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="8138a-154">A imagem a seguir mostra um exemplo de declaração de valores em caixa.</span><span class="sxs-lookup"><span data-stu-id="8138a-154">The following image shows an example of a cash declaration.</span></span>

![Configurar declarações de valores em caixa](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="8138a-156">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="8138a-156">Set up modes of delivery</span></span>

<span data-ttu-id="8138a-157">Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.</span><span class="sxs-lookup"><span data-stu-id="8138a-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="8138a-158">Para alterar ou adicionar um modo de entrega, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8138a-158">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="8138a-159">No painel de navegação, vá para **Módulos \> Gerenciamento de estoque \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="8138a-159">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="8138a-160">No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.</span><span class="sxs-lookup"><span data-stu-id="8138a-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="8138a-161">Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal.</span><span class="sxs-lookup"><span data-stu-id="8138a-161">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="8138a-162">Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="8138a-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="8138a-163">A imagem a seguir mostra um exemplo de modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="8138a-163">The following image shows an example of a mode of delivery.</span></span>

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="8138a-165">Configurar conta de receita/despesa</span><span class="sxs-lookup"><span data-stu-id="8138a-165">Set up income/expense account</span></span>

<span data-ttu-id="8138a-166">Para configurar a conta de receita/despesa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8138a-166">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="8138a-167">No painel de ação, selecione a guia **Configurar** e, depois, **Conta de receita/despesa**.</span><span class="sxs-lookup"><span data-stu-id="8138a-167">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="8138a-168">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8138a-168">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8138a-169">Em **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="8138a-169">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="8138a-170">Em **Nome de pesquisa**, insira um nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8138a-170">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="8138a-171">Em **Tipo de conta**, insira o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="8138a-171">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="8138a-172">Insira o texto de **Linha de mensagem 1**, **Linha de mensagem 2**, **Texto da guia 1** e **Texto da guia 2**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8138a-172">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="8138a-173">Em **Lançamento**, insira as informações de lançamento.</span><span class="sxs-lookup"><span data-stu-id="8138a-173">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="8138a-174">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8138a-174">On the action pane, select **Save**.</span></span>

<span data-ttu-id="8138a-175">A imagem a seguir mostra um exemplo de conta de receita/despesa.</span><span class="sxs-lookup"><span data-stu-id="8138a-175">The following image shows an example of an income/expense account.</span></span>

![Configurar contas de receita/despesa](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="8138a-177">Configurar seções</span><span class="sxs-lookup"><span data-stu-id="8138a-177">Set up sections</span></span>

<span data-ttu-id="8138a-178">Para configurar seções, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8138a-178">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="8138a-179">No painel de ação, selecione a guia **Configurar** e clique em **Seções**.</span><span class="sxs-lookup"><span data-stu-id="8138a-179">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="8138a-180">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8138a-180">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8138a-181">Em **Número da seção**, insira um número de seção.</span><span class="sxs-lookup"><span data-stu-id="8138a-181">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="8138a-182">Em **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="8138a-182">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="8138a-183">Em **Tamanho da seção**, insira um tamanho de seção.</span><span class="sxs-lookup"><span data-stu-id="8138a-183">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="8138a-184">Defina configurações adicionais para **Geral** e **Estatísticas de venda**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8138a-184">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="8138a-185">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8138a-185">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="8138a-186">Configurar uma atribuição de grupo de orçamento</span><span class="sxs-lookup"><span data-stu-id="8138a-186">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="8138a-187">Para configurar uma atribuição de grupo de orçamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8138a-187">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="8138a-188">No painel de ação, selecione a guia **Configurar** e, depois, **Atribuição de grupo de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="8138a-188">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="8138a-189">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8138a-189">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8138a-190">Na lista suspensa **Grupo de orçamento**, selecione um grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="8138a-190">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="8138a-191">Na lista suspensa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="8138a-191">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="8138a-192">No painel de ação, selecione **Salvar**</span><span class="sxs-lookup"><span data-stu-id="8138a-192">On the action pane, select **Save**</span></span>

<span data-ttu-id="8138a-193">A imagem a seguir mostra um exemplo de configuração de atribuição de grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="8138a-193">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurar atribuições de grupo de orçamento](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="8138a-195">Configurar cofres</span><span class="sxs-lookup"><span data-stu-id="8138a-195">Set up safes</span></span>

<span data-ttu-id="8138a-196">Para configurar cofres, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8138a-196">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="8138a-197">No painel de ação, selecione a guia **Configurar** e clique em **Cofres**.</span><span class="sxs-lookup"><span data-stu-id="8138a-197">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="8138a-198">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8138a-198">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="8138a-199">Insira um nome para o cofre.</span><span class="sxs-lookup"><span data-stu-id="8138a-199">Enter a name for the safe.</span></span>
1. <span data-ttu-id="8138a-200">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8138a-200">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8138a-201">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8138a-201">Additional resources</span></span>

[<span data-ttu-id="8138a-202">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="8138a-202">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="8138a-203">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="8138a-203">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="8138a-204">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="8138a-204">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="8138a-205">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="8138a-205">Set up a call center channel</span></span>](channel-setup-callcenter.md)

