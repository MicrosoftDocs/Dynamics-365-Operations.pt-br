---
title: Configurar um canal de varejo
description: Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 713cbe68c151b6893519843611089941cabf0e70
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800582"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="30701-103">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="30701-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="30701-104">Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="30701-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="30701-105">O Dynamics 365 Commerce oferece suporte a vários canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="30701-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="30701-106">Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais).</span><span class="sxs-lookup"><span data-stu-id="30701-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="30701-107">Cada canal de loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe.</span><span class="sxs-lookup"><span data-stu-id="30701-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="30701-108">Você deve configurar todos esses elementos para poder criar um canal de loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="30701-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="30701-109">Antes de criar um canal de varejo, certifique-se de seguir os [pré-requisitos do canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="30701-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="30701-110">Criar e configurar um novo canal de varejo</span><span class="sxs-lookup"><span data-stu-id="30701-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="30701-111">No painel de navegação, vá para **Módulos \> Canais \> Lojas \> Todas as lojas**.</span><span class="sxs-lookup"><span data-stu-id="30701-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="30701-112">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="30701-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="30701-113">No campo **Nome**, forneça um nome para o novo canal.</span><span class="sxs-lookup"><span data-stu-id="30701-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="30701-114">No campo **Número da loja**, forneça um número de loja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="30701-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="30701-115">O número pode ser alfanumérico e ter no máximo 10 caracteres.</span><span class="sxs-lookup"><span data-stu-id="30701-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="30701-116">Na lista suspensa **Entidade legal**, insira a entidade legal apropriada.</span><span class="sxs-lookup"><span data-stu-id="30701-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="30701-117">Na lista suspensa **Depósito**, insira o depósito apropriado.</span><span class="sxs-lookup"><span data-stu-id="30701-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="30701-118">No campo **Fuso horário da loja**, selecione o fuso horário apropriado.</span><span class="sxs-lookup"><span data-stu-id="30701-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="30701-119">Na lista suspensa **Grupo de impostos**, selecione um grupo de impostos apropriado para a loja.</span><span class="sxs-lookup"><span data-stu-id="30701-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="30701-120">No campo **Moeda**, selecione a moeda apropriada.</span><span class="sxs-lookup"><span data-stu-id="30701-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="30701-121">No campo **Catálogo de endereços do cliente**, forneça um catálogo de endereços válido.</span><span class="sxs-lookup"><span data-stu-id="30701-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="30701-122">No campo **Cliente padrão**, forneça um cliente padrão válido.</span><span class="sxs-lookup"><span data-stu-id="30701-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="30701-123">No campo **Perfil de funcionalidade**, selecione um perfil de funcionalidade se aplicável.</span><span class="sxs-lookup"><span data-stu-id="30701-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="30701-124">No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.</span><span class="sxs-lookup"><span data-stu-id="30701-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="30701-125">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30701-125">On the action pane, select **Save**.</span></span>

<span data-ttu-id="30701-126">A imagem a seguir mostra a criação de um novo canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="30701-126">The following image shows the creation of a new retail channel.</span></span>

![Novo canal de varejo](media/channel-setup-retail-1.png)

<span data-ttu-id="30701-128">A imagem a seguir mostra um exemplo de canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="30701-128">The following image shows an example retail channel.</span></span>

![Exemplo de canal de varejo](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="30701-130">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="30701-130">Other settings</span></span>

<span data-ttu-id="30701-131">Existem várias outras configurações opcionais que podem ser definidas nas seções **Demonstrativo/fechamento** e **Diversos** conforme as necessidades da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="30701-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="30701-132">Além disso, consulte [Layouts de tela para o ponto de venda (PDV)](pos-screen-layouts.md) para obter informações sobre como configurar o layout de tela padrão na seção **Layout da tela** e [Configurar e instalar Retail Hardware Station](retail-hardware-station-configuration-installation.md) para obter informações de configuração sobre a seção **Estações de hardware**.</span><span class="sxs-lookup"><span data-stu-id="30701-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="30701-133">A imagem a seguir mostra um exemplo de configuração da instalação de canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="30701-133">The following image shows an example retail channel setup configuration.</span></span>

![Exemplo de configuração de canal de varejo](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="30701-135">Outras configurações de canal</span><span class="sxs-lookup"><span data-stu-id="30701-135">Additional channel set up</span></span>

<span data-ttu-id="30701-136">Existem outros itens que precisam ser configurados para um canal e que podem ser encontrados no **Painel de ação** da seção **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="30701-136">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="30701-137">Outras tarefas necessárias para a configuração do canal online incluem configurar métodos de pagamento, declaração de valores em caixa, modos de entrega, conta de receita/despesa, seções, a atribuição de grupo de orçamento e cofres.</span><span class="sxs-lookup"><span data-stu-id="30701-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="30701-138">A imagem a seguir mostra várias opções adicionais de configuração de canal de varejo na guia **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="30701-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Configurar o canal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="30701-140">Configurar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="30701-140">Set up payment methods</span></span>

<span data-ttu-id="30701-141">Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.</span><span class="sxs-lookup"><span data-stu-id="30701-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="30701-142">No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="30701-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="30701-143">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="30701-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="30701-144">No painel de navegação, selecione o método de pagamento desejado.</span><span class="sxs-lookup"><span data-stu-id="30701-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="30701-145">Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.</span><span class="sxs-lookup"><span data-stu-id="30701-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="30701-146">Defina as configurações adicionais necessárias para o tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="30701-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="30701-147">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30701-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="30701-148">A imagem a seguir mostra um exemplo de método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="30701-148">The following image shows an example of a cash payment method.</span></span>

![Exemplo de métodos de pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="30701-150">Configurar a declaração de valores em caixa</span><span class="sxs-lookup"><span data-stu-id="30701-150">Set up cash declaration</span></span>

1. <span data-ttu-id="30701-151">No painel de ação, selecione a guia **Configurar** e, depois, **Declaração de valores em caixa**.</span><span class="sxs-lookup"><span data-stu-id="30701-151">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="30701-152">No painel de ação, selecione **Novo** e crie todas as denominações aplicáveis de **Moeda** e **Nota**.</span><span class="sxs-lookup"><span data-stu-id="30701-152">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="30701-153">A imagem a seguir mostra um exemplo de declaração de valores em caixa.</span><span class="sxs-lookup"><span data-stu-id="30701-153">The following image shows an example of a cash declaration.</span></span>

![Configurar declarações de valores em caixa](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="30701-155">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="30701-155">Set up modes of delivery</span></span>

<span data-ttu-id="30701-156">Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.</span><span class="sxs-lookup"><span data-stu-id="30701-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="30701-157">Para alterar ou adicionar um modo de entrega, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="30701-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="30701-158">No painel de navegação, vá para **Módulos \> Gerenciamento de estoque \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="30701-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="30701-159">No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.</span><span class="sxs-lookup"><span data-stu-id="30701-159">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="30701-160">Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal.</span><span class="sxs-lookup"><span data-stu-id="30701-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="30701-161">Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="30701-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="30701-162">A imagem a seguir mostra um exemplo de modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="30701-162">The following image shows an example of a mode of delivery.</span></span>

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="30701-164">Configurar conta de receita/despesa</span><span class="sxs-lookup"><span data-stu-id="30701-164">Set up income/expense account</span></span>

<span data-ttu-id="30701-165">Para configurar a conta de receita/despesa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="30701-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="30701-166">No painel de ação, selecione a guia **Configurar** e, depois, **Conta de receita/despesa**.</span><span class="sxs-lookup"><span data-stu-id="30701-166">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="30701-167">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="30701-167">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="30701-168">Em **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="30701-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="30701-169">Em **Nome de pesquisa**, insira um nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="30701-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="30701-170">Em **Tipo de conta**, insira o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="30701-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="30701-171">Insira o texto de **Linha de mensagem 1**, **Linha de mensagem 2**, **Texto da guia 1** e **Texto da guia 2**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="30701-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="30701-172">Em **Lançamento**, insira as informações de lançamento.</span><span class="sxs-lookup"><span data-stu-id="30701-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="30701-173">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30701-173">On the action pane, select **Save**.</span></span>

<span data-ttu-id="30701-174">A imagem a seguir mostra um exemplo de conta de receita/despesa.</span><span class="sxs-lookup"><span data-stu-id="30701-174">The following image shows an example of an income/expense account.</span></span>

![Configurar contas de receita/despesa](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="30701-176">Configurar seções</span><span class="sxs-lookup"><span data-stu-id="30701-176">Set up sections</span></span>

<span data-ttu-id="30701-177">Para configurar seções, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="30701-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="30701-178">No painel de ação, selecione a guia **Configurar** e clique em **Seções**.</span><span class="sxs-lookup"><span data-stu-id="30701-178">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="30701-179">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="30701-179">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="30701-180">Em **Número da seção**, insira um número de seção.</span><span class="sxs-lookup"><span data-stu-id="30701-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="30701-181">Em **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="30701-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="30701-182">Em **Tamanho da seção**, insira um tamanho de seção.</span><span class="sxs-lookup"><span data-stu-id="30701-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="30701-183">Defina configurações adicionais para **Geral** e **Estatísticas de venda**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="30701-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="30701-184">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30701-184">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="30701-185">Configurar uma atribuição de grupo de orçamento</span><span class="sxs-lookup"><span data-stu-id="30701-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="30701-186">Para configurar uma atribuição de grupo de orçamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="30701-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="30701-187">No painel de ação, selecione a guia **Configurar** e, depois, **Atribuição de grupo de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="30701-187">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="30701-188">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="30701-188">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="30701-189">Na lista suspensa **Grupo de orçamento**, selecione um grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="30701-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="30701-190">Na lista suspensa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="30701-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="30701-191">No painel de ação, selecione **Salvar**</span><span class="sxs-lookup"><span data-stu-id="30701-191">On the action pane, select **Save**</span></span>

<span data-ttu-id="30701-192">A imagem a seguir mostra um exemplo de configuração de atribuição de grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="30701-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurar atribuições de grupo de orçamento](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="30701-194">Configurar cofres</span><span class="sxs-lookup"><span data-stu-id="30701-194">Set up safes</span></span>

<span data-ttu-id="30701-195">Para configurar cofres, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="30701-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="30701-196">No painel de ação, selecione a guia **Configurar** e clique em **Cofres**.</span><span class="sxs-lookup"><span data-stu-id="30701-196">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="30701-197">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="30701-197">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="30701-198">Insira um nome para o cofre.</span><span class="sxs-lookup"><span data-stu-id="30701-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="30701-199">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30701-199">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30701-200">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="30701-200">Additional resources</span></span>

[<span data-ttu-id="30701-201">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="30701-201">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="30701-202">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="30701-202">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="30701-203">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="30701-203">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="30701-204">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="30701-204">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
