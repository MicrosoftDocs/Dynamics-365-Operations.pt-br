---
title: Configurar um canal de varejo
description: Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/23/2021
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
ms.openlocfilehash: 3f1f5dc2c8402d9b6b68a049f804932812eb74c0
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937525"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="9497d-103">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="9497d-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9497d-104">Este tópico descreve como criar um novo canal de varejo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9497d-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9497d-105">O Dynamics 365 Commerce oferece suporte a vários canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="9497d-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="9497d-106">Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais).</span><span class="sxs-lookup"><span data-stu-id="9497d-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="9497d-107">Cada canal de loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe.</span><span class="sxs-lookup"><span data-stu-id="9497d-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="9497d-108">Você deve configurar todos esses elementos para poder criar um canal de loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="9497d-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="9497d-109">Antes de criar um canal de varejo, certifique-se de seguir os [pré-requisitos do canal](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9497d-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="9497d-110">Criar e configurar um novo canal de varejo</span><span class="sxs-lookup"><span data-stu-id="9497d-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="9497d-111">No painel de navegação, vá para **Módulos \> Canais \> Lojas \> Todas as lojas**.</span><span class="sxs-lookup"><span data-stu-id="9497d-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="9497d-112">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9497d-112">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9497d-113">No campo **Nome**, forneça um nome para o novo canal.</span><span class="sxs-lookup"><span data-stu-id="9497d-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="9497d-114">No campo **Número da loja**, forneça um número de loja exclusivo.</span><span class="sxs-lookup"><span data-stu-id="9497d-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="9497d-115">O número pode ser alfanumérico e ter no máximo 10 caracteres.</span><span class="sxs-lookup"><span data-stu-id="9497d-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="9497d-116">Na lista suspensa **Entidade legal**, insira a entidade legal apropriada.</span><span class="sxs-lookup"><span data-stu-id="9497d-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="9497d-117">Na lista suspensa **Depósito**, insira o depósito apropriado.</span><span class="sxs-lookup"><span data-stu-id="9497d-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="9497d-118">No campo **Fuso horário da loja**, selecione o fuso horário apropriado.</span><span class="sxs-lookup"><span data-stu-id="9497d-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="9497d-119">Na lista suspensa **Grupo de impostos**, selecione um grupo de impostos apropriado para a loja.</span><span class="sxs-lookup"><span data-stu-id="9497d-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="9497d-120">No campo **Moeda**, selecione a moeda apropriada.</span><span class="sxs-lookup"><span data-stu-id="9497d-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="9497d-121">No campo **Catálogo de endereços do cliente**, forneça um catálogo de endereços válido.</span><span class="sxs-lookup"><span data-stu-id="9497d-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="9497d-122">No campo **Cliente padrão**, forneça um cliente padrão válido.</span><span class="sxs-lookup"><span data-stu-id="9497d-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="9497d-123">No campo **Perfil de funcionalidade**, selecione um perfil de funcionalidade se aplicável.</span><span class="sxs-lookup"><span data-stu-id="9497d-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="9497d-124">No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.</span><span class="sxs-lookup"><span data-stu-id="9497d-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="9497d-125">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9497d-125">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9497d-126">A imagem a seguir mostra a criação de um novo canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="9497d-126">The following image shows the creation of a new retail channel.</span></span>

![Novo canal de varejo](media/channel-setup-retail-1.png)

<span data-ttu-id="9497d-128">A imagem a seguir mostra um exemplo de canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="9497d-128">The following image shows an example retail channel.</span></span>

![Exemplo de canal de varejo](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="9497d-130">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="9497d-130">Other settings</span></span>

<span data-ttu-id="9497d-131">Existem várias outras configurações opcionais que podem ser definidas nas seções **Demonstrativo/fechamento** e **Diversos** conforme as necessidades da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="9497d-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="9497d-132">Além disso, consulte [Layouts de tela para o ponto de venda (PDV)](pos-screen-layouts.md) para obter informações sobre como configurar o layout de tela padrão na seção **Layout da tela** e [Configurar e instalar Retail Hardware Station](retail-hardware-station-configuration-installation.md) para obter informações de configuração sobre a seção **Estações de hardware**.</span><span class="sxs-lookup"><span data-stu-id="9497d-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="9497d-133">A imagem a seguir mostra um exemplo de configuração da instalação de canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="9497d-133">The following image shows an example retail channel setup configuration.</span></span>

![Exemplo de configuração de canal de varejo](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="9497d-135">Outras configurações de canal</span><span class="sxs-lookup"><span data-stu-id="9497d-135">Additional channel set up</span></span>

<span data-ttu-id="9497d-136">Existem outros itens que precisam ser configurados para um canal e que podem ser encontrados no Painel de Ação da seção **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9497d-136">There are additional items that need to be set up for a channel that can be found on the Action Pane under the **Set up** section.</span></span>

<span data-ttu-id="9497d-137">Outras tarefas necessárias para a configuração do canal online incluem configurar métodos de pagamento, declaração de valores em caixa, modos de entrega, conta de receita/despesa, seções, a atribuição de grupo de orçamento e cofres.</span><span class="sxs-lookup"><span data-stu-id="9497d-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="9497d-138">A imagem a seguir mostra várias opções adicionais de configuração de canal de varejo na guia **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9497d-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Configurar o canal](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="9497d-140">Configurar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="9497d-140">Set up payment methods</span></span>

<span data-ttu-id="9497d-141">Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.</span><span class="sxs-lookup"><span data-stu-id="9497d-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="9497d-142">No Painel de Ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="9497d-142">On the Action Pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="9497d-143">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9497d-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9497d-144">No painel de navegação, selecione o método de pagamento desejado.</span><span class="sxs-lookup"><span data-stu-id="9497d-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="9497d-145">Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.</span><span class="sxs-lookup"><span data-stu-id="9497d-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="9497d-146">Defina as configurações adicionais necessárias para o tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="9497d-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="9497d-147">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9497d-147">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9497d-148">A imagem a seguir mostra um exemplo de método de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="9497d-148">The following image shows an example of a cash payment method.</span></span>

![Exemplo de métodos de pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="9497d-150">Configurar a declaração de valores em caixa</span><span class="sxs-lookup"><span data-stu-id="9497d-150">Set up cash declaration</span></span>

1. <span data-ttu-id="9497d-151">No Painel de Ação, selecione a guia **Configurar** e, depois, **Declaração de valores em caixa**.</span><span class="sxs-lookup"><span data-stu-id="9497d-151">On the Action Pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="9497d-152">No Painel de Ação, selecione **Novo** e crie todas as denominações aplicáveis de **Moeda** e **Nota**.</span><span class="sxs-lookup"><span data-stu-id="9497d-152">On the Action Pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="9497d-153">A imagem a seguir mostra um exemplo de declaração de valores em caixa.</span><span class="sxs-lookup"><span data-stu-id="9497d-153">The following image shows an example of a cash declaration.</span></span>

![Configurar declarações de valores em caixa](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="9497d-155">Configurar os modos de entrega</span><span class="sxs-lookup"><span data-stu-id="9497d-155">Set up modes of delivery</span></span>

<span data-ttu-id="9497d-156">Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configuração** no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="9497d-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the Action Pane.</span></span>  

<span data-ttu-id="9497d-157">Para alterar ou adicionar um modo de entrega, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9497d-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="9497d-158">No painel de navegação, vá para **Módulos \> Gerenciamento de estoque \> Modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="9497d-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="9497d-159">No Painel de Ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.</span><span class="sxs-lookup"><span data-stu-id="9497d-159">On the Action Pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="9497d-160">Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal.</span><span class="sxs-lookup"><span data-stu-id="9497d-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="9497d-161">Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="9497d-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="9497d-162">A imagem a seguir mostra um exemplo de modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="9497d-162">The following image shows an example of a mode of delivery.</span></span>

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="9497d-164">Configurar conta de receita/despesa</span><span class="sxs-lookup"><span data-stu-id="9497d-164">Set up income/expense account</span></span>

<span data-ttu-id="9497d-165">Para configurar a conta de receita/despesa, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9497d-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="9497d-166">No Painel de Ação, selecione a guia **Configurar** e, depois, **Conta de Receita/Despesa**.</span><span class="sxs-lookup"><span data-stu-id="9497d-166">On the Action Pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="9497d-167">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9497d-167">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9497d-168">Em **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="9497d-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="9497d-169">Em **Nome de pesquisa**, insira um nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9497d-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="9497d-170">Em **Tipo de conta**, insira o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="9497d-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="9497d-171">Insira o texto de **Linha de mensagem 1**, **Linha de mensagem 2**, **Texto da guia 1** e **Texto da guia 2**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9497d-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="9497d-172">Em **Lançamento**, insira as informações de lançamento.</span><span class="sxs-lookup"><span data-stu-id="9497d-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="9497d-173">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9497d-173">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9497d-174">A imagem a seguir mostra um exemplo de conta de receita/despesa.</span><span class="sxs-lookup"><span data-stu-id="9497d-174">The following image shows an example of an income/expense account.</span></span>

![Configurar contas de receita/despesa](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="9497d-176">Configurar seções</span><span class="sxs-lookup"><span data-stu-id="9497d-176">Set up sections</span></span>

<span data-ttu-id="9497d-177">Para configurar seções, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9497d-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="9497d-178">No Painel de Ação, selecione a guia **Configurar** e clique em **Seções**.</span><span class="sxs-lookup"><span data-stu-id="9497d-178">On the Action Pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="9497d-179">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9497d-179">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9497d-180">Em **Número da seção**, insira um número de seção.</span><span class="sxs-lookup"><span data-stu-id="9497d-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="9497d-181">Em **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="9497d-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="9497d-182">Em **Tamanho da seção**, insira um tamanho de seção.</span><span class="sxs-lookup"><span data-stu-id="9497d-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="9497d-183">Defina configurações adicionais para **Geral** e **Estatísticas de venda**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9497d-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="9497d-184">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9497d-184">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="9497d-185">Configurar uma atribuição de grupo de orçamento</span><span class="sxs-lookup"><span data-stu-id="9497d-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="9497d-186">Para configurar uma atribuição de grupo de orçamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9497d-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="9497d-187">No Painel de Ação, selecione a guia **Configurar** e, depois, **Atribuição de grupo de atendimento**.</span><span class="sxs-lookup"><span data-stu-id="9497d-187">On the Action Pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="9497d-188">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9497d-188">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9497d-189">Na lista suspensa **Grupo de orçamento**, selecione um grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="9497d-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="9497d-190">Na lista suspensa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="9497d-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="9497d-191">No Painel de Ações, selecione **Salvar**</span><span class="sxs-lookup"><span data-stu-id="9497d-191">On the Action Pane, select **Save**</span></span>

<span data-ttu-id="9497d-192">A imagem a seguir mostra um exemplo de configuração de atribuição de grupo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="9497d-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Configurar atribuições de grupo de orçamento](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="9497d-194">Configurar cofres</span><span class="sxs-lookup"><span data-stu-id="9497d-194">Set up safes</span></span>

<span data-ttu-id="9497d-195">Para configurar cofres, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="9497d-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="9497d-196">No Painel de Ações, selecione a guia **Configurar** e clique em **Cofres**.</span><span class="sxs-lookup"><span data-stu-id="9497d-196">On the Action Pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="9497d-197">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9497d-197">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9497d-198">Insira um nome para o cofre.</span><span class="sxs-lookup"><span data-stu-id="9497d-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="9497d-199">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9497d-199">On the Action Pane, select **Save**.</span></span>

### <a name="ensure-unique-transaction-ids"></a><span data-ttu-id="9497d-200">Garantir IDs de transação exclusivas</span><span class="sxs-lookup"><span data-stu-id="9497d-200">Ensure unique transaction IDs</span></span>

<span data-ttu-id="9497d-201">A partir da versão 10.0.18 do Commerce, as IDs de transação geradas para o ponto de venda (PDV) são sequenciais e incluem as seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="9497d-201">As of the Commerce version 10.0.18 , transaction IDs generated for the point of sale (POS) are sequential and include the following parts:</span></span>

- <span data-ttu-id="9497d-202">Uma parte fixa, que é uma concatenação da ID de armazenamento e da ID de terminal.</span><span class="sxs-lookup"><span data-stu-id="9497d-202">A fixed part, which is a concatenation of store ID and terminal ID.</span></span> 
- <span data-ttu-id="9497d-203">Uma parte sequencial, que é uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="9497d-203">A sequential part, which is a number sequence.</span></span> 

<span data-ttu-id="9497d-204">Especificamente, o formato é *{store}-{terminal}-{numbersequence}*.</span><span class="sxs-lookup"><span data-stu-id="9497d-204">Specifically, the format is *{store}-{terminal}-{numbersequence}*.</span></span> 

<span data-ttu-id="9497d-205">Como as IDs de transação podem ser geradas nos modos offline e online, foram geradas instâncias de IDs de transação duplicadas.</span><span class="sxs-lookup"><span data-stu-id="9497d-205">Because transaction IDs can be generated in offline and online modes, there have been instances of duplicate transaction IDs being generated.</span></span> <span data-ttu-id="9497d-206">A eliminação de IDs de transação duplicada requer muita correção manual de dados.</span><span class="sxs-lookup"><span data-stu-id="9497d-206">Eliminating duplicate transaction IDs requires a lot of manual data fixing.</span></span> 

<span data-ttu-id="9497d-207">Com a versão 10.0.19 do Commerce, o formato da ID da transação foi atualizado para remover a parte sequencial e, em vez disso, usa um número de 13 dígitos gerado pelo cálculo do tempo em milissegundos desde 1970.</span><span class="sxs-lookup"><span data-stu-id="9497d-207">With Commerce version 10.0.19, the transaction ID format has been updated to remove the sequential part and instead uses a 13-digit number generated by calculating the time in milliseconds since 1970.</span></span> <span data-ttu-id="9497d-208">Com essa alteração, o novo formato da ID da transação é *{store}-{terminal}-{millisecondsSince1970}*.</span><span class="sxs-lookup"><span data-stu-id="9497d-208">With this change, the new transaction ID format is *{store}-{terminal}-{millisecondsSince1970}*.</span></span> <span data-ttu-id="9497d-209">Essa atualização torna a ID de transação não sequencial e garante que as IDs de transação sejam sempre exclusivas.</span><span class="sxs-lookup"><span data-stu-id="9497d-209">This update makes the transaction ID non-sequential and ensures that transaction IDs are always unique.</span></span> 

> [!NOTE]
> <span data-ttu-id="9497d-210">As IDs de transação são destinadas somente ao uso interno do sistema e, portanto, não precisam ser sequenciais.</span><span class="sxs-lookup"><span data-stu-id="9497d-210">Transaction IDs are meant for internal system use only, so they are not required to be sequential.</span></span> <span data-ttu-id="9497d-211">No entanto, muitos países exigem que as IDs de recebimento sejam sequenciais.</span><span class="sxs-lookup"><span data-stu-id="9497d-211">However, many countries require receipt IDs to be sequential.</span></span>

<span data-ttu-id="9497d-212">O novo recurso de formato da ID da transação pode ser habilitado no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="9497d-212">The new transaction ID format feature can be enabled from the **Feature management** workspace.</span></span> 

<span data-ttu-id="9497d-213">Para habilitar o uso de novas IDs de transação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9497d-213">To enable the use of new transaction IDs, follow these steps:</span></span>

1. <span data-ttu-id="9497d-214">No Commerce headquarters, vá para **Administração do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="9497d-214">In Commerce headquarters, go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="9497d-215">Filtrar para o módulo "varejo e comércio".</span><span class="sxs-lookup"><span data-stu-id="9497d-215">Filter for the "retail and commerce" module.</span></span>
1. <span data-ttu-id="9497d-216">Procure o nome do recurso **Habilitar nova ID da transação para evitar IDs da transação duplicadas**.</span><span class="sxs-lookup"><span data-stu-id="9497d-216">Search for the **Enable new transaction id to avoid duplicate transaction ids** feature name.</span></span>
1. <span data-ttu-id="9497d-217">Selecione o recurso e depois **Habilitar Agora** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="9497d-217">Select the feature, and then select **Enable Now** in the right pane.</span></span>  
1. <span data-ttu-id="9497d-218">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="9497d-218">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="9497d-219">Execute os trabalhos **Configuração do canal 1070** e **Gravador de tarefas do PDV 1170** para sincronizar o recurso habilitado para os armazenamentos.</span><span class="sxs-lookup"><span data-stu-id="9497d-219">Run the **1070 Channel configuration** and **1170 POS task recorder** jobs to synchronize the enabled feature to the stores.</span></span>
1. <span data-ttu-id="9497d-220">Depois que as alterações forem enviadas para os armazenamentos, os terminais de PDV deverão ser fechados e reabertos para usar o novo formato de ID da transação.</span><span class="sxs-lookup"><span data-stu-id="9497d-220">After the changes have been sent to the stores, POS terminals must be closed and reopened to use the new transaction ID format.</span></span> 

> [!NOTE]
> <span data-ttu-id="9497d-221">Depois que o novo recurso de formato de ID da transação estiver habilitado, você não poderá desabilitar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="9497d-221">After the new transaction ID format feature is enabled, you will not be able to disable this feature.</span></span> <span data-ttu-id="9497d-222">Se precisar ser desabilitado, contate o Suporte do Commerce.</span><span class="sxs-lookup"><span data-stu-id="9497d-222">If it must be disabled, please contact Commerce Support.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9497d-223">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9497d-223">Additional resources</span></span>

[<span data-ttu-id="9497d-224">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="9497d-224">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="9497d-225">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="9497d-225">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="9497d-226">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="9497d-226">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="9497d-227">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="9497d-227">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
