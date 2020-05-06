---
title: Configurar BOPIS em um ambiente do Dynamics 365 Commerce
description: Este tópico explica como configurar e fazer compras online, retirar na loja (BOPIS) em um ambiente do Microsoft Dynamics 365 Commerce após ele ter sido provisionado.
author: rubendel
manager: annbe
ms.date: 04/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 956d66d09885d4d54655ce25b3aa7ba6a9c34cf4
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282787"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-environment"></a><span data-ttu-id="7abbd-103">Configurar BOPIS em um ambiente do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7abbd-103">Configure BOPIS in a Dynamics 365 Commerce environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7abbd-104">Este tópico explica como configurar e fazer compras online, retirar na loja (BOPIS) em um ambiente do Microsoft Dynamics 365 Commerce após o ambiente ter sido provisionado.</span><span class="sxs-lookup"><span data-stu-id="7abbd-104">This topic explains how to configure buy online, pickup in store (BOPIS) in a Microsoft Dynamics 365 Commerce environment after the environment has been provisioned.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="7abbd-105">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="7abbd-105">Prerequisite</span></span>

<span data-ttu-id="7abbd-106">Conclua os procedimentos neste tópico somente após o provisionamento e a configuração do seu ambiente de visualização comercial.</span><span class="sxs-lookup"><span data-stu-id="7abbd-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned and configured.</span></span> <span data-ttu-id="7abbd-107">Para obter informações sobre como provisionar e configurar seu ambiente, consulte [Provisionar um ambiente de visualização do Dynamics 365 Commerce](provisioning-guide.md) e [Configurar um ambiente de visualização do Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span><span class="sxs-lookup"><span data-stu-id="7abbd-107">For information about how to provision and configure your environment, see [Provision a Dynamics 365 Commerce preview environment](provisioning-guide.md) and [Configure a Dynamics 365 Commerce preview environment](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span></span>

<span data-ttu-id="7abbd-108">Depois que o ambiente do Commerce tiver sido provisionado e configurado de ponta a ponta, é possível usar esse tópico para habilitar cenários de BOPIS.</span><span class="sxs-lookup"><span data-stu-id="7abbd-108">After your Commerce environment has been provisioned and configured end to end, you can use this topic to enable BOPIS scenarios.</span></span>

## <a name="configure-the-pos"></a><span data-ttu-id="7abbd-109">Configurar o PDV</span><span class="sxs-lookup"><span data-stu-id="7abbd-109">Configure the POS</span></span>

### <a name="configure-modern-pos"></a><span data-ttu-id="7abbd-110">Configurar o PDV Moderno</span><span class="sxs-lookup"><span data-stu-id="7abbd-110">Configure Modern POS</span></span>

<span data-ttu-id="7abbd-111">Os cenários de BOPIS que envolvem um pagamento em cartão de crédito exigem uma estação de hardware.</span><span class="sxs-lookup"><span data-stu-id="7abbd-111">BOPIS scenarios that involve a credit card payment require a hardware station.</span></span> <span data-ttu-id="7abbd-112">A estação de hardware é criada nos programas de PDV Moderno para clientes do Windows e Android.</span><span class="sxs-lookup"><span data-stu-id="7abbd-112">The hardware station is built into Modern POS for Windows and Android clients.</span></span> <span data-ttu-id="7abbd-113">Se você estiver usando o PDV em Nuvem ou o PDV Moderno para iOS, o cliente do ponto de venda (PDV) deve ser emparelhado com uma estação de hardware compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7abbd-113">If you're using Cloud POS or Modern POS for iOS, the point of sale (POS) client must be paired with a shared hardware station.</span></span> <span data-ttu-id="7abbd-114">Este tópico explica como configurar BOPIS para clientes do Windows e Android.</span><span class="sxs-lookup"><span data-stu-id="7abbd-114">This topic explains how to configure BOPIS for Windows and Android clients.</span></span> <span data-ttu-id="7abbd-115">Para mais informações sobre como configurar uma estação de hardware compartilhada, consulte [Configurar e instalar a estação de hardware do Retail](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="7abbd-115">For information about how to set up a shared hardware station, see [Configure and install Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span></span>

1. <span data-ttu-id="7abbd-116">Vá para **Varejo e comércio \> Configuração de canal \> Configuração do PDV \> Caixas registradoras**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-116">Go to **Retail and Commerce \> Channel setup \> POS setup \> Registers**.</span></span>
2. <span data-ttu-id="7abbd-117">Selecione registrar **SANFRAN-5** e, depois, **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-117">Select register **SANFRAN-5**, and then select **Edit**.</span></span>
3. <span data-ttu-id="7abbd-118">Altere o valor do campo **Perfil do hardware** de **HW002** para **HW001** e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-118">Change the value of the **Hardware profile** field from **HW002** to **HW001**, and then select **Save**.</span></span>
4. <span data-ttu-id="7abbd-119">Para sincronizar as alterações, vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-119">To synchronize the changes, go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="7abbd-120">Selecione a agenda de distribuição**1090** e selecione **Executar agora** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="7abbd-120">Select distribution schedule **1090**, and then, on the Action Pane, select **Run now**.</span></span>
6. <span data-ttu-id="7abbd-121">Selecione **Sim** e depois **OK** para iniciar a sincronização de dados.</span><span class="sxs-lookup"><span data-stu-id="7abbd-121">Select **Yes** and then **OK** to initiate data synchronization.</span></span> 

### <a name="install-modern-pos"></a><span data-ttu-id="7abbd-122">Instalar o PDV Moderno</span><span class="sxs-lookup"><span data-stu-id="7abbd-122">Install Modern POS</span></span>

1. <span data-ttu-id="7abbd-123">Vá para **Varejo e comércio \> Configuração de canal \> Configuração do PDV \> Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-123">Go to **Retail and Commerce \> Channel setup \> POS setup \> Devices**.</span></span>
2. <span data-ttu-id="7abbd-124">Selecione o dispositivo **SANFRANCIS-5**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-124">Select device **SANFRANCIS-5**.</span></span>
3. <span data-ttu-id="7abbd-125">No Painel de Ações, selecione **Download** e depois selecione **Arquivo de configuração**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-125">On the Action Pane, select **Download**, and then select **Configuration file**.</span></span>
4. <span data-ttu-id="7abbd-126">Selecione **Download** e depois **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-126">Select **Download**, and then select **Retail Modern POS**.</span></span> 
5. <span data-ttu-id="7abbd-127">Quando o download do arquivo **ModernPOSSetup.exe** for concluído, selecione **Abrir arquivo**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-127">When download of the **ModernPOSSetup.exe** file is completed, select **Open file**.</span></span>

    ![Abrir arquivo](./dev-itpro/media/PAYMENTS/openfile.png)

6. <span data-ttu-id="7abbd-129">Selecione **Avançar** para continuar o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="7abbd-129">Select **Next** to go through the installation process.</span></span> <span data-ttu-id="7abbd-130">Quando a instalação for concluída, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-130">When installation is completed, select **Close**.</span></span>

### <a name="activate-modern-pos"></a><span data-ttu-id="7abbd-131">Ativar o PDV Moderno</span><span class="sxs-lookup"><span data-stu-id="7abbd-131">Activate Modern POS</span></span>

1. <span data-ttu-id="7abbd-132">Na área de trabalho do Windows, selecione o botão **Iniciar** e insira **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-132">On the Windows desktop, select the **Start** button, and enter **Retail Modern POS**.</span></span>
2. <span data-ttu-id="7abbd-133">Selecione o aplicativo **Retail Modern POS** para iniciar a ativação.</span><span class="sxs-lookup"><span data-stu-id="7abbd-133">Select the **Retail Modern POS** application to initiate activation.</span></span>
3. <span data-ttu-id="7abbd-134">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-134">Select **Next**.</span></span> <span data-ttu-id="7abbd-135">Os campos **URL do servidor**, **ID do dispositivo** e **Número do registro** devem ser predefinidos usando as informações do arquivo de configuração baixado no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="7abbd-135">The **Server URL**, **Device ID**, and **Register number** fields should be preset by using information from the configuration file that you downloaded in the previous procedure.</span></span>
4. <span data-ttu-id="7abbd-136">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-136">Select **Activate**.</span></span>
5. <span data-ttu-id="7abbd-137">Uma caixa de diálogo de autenticação é exibida.</span><span class="sxs-lookup"><span data-stu-id="7abbd-137">An authentication dialog box appears.</span></span> <span data-ttu-id="7abbd-138">Selecione a conta que usa o endereço de email que foi associado previamente ao trabalhador **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-138">Select the account that uses the email address that was previously associated with worker **000713 - Andrew Collette**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7abbd-139">Se você ainda não associou um trabalhador à sua identidade, a ativação não terá êxito.</span><span class="sxs-lookup"><span data-stu-id="7abbd-139">If you haven't yet associated a worker with your identity, activation will be unsuccessful.</span></span> <span data-ttu-id="7abbd-140">Nesse caso, siga as etapas na seção "Associar um trabalhador à sua identidade" no tópico [Configurar um ambiente de visualização do Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).</span><span class="sxs-lookup"><span data-stu-id="7abbd-140">In this case, follow the steps under the "Associate a worker with your identity" section in the [Configure a Dynamics 365 Commerce preview environment](cpe-post-provisioning.md#associate-a-worker-with-your-identity) topic.</span></span>
    
6. <span data-ttu-id="7abbd-141">Quando for solicitado permitir que a sua organização gerencie o dispositivo, selecione **Somente este aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-141">When you're prompted to let your organization manage the device, select **This app only**.</span></span>
7. <span data-ttu-id="7abbd-142">Quando a ativação for concluída, selecione **Introdução**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-142">When activation is completed, select **Get started**.</span></span>

### <a name="enable-bopis-in-modern-pos"></a><span data-ttu-id="7abbd-143">Habilitar BOPIS no PDV Moderno</span><span class="sxs-lookup"><span data-stu-id="7abbd-143">Enable BOPIS in Modern POS</span></span>

1. <span data-ttu-id="7abbd-144">Faça logon no PDV Moderno usando **000713** como ID do operador e **123** como a senha.</span><span class="sxs-lookup"><span data-stu-id="7abbd-144">Sign in to Modern POS by using **000713** as the operator ID and **123** as the password.</span></span>
2. <span data-ttu-id="7abbd-145">Enquanto o vídeo do passo a passo introdutório estiver sendo exibido, marque as duas caixas de seleção no canto inferior esquerdo da caixa de diálogo e depois feche-a.</span><span class="sxs-lookup"><span data-stu-id="7abbd-145">While the introductory walkthrough video is playing, select the two check boxes in the lower-left corner of the dialog box, and then close the dialog box.</span></span>
3. <span data-ttu-id="7abbd-146">Caso não seja solicitado que você feche o turno, role para a direita na página **Inicial**, selecione **Fechar turno** e faça logon novamente no PDV.</span><span class="sxs-lookup"><span data-stu-id="7abbd-146">If you aren't prompted to close the shift, scroll to the right on the **Welcome** page, select **Close shift**, and then sign back in to the POS.</span></span>
4. <span data-ttu-id="7abbd-147">Após fazer o logon, quando solicitado, selecione **Executar uma operação sem gaveta**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-147">After you're signed in, when you're prompted, select **Perform a non-drawer operation**.</span></span>
5. <span data-ttu-id="7abbd-148">Na página **Inicial**, role para a direita e selecione a operação **Selecionar estação de hardware**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-148">On the **Welcome** page, scroll to the right, and select the **Select hardware station** operation.</span></span>
6. <span data-ttu-id="7abbd-149">Selecione **Gerenciar**, defina a opção **Usar estação de hardware** como **Ativado** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-149">Select **Manage**, set the **Use hardware station** option to **On**, and then select **OK**.</span></span>
7. <span data-ttu-id="7abbd-150">Saia do POS e entre novamente.</span><span class="sxs-lookup"><span data-stu-id="7abbd-150">Sign out of the POS, and then sign back in.</span></span>
8. <span data-ttu-id="7abbd-151">Depois de fazer logon, selecione **Abrir novo turno** e selecione **Gaveta**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-151">After you're signed in, select **Open a new shift**, and then select **Drawer**.</span></span>

## <a name="complete-a-bopis-scenario"></a><span data-ttu-id="7abbd-152">Concluir um cenário BOPIS</span><span class="sxs-lookup"><span data-stu-id="7abbd-152">Complete a BOPIS scenario</span></span>

### <a name="create-a-storefront-order-for-in-store-pickup"></a><span data-ttu-id="7abbd-153">Crie uma ordem da vitrine para retirada na loja</span><span class="sxs-lookup"><span data-stu-id="7abbd-153">Create a storefront order for in-store pickup</span></span>

1. <span data-ttu-id="7abbd-154">Vá para a URL especificada na etapa [Inicializar o e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) durante a configuração do ambiente.</span><span class="sxs-lookup"><span data-stu-id="7abbd-154">Go to the URL that you specified in the [Initialize e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) step during environment configuration.</span></span>
2. <span data-ttu-id="7abbd-155">Selecione um item e, depois, **Adicionar ao carrinho**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-155">Select an item, and select **Add to cart**.</span></span>
3. <span data-ttu-id="7abbd-156">Na página da sacola de compras, selecione **Retirar este item** na linha da ordem que acabou de adicionar.</span><span class="sxs-lookup"><span data-stu-id="7abbd-156">On the shopping bag page, select **Pick this up** for the order line that you just added.</span></span>
4. <span data-ttu-id="7abbd-157">Na caixa de diálogo **Selecionar uma loja**, insira **São Francisco** e, depois, selecione o botão **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-157">In the **Select a store** dialog box, enter **San Francisco**, and then select the **Search** button.</span></span>
5. <span data-ttu-id="7abbd-158">Na lista de resultados, encontre a loja em São Francisco e selecione **Retirar aqui**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-158">In the list of results, find the San Francisco store, and select **Pick up here**.</span></span>
6. <span data-ttu-id="7abbd-159">Na página da sacola de compras, selecione **Finalizar Compra como Convidado**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-159">On the shopping bag page, select **Checkout as Guest**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="7abbd-160">Para continuar com a finalização da compra, é necessário aceitar o aviso de cookies.</span><span class="sxs-lookup"><span data-stu-id="7abbd-160">To continue with checkout, you must accept the cookie notice.</span></span> <span data-ttu-id="7abbd-161">Este aviso aparece como um banner no topo da página da finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="7abbd-161">This notice appears as a banner at the top of the checkout page.</span></span>

7. <span data-ttu-id="7abbd-162">Para a forma de pagamento no cartão de crédito, insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="7abbd-162">For the credit card payment method, enter the following details:</span></span>

    - <span data-ttu-id="7abbd-163">**Nome do titular do cartão:** Insira qualquer nome.</span><span class="sxs-lookup"><span data-stu-id="7abbd-163">**Cardholder name:** Enter any name.</span></span>
    - <span data-ttu-id="7abbd-164">**Número do cartão:** Insira **4111-1111-1111-1111**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-164">**Card number:** Enter **4111-1111-1111-1111**.</span></span>
    - <span data-ttu-id="7abbd-165">**Data de vencimento:** Insira **20/10**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-165">**Expiration date:** Enter **10/20**.</span></span>
    - <span data-ttu-id="7abbd-166">**Código do valor de verificação do cartão (CVV)**: Insira **737**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-166">**Card verification value (CVV) code:** Enter **737**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7abbd-167">Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.</span><span class="sxs-lookup"><span data-stu-id="7abbd-167">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

8. <span data-ttu-id="7abbd-168">Continue a finalização da compra inserindo os detalhes do endereço de cobrança e selecione **Salvar e continuar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-168">Continue with checkout by entering details of the billing address, and then select **Save and continue**.</span></span>
9. <span data-ttu-id="7abbd-169">Quando a ordem estiver pronta para ser realizada, selecione **Finalizar compra**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-169">When the order is ready to be placed, select **Checkout**.</span></span>

### <a name="synchronize-online-orders-to-the-back-office"></a><span data-ttu-id="7abbd-170">Sincronizar ordens online para o back-office</span><span class="sxs-lookup"><span data-stu-id="7abbd-170">Synchronize online orders to the back office</span></span>

<span data-ttu-id="7abbd-171">Para obter informações sobre como sincronizar ordens online, consulte [Lançamento de vendas e pagamentos online](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span><span class="sxs-lookup"><span data-stu-id="7abbd-171">For information about how to synchronize online orders, see [Posting of online sales and payments](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span></span>

### <a name="pick-up-an-order-in-the-store"></a><span data-ttu-id="7abbd-172">Retirar um pedido na loja</span><span class="sxs-lookup"><span data-stu-id="7abbd-172">Pick up an order in the store</span></span>

1. <span data-ttu-id="7abbd-173">Entrar no PDV.</span><span class="sxs-lookup"><span data-stu-id="7abbd-173">Sign in to the POS.</span></span>
2. <span data-ttu-id="7abbd-174">Na tela **Inicial**, selecione **Atendimento da ordem**</span><span class="sxs-lookup"><span data-stu-id="7abbd-174">On the **Welcome** screen, select **Order fulfillment**</span></span>
3. <span data-ttu-id="7abbd-175">Na lista de itens para retirada, selecione a linha da ordem que foi lançada online.</span><span class="sxs-lookup"><span data-stu-id="7abbd-175">In the list of items for pickup, select the line from the order that was placed online.</span></span>
4. <span data-ttu-id="7abbd-176">Quando a linha da ordem for selecionada, selecione **Retirar**.</span><span class="sxs-lookup"><span data-stu-id="7abbd-176">While the order line is selected, select **Pick up**.</span></span>

    <span data-ttu-id="7abbd-177">O item da linha é adicionado à tela da transação e **US$ 0,00** é exibido como o saldo devido.</span><span class="sxs-lookup"><span data-stu-id="7abbd-177">The line item is added to the transaction screen, and **$0.00** is shown as the balance that is due.</span></span>

5. <span data-ttu-id="7abbd-178">Selecione o saldo devido de **US$0,00** ou selecione qualquer forma de pagamento para concluir a transação.</span><span class="sxs-lookup"><span data-stu-id="7abbd-178">Select the balance due of **$0.00**, or select any payment method to conclude the transaction.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7abbd-179">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="7abbd-179">Troubleshooting</span></span>

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a><span data-ttu-id="7abbd-180">As ordens online que são recuperadas no PDV têm um saldo devido diferente de zero</span><span class="sxs-lookup"><span data-stu-id="7abbd-180">Online orders that are retrieved in the POS have a non-zero balance due</span></span>

<span data-ttu-id="7abbd-181">Quando uma ordem for recuperada para uma retirada na loja, se o saldo devido não for zero (0), certifique-se de que o PDV Moderno está sendo usado e de que a estação de hardware está ativa.</span><span class="sxs-lookup"><span data-stu-id="7abbd-181">When an order is retrieved for in-store pickup, if the balance due isn't 0 (zero), make sure that Modern POS is being used, and that the hardware station is active.</span></span> <span data-ttu-id="7abbd-182">Se o PDV em Nuvem ou o PDV Moderno para iOS estiver sendo usado, certifique-se de que uma estação de hardware compartilhada está ativa.</span><span class="sxs-lookup"><span data-stu-id="7abbd-182">If Cloud POS or Modern POS for iOS is being used, make sure that a shared hardware station is active.</span></span> <span data-ttu-id="7abbd-183">É necessário ter alguma forma de estação de hardware ativa para recuperar pagamentos que foram feitos online.</span><span class="sxs-lookup"><span data-stu-id="7abbd-183">Some form of active hardware station is required to retrieve payments that were made online.</span></span>

### <a name="general-issues-with-payment-capture"></a><span data-ttu-id="7abbd-184">Problemas gerais com a captura de pagamento</span><span class="sxs-lookup"><span data-stu-id="7abbd-184">General issues with payment capture</span></span>

<span data-ttu-id="7abbd-185">Para todos os problemas gerais, é necessário sempre consultar o PDV Moderno ou os logs de evento da Estação de Hardware dos Serviços de Informações da Internet (IIS) como a primeira etapa.</span><span class="sxs-lookup"><span data-stu-id="7abbd-185">For all general issues, you should always consult the Modern POS or Internet Information Services (IIS) Hardware Station event logs as a first step.</span></span> <span data-ttu-id="7abbd-186">Você pode encontrar esses logs nos seguintes nós no log de eventos do Windows:</span><span class="sxs-lookup"><span data-stu-id="7abbd-186">You can find these logs under the following nodes in the Windows event log:</span></span>

- <span data-ttu-id="7abbd-187">Logs de Aplicativos e Serviços \> Microsoft \> Dynamics \> Commerce-ModernPOS</span><span class="sxs-lookup"><span data-stu-id="7abbd-187">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-ModernPOS</span></span>
- <span data-ttu-id="7abbd-188">Logs de Aplicativos e Serviços \> Microsoft \> Dynamics \> Commerce-Estação de Hardware</span><span class="sxs-lookup"><span data-stu-id="7abbd-188">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-Hardware Station</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7abbd-189">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7abbd-189">Additional resources</span></span>

[<span data-ttu-id="7abbd-190">Visão geral do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7abbd-190">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="7abbd-191">Provisionar um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7abbd-191">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="7abbd-192">Configurar recursos opcionais para um ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7abbd-192">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="7abbd-193">Perguntas frequentes do ambiente de visualização do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7abbd-193">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="7abbd-194">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="7abbd-194">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="7abbd-195">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="7abbd-195">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="7abbd-196">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="7abbd-196">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="7abbd-197">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="7abbd-197">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="7abbd-198">Conector de pagamento Adyen</span><span class="sxs-lookup"><span data-stu-id="7abbd-198">Adyen payment connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[<span data-ttu-id="7abbd-199">Salvando meios de pagamento online com o conector Adyen</span><span class="sxs-lookup"><span data-stu-id="7abbd-199">Saving online payment instruments with the Adyen connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[<span data-ttu-id="7abbd-200">Visão geral de pagamentos de omnicanal</span><span class="sxs-lookup"><span data-stu-id="7abbd-200">Omni-channel payments overview</span></span>](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)
