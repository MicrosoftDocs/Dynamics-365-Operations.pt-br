---
title: Criar e atualizar uma política de devolução e reembolso para um canal
description: Este tópico explica como configurar uma política de devoluções e reembolsos para um canal.
author: ShalabhjainMSFT
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: e23291130d55fdfb5c2e2077b78c221866d72c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792066"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="3796a-103">Criar e atualizar uma política de devolução e reembolso para um canal</span><span class="sxs-lookup"><span data-stu-id="3796a-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3796a-104">A política de devolução de canal no Dynamics 365 Commerce permite que os varejistas definam os encargos nos quais os meios de pagamento possam ser permitidos para processar uma devolução em um dispositivo de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="3796a-104">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="3796a-105">Este tópico descreve as etapas para configurar uma política de devoluções e reembolsos para um canal.</span><span class="sxs-lookup"><span data-stu-id="3796a-105">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="3796a-106">No momento, o escopo da política está limitado à definição de meios de pagamento que possam ser permitidos para um canal.</span><span class="sxs-lookup"><span data-stu-id="3796a-106">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="3796a-107">A lista "permitido" baseia-se nos métodos de pagamento usados para fazer a compra.</span><span class="sxs-lookup"><span data-stu-id="3796a-107">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="3796a-108">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3796a-108">For example:</span></span>

- <span data-ttu-id="3796a-109">Se uma compra tiver sido feita com o uso de um vale-presente, a política da loja será processar os reembolsos apenas para um novo vale-presente ou para conceder crédito da loja.</span><span class="sxs-lookup"><span data-stu-id="3796a-109">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="3796a-110">Se uma venda é feita em dinheiro, as opções permitidas para reembolso são dinheiro, vale-presente e conta do cliente, mas não cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="3796a-110">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="3796a-111">Habilitar política de devolução</span><span class="sxs-lookup"><span data-stu-id="3796a-111">Enable return policy</span></span>

<span data-ttu-id="3796a-112">Para habilitar a funcionalidade de política de devolução de canais, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3796a-112">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="3796a-113">Vá para o espaço de trabalho **Gerenciamento de Recursos** no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3796a-113">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="3796a-114">Procure o recurso **Habilitar políticas de devolução de canal** na lista de nomes de recursos.</span><span class="sxs-lookup"><span data-stu-id="3796a-114">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="3796a-115">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="3796a-115">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="3796a-116">Configurar política de devolução</span><span class="sxs-lookup"><span data-stu-id="3796a-116">Configure return policy</span></span>

<span data-ttu-id="3796a-117">Siga estas etapas para configurar uma política de devolução para uma loja de varejo ou canal de varejo online.</span><span class="sxs-lookup"><span data-stu-id="3796a-117">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="3796a-118">Vá para **Retail e Commerce** \> **Configuração do Canal** \> **Devoluções** \> **Política de devolução de canais**.</span><span class="sxs-lookup"><span data-stu-id="3796a-118">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="3796a-119">Selecionar **Novo** para criar um novo modelo de política de devolução.</span><span class="sxs-lookup"><span data-stu-id="3796a-119">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="3796a-120">Para usar um modelo existente, selecione o modelo no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="3796a-120">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="3796a-121">Para novos modelos, adicione um nome e uma descrição que o ajudarão a identificar a política quando ela estiver sendo aplicada ao canal.</span><span class="sxs-lookup"><span data-stu-id="3796a-121">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="3796a-122">![Adicionar nova política de devolução](media/Return-policy-page1.png "Adicionar nova política de devolução")</span><span class="sxs-lookup"><span data-stu-id="3796a-122">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="3796a-123">Na seção **Métodos de pagamento de reembolso permitidos**, defina meios de pagamento de devolução **Permitidos** que sejam específicos de cada método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3796a-123">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="3796a-124">![Adicionar métodos de pagamento](media/Return-policy-page2.PNG "Definir métodos de pagamento permitidos por tipo de pagamento")</span><span class="sxs-lookup"><span data-stu-id="3796a-124">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="3796a-125">Os métodos de pagamento derivam dos métodos de pagamento definidos para a organização.</span><span class="sxs-lookup"><span data-stu-id="3796a-125">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="3796a-126">Adicionar um tipo de meio de pagamento de devolução permitido para cada método de pagamento listado garantirá que as devoluções possam ser feitas no tipo de meio de pagamento de devolução permitido.</span><span class="sxs-lookup"><span data-stu-id="3796a-126">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="3796a-127">Associe o modelo de política de devolução com as lojas em que ele será usado.</span><span class="sxs-lookup"><span data-stu-id="3796a-127">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="3796a-128">Selecione **Adicionar** na guia **Canais de varejo** e associe os canais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3796a-128">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="3796a-129">Na caixa de diálogo **Escolher nós organizacionais**, selecione os armazenamentos, regiões e organizações aos quais o modelo será associado.</span><span class="sxs-lookup"><span data-stu-id="3796a-129">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="3796a-130">Apenas um modelo de política de devolução pode ser associado a cada loja.</span><span class="sxs-lookup"><span data-stu-id="3796a-130">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="3796a-131">Use os botões de seta para selecionar lojas, regiões ou organizações.</span><span class="sxs-lookup"><span data-stu-id="3796a-131">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="3796a-132">A data de efetivação na política será a data na qual as políticas são aplicadas aos canais e os trabalhos do canal são executados.</span><span class="sxs-lookup"><span data-stu-id="3796a-132">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="3796a-133">![Escolha a caixa de diálogo dos nós da organização](media/Return-policy-page3.PNG "Escolha a caixa de diálogo dos nós da organização")</span><span class="sxs-lookup"><span data-stu-id="3796a-133">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="3796a-134">Na página **Agenda de distribuição**, execute o trabalho **1070** para disponibilizar a política de devolução do canal para o PDV.</span><span class="sxs-lookup"><span data-stu-id="3796a-134">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="3796a-135">Visualize a política de devolução de canal no PDV.</span><span class="sxs-lookup"><span data-stu-id="3796a-135">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="3796a-136">Siga as etapas em um dos exemplos a seguir para exibir os tipos de meio de pagamento de devolução permitidos no PDV.</span><span class="sxs-lookup"><span data-stu-id="3796a-136">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="3796a-137">Entre no PDV como um caixa ou gerente.</span><span class="sxs-lookup"><span data-stu-id="3796a-137">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="3796a-138">Em **Turno e gaveta**, selecione **Mostrar diário**.</span><span class="sxs-lookup"><span data-stu-id="3796a-138">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="3796a-139">Selecione a transação que faz parte da devolução.</span><span class="sxs-lookup"><span data-stu-id="3796a-139">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="3796a-140">Selecione os itens a serem reembolsados e escolha o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3796a-140">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="3796a-141">Se o meio de pagamento selecionado estiver na lista permitida de tipos de meio de pagamento de devolução, o caixa poderá concluir a transação.</span><span class="sxs-lookup"><span data-stu-id="3796a-141">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="3796a-142">Se o meio de pagamento selecionado não for permitido, uma mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="3796a-142">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="3796a-143">Selecione **Valor Devido** para exibir uma lista de todos os tipos de meio de pagamento de devolução permitidos.</span><span class="sxs-lookup"><span data-stu-id="3796a-143">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="3796a-144">- ou -</span><span class="sxs-lookup"><span data-stu-id="3796a-144">-or-</span></span>

1. <span data-ttu-id="3796a-145">Entre no PDV como um caixa ou gerente.</span><span class="sxs-lookup"><span data-stu-id="3796a-145">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="3796a-146">Selecione **Transação de Devolução** e insira a ID de recibo usando uma verificação de código de barras ou por entrada manual.</span><span class="sxs-lookup"><span data-stu-id="3796a-146">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="3796a-147">Selecione a transação que faz parte da devolução.</span><span class="sxs-lookup"><span data-stu-id="3796a-147">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="3796a-148">Selecione os itens a serem reembolsados e escolha o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3796a-148">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="3796a-149">Se o meio de pagamento selecionado estiver na lista permitida de tipos de meio de pagamento de devolução, o caixa poderá concluir a transação.</span><span class="sxs-lookup"><span data-stu-id="3796a-149">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="3796a-150">Se o meio de pagamento selecionado não for permitido, uma mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="3796a-150">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="3796a-151">Selecione **Valor Devido** para exibir uma lista de todos os tipos de meio de pagamento de devolução permitidos.</span><span class="sxs-lookup"><span data-stu-id="3796a-151">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="3796a-152">![Reembolso não permitido](media/Return-policy-page6.png "Tipo de reembolso não permitido")</span><span class="sxs-lookup"><span data-stu-id="3796a-152">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="3796a-153">![Lista de métodos de pagamento](media/Return-policy-page5.PNG "Tipos de reembolso não permitidos")</span><span class="sxs-lookup"><span data-stu-id="3796a-153">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
