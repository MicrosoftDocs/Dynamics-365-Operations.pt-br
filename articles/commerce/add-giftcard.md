---
title: Módulo do vale-presente
description: Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8db7e597241f1fd552f6b960c2b57b0ba83da949
ms.sourcegitcommit: efde05c758b2e02960760d875569d780d77d5550
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2021
ms.locfileid: "5962754"
---
# <a name="gift-card-module"></a><span data-ttu-id="abc2f-103">Módulo de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="abc2f-103">Gift card module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="abc2f-104">Este tópico abrange os módulos de cartão-presente e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="abc2f-104">This topic covers gift card modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="abc2f-105">Os módulos de cartão-presente podem ser usados em módulos de finalização de compra para aceitar cartões-presente, uma forma comum de pagamento usada para transações de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="abc2f-105">Gift card modules can be used in checkout modules to accept gift cards, a common form of payment used for e-Commerce transactions.</span></span> <span data-ttu-id="abc2f-106">O módulo de cartão-presente oferece suporte a cartões-presente Dynamics 365, SVS e Givex.</span><span class="sxs-lookup"><span data-stu-id="abc2f-106">The gift card module supports Dynamics 365, SVS, and Givex gift cards.</span></span> <span data-ttu-id="abc2f-107">Os cartões-presente SVS e Givex são resgatados por meio do provedor de pagamentos Adyen.</span><span class="sxs-lookup"><span data-stu-id="abc2f-107">SVS and Givex gift cards are redeemed via the Adyen payment provider.</span></span> <span data-ttu-id="abc2f-108">Para obter mais informações sobre suporte a cartões-presente externos, como SVS e Givex, consulte [Suporte a cartões-presente externos](./dev-itpro/gift-card.md).</span><span class="sxs-lookup"><span data-stu-id="abc2f-108">For more information about support for external gift cards such as SVS and Givex, see [Support for external gift cards](./dev-itpro/gift-card.md).</span></span>

> [!NOTE]
> <span data-ttu-id="abc2f-109">O suporte para o resgate de vales-presentes SVS e Givex durante o fluxo de finalização de compra está disponível na versão 10.0.11 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="abc2f-109">Support for redeeming SVS and Givex gift cards during checkout flow is available in the Dynamics 365 Commerce 10.0.11 release.</span></span> 

<span data-ttu-id="abc2f-110">Há dois módulos de cartão-presente disponíveis:</span><span class="sxs-lookup"><span data-stu-id="abc2f-110">There are two gift card modules available:</span></span>

- <span data-ttu-id="abc2f-111">**Cartão-presente** - Este módulo pode ser usado em uma página de finalização de compra para resgatar um cartão-presente como meio de pagamento.</span><span class="sxs-lookup"><span data-stu-id="abc2f-111">**Gift card** – This module can be used on a checkout page to redeem a gift card as tender.</span></span> 
- <span data-ttu-id="abc2f-112">**Verificação de saldo do cartão-presente** - Este módulo pode ser usado em qualquer página para verificar o saldo de um cartão-presente.</span><span class="sxs-lookup"><span data-stu-id="abc2f-112">**Gift card balance check** – This module can be used on any page to check the balance on a gift card.</span></span> <span data-ttu-id="abc2f-113">Este módulo está disponível nas versões 10.0.14 e posterior do Commerce.</span><span class="sxs-lookup"><span data-stu-id="abc2f-113">This module is available in Commerce release 10.0.14 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="abc2f-114">O suporte para o módulo de verificação de saldo de vale-presente está disponível na versão do 10.0.14 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="abc2f-114">Support for the gift card balance check module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="abc2f-115">A imagem a seguir mostra um exemplo de um módulo de cartão-presente em uma página de finalização de compra.</span><span class="sxs-lookup"><span data-stu-id="abc2f-115">The following image shows an example of a gift card module on a checkout page.</span></span>

![Exemplo de um módulo de cartão-presente](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a><span data-ttu-id="abc2f-117">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="abc2f-117">Module properties</span></span>

- <span data-ttu-id="abc2f-118">**Mostrar campos adicionais**- Essa propriedade define quais campos devem ser exibidos para cartões-presente além do número do cartão-presente, que é sempre exibido por padrão.</span><span class="sxs-lookup"><span data-stu-id="abc2f-118">**Show additional fields** – This property defines what fields should be displayed for gift cards in addition to the gift card number, which is always displayed by default.</span></span> <span data-ttu-id="abc2f-119">Por exemplo, alguns cartões-presente suportam a exibição de um PIN (número de identificação pessoal) e outros suportam a exibição de um PIN e uma data de validade.</span><span class="sxs-lookup"><span data-stu-id="abc2f-119">For example, some gift cards support displaying a personal identification number (PIN), and others support displaying a PIN and expiration date.</span></span> <span data-ttu-id="abc2f-120">Como alternativa, essa propriedade pode ser definida como "Nenhum", que exibiria somente o número do cartão-presente e nenhum outro campo.</span><span class="sxs-lookup"><span data-stu-id="abc2f-120">Alternatively, this property could be set to "None", which would only display the gift card number and no additional fields.</span></span>

<span data-ttu-id="abc2f-121">Valores com suporte:</span><span class="sxs-lookup"><span data-stu-id="abc2f-121">Supported values:</span></span>
-   <span data-ttu-id="abc2f-122">PIN</span><span class="sxs-lookup"><span data-stu-id="abc2f-122">PIN</span></span>
-   <span data-ttu-id="abc2f-123">Data de validade</span><span class="sxs-lookup"><span data-stu-id="abc2f-123">Expiration date</span></span>
-   <span data-ttu-id="abc2f-124">PIN e data de vencimento</span><span class="sxs-lookup"><span data-stu-id="abc2f-124">PIN and expiration date</span></span> 
-   <span data-ttu-id="abc2f-125">Nemhum(a)</span><span class="sxs-lookup"><span data-stu-id="abc2f-125">None</span></span>

## <a name="site-settings-for-gift-card-modules"></a><span data-ttu-id="abc2f-126">Configurações do site para módulos de cartão-presente</span><span class="sxs-lookup"><span data-stu-id="abc2f-126">Site settings for gift card modules</span></span>

<span data-ttu-id="abc2f-127">No construtor de sites do Commerce em **Configurações de site \> Extensões**, há uma configuração de módulo de cartão-presente chamada **Tipo de cartão-presente compatível**.</span><span class="sxs-lookup"><span data-stu-id="abc2f-127">In Commerce site builder under **Site Settings \> Extensions**, there is a gift card module setting called **Supported gift card type**.</span></span> <span data-ttu-id="abc2f-128">Esta configuração oferece suporte a três valores:</span><span class="sxs-lookup"><span data-stu-id="abc2f-128">This setting supports three values:</span></span>
- <span data-ttu-id="abc2f-129">**Cartão-presente do Dynamics 365** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="abc2f-129">**Dynamics 365 gift card** – When this setting is applied, the gift card module only allows the redemption of Dynamics 365 gift cards.</span></span> <span data-ttu-id="abc2f-130">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="abc2f-130">This setting is only supported for signed-in users on the e-Commerce site.</span></span>
- <span data-ttu-id="abc2f-131">**Cartões-presente SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="abc2f-131">**SVS and Givex gift cards** – When this setting is applied, the gift card module only allows the redemption of Givex and SVS gift cards.</span></span> <span data-ttu-id="abc2f-132">Essa configuração tem suporte para usuários conectados e anônimos no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="abc2f-132">This setting is supported for signed-in and anonymous users on the e-Commerce site.</span></span>
- <span data-ttu-id="abc2f-133">**Cartões-presente Dynamics 365, SVS e Givex** - Quando essa configuração é aplicada, o módulo do cartão-presente só permite o resgate dos cartões-presente Dynamics 365, Givex e SVS.</span><span class="sxs-lookup"><span data-stu-id="abc2f-133">**Dynamics 365, SVS, and Givex gift cards** – When this setting is applied, the gift card module allows the redemption of Dynamics 365, Givex, and SVS gift cards.</span></span> <span data-ttu-id="abc2f-134">Essa configuração só tem suporte para usuários conectados no site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="abc2f-134">This setting is only supported for signed-in users on the e-Commerce site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abc2f-135">Essas configurações estão disponíveis na versão 10.0.11 do Dynamics 365 Commerce e são necessárias somente se você precisar de suporte para vales-presente SVS ou Givex.</span><span class="sxs-lookup"><span data-stu-id="abc2f-135">These settings are available in the Dynamics 365 Commerce 10.0.11 release and are required only if you need support for SVS or Givex gift cards.</span></span> <span data-ttu-id="abc2f-136">Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json.</span><span class="sxs-lookup"><span data-stu-id="abc2f-136">If you are updating from an older version of Dynamics 365 Commerce, you must manually update the appsettings.json file.</span></span> <span data-ttu-id="abc2f-137">Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span><span class="sxs-lookup"><span data-stu-id="abc2f-137">For instructions on updating the appsettings.json file, see [SDK and module library updates](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).</span></span> 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a><span data-ttu-id="abc2f-138">Estender cartões de presente internos para uso em lojas de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="abc2f-138">Extend internal gift cards for use in e-commerce storefronts</span></span>

<span data-ttu-id="abc2f-139">Por padrão, os cartões de presente internos não são otimizados para uso em lojas de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="abc2f-139">By default, internal gift cards aren't optimized for use in e-commerce storefronts.</span></span> <span data-ttu-id="abc2f-140">Portanto, antes de permitir que cartões de presente internos sejam usados para pagamento, você deve configurá-los com extensões que ajudam a torná-los mais seguros.</span><span class="sxs-lookup"><span data-stu-id="abc2f-140">Therefore, before you allow internal gift cards to be used for payment, you should configure them with extensions that help make them more secure.</span></span> <span data-ttu-id="abc2f-141">Aqui estão as áreas de vale-presente que você deve estender antes de permitir que os vales-presentes internos sejam usados na produção:</span><span class="sxs-lookup"><span data-stu-id="abc2f-141">Here are the gift card areas that you should extend before you allow internal gift cards to be used in production:</span></span>

- <span data-ttu-id="abc2f-142">**Número do vale-presente** - as sequências numéricas são usadas para gerar números de vale-presente para vales-presentes internos.</span><span class="sxs-lookup"><span data-stu-id="abc2f-142">**Gift card number** – Number sequences are used to generate gift card numbers for internal gift cards.</span></span> <span data-ttu-id="abc2f-143">Como as sequências numéricas podem ser facilmente previstas, você deve estender a geração de números de vale-presente para que sequências de caracteres de segurança aleatórias e criptografadas sejam usadas para os números de cartão de presente que são emitidos.</span><span class="sxs-lookup"><span data-stu-id="abc2f-143">Because number sequences can easily be predicted, you should extend the generation of gift card numbers so that random, cryptographically secure strings are used for the gift card numbers that are issued.</span></span>
- <span data-ttu-id="abc2f-144">**Getbalance** – a API **GetBalance** é usada na pesquisa de saldos do vale-presente.</span><span class="sxs-lookup"><span data-stu-id="abc2f-144">**GetBalance** – The **GetBalance** API is used to look up gift card balances.</span></span> <span data-ttu-id="abc2f-145">Por padrão, essa API é pública.</span><span class="sxs-lookup"><span data-stu-id="abc2f-145">By default, this API public.</span></span> <span data-ttu-id="abc2f-146">Se um PIN não for necessário para procurar saldos do vale-presente, há um risco que os ataques de força bruta pudessem usar a **API Getbalance** para tentar procurar números de vale-presente que tenham saldos.</span><span class="sxs-lookup"><span data-stu-id="abc2f-146">If a PIN isn't required to look up gift card balances, there is a risk that brute force attacks could use the **GetBalance** API to try to look up gift card numbers that have balances.</span></span> <span data-ttu-id="abc2f-147">Ao implementar os dois requisitos de PIN para vales-presentes internos e limitação de API, você pode ajudar a mitigar o risco.</span><span class="sxs-lookup"><span data-stu-id="abc2f-147">By implementing both PIN requirements for internal gift cards and API throttling, you can help mitigate the risk.</span></span>
- <span data-ttu-id="abc2f-148">**PIN** – por padrão, os vales-presentes internos não dão suporte a PINs.</span><span class="sxs-lookup"><span data-stu-id="abc2f-148">**PIN** – By default, internal gift cards don't support PINs.</span></span> <span data-ttu-id="abc2f-149">Você deve estender os vales-presentes internos para que um PIN seja necessário para pesquisar saldos.</span><span class="sxs-lookup"><span data-stu-id="abc2f-149">You should extend internal gift cards so that a PIN is required to look up balances.</span></span> <span data-ttu-id="abc2f-150">Essa funcionalidade também pode ser usada para bloquear vales-presentes após tentativas incorretas consecutivas de inserir o PIN.</span><span class="sxs-lookup"><span data-stu-id="abc2f-150">This functionality can also be used to lock gift cards after consecutive incorrect attempts to enter the PIN.</span></span>

## <a name="enable-gift-card-payments-for-guest-checkout"></a><span data-ttu-id="abc2f-151">Habilitar pagamentos do vale-presente para o finalização de compra do convidado</span><span class="sxs-lookup"><span data-stu-id="abc2f-151">Enable gift card payments for guest checkout</span></span>

<span data-ttu-id="abc2f-152">Por padrão, os pagamentos de vale-presente são habilitados para finalização de compra de convidado (anônimo).</span><span class="sxs-lookup"><span data-stu-id="abc2f-152">By default, gift card payments aren't enabled for guest (anonymous) checkout.</span></span> <span data-ttu-id="abc2f-153">Para habilitá-los, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="abc2f-153">To enable them, follow these steps.</span></span>

1. <span data-ttu-id="abc2f-154">No Commerce headquarters, vá para **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="abc2f-154">In Commerce headquarters, go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS Operations**.</span></span>
1. <span data-ttu-id="abc2f-155">Selecione e segure (ou clique com o botão direito do mouse) no cabeçalho da grade e, em seguida, selecione **Inserir colunas**.</span><span class="sxs-lookup"><span data-stu-id="abc2f-155">Select and hold (or right-click) the header of the grid, and then select **Insert columns**.</span></span>
1. <span data-ttu-id="abc2f-156">Na caixa de diálogo **Inserir colunas**, marque a caixa de seleção **AllowAnonymousAccess**.</span><span class="sxs-lookup"><span data-stu-id="abc2f-156">In the **Insert columns** dialog box, select the **AllowAnonymousAccess** check box.</span></span>
1. <span data-ttu-id="abc2f-157">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="abc2f-157">Select **Update**.</span></span>
1. <span data-ttu-id="abc2f-158">Para operações **520** (saldo do vale-presente) e **214**, defina o valor de **AllowAnonymousAccess** como **1**.</span><span class="sxs-lookup"><span data-stu-id="abc2f-158">For operations **520** (Gift card balance) and **214**, set the **AllowAnonymousAccess** value to **1**.</span></span>
1. <span data-ttu-id="abc2f-159">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="abc2f-159">Select **Save**.</span></span>
1. <span data-ttu-id="abc2f-160">Execute o trabalho do agendador **1090** para sincronizar alterações para o banco de dados do canal.</span><span class="sxs-lookup"><span data-stu-id="abc2f-160">Run the **1090** scheduler job to sync changes to the channel database.</span></span> 

## <a name="add-a-gift-card-module-to-a-page"></a><span data-ttu-id="abc2f-161">Adicionar um módulo de cartão-presente a uma página</span><span class="sxs-lookup"><span data-stu-id="abc2f-161">Add a gift card module to a page</span></span>

<span data-ttu-id="abc2f-162">Para obter instruções sobre como adicionar um módulo de cartão-presente a uma página de check-in e definir as propriedades necessárias, consulte [Módulo de finalização](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="abc2f-162">For instructions on how to add a gift card module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="abc2f-163">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="abc2f-163">Additional resources</span></span>

[<span data-ttu-id="abc2f-164">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="abc2f-164">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="abc2f-165">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="abc2f-165">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="abc2f-166">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="abc2f-166">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="abc2f-167">Módulo de pagamento</span><span class="sxs-lookup"><span data-stu-id="abc2f-167">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="abc2f-168">Módulo de endereço de remessa</span><span class="sxs-lookup"><span data-stu-id="abc2f-168">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="abc2f-169">Módulo de opções de entrega</span><span class="sxs-lookup"><span data-stu-id="abc2f-169">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="abc2f-170">Módulo de informações sobre retirada</span><span class="sxs-lookup"><span data-stu-id="abc2f-170">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="abc2f-171">Módulo de detalhes da ordem</span><span class="sxs-lookup"><span data-stu-id="abc2f-171">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="abc2f-172">Suporte a cartões-presente externos</span><span class="sxs-lookup"><span data-stu-id="abc2f-172">Support for external gift cards</span></span>](./dev-itpro/gift-card.md)

[<span data-ttu-id="abc2f-173">SDK e atualizações da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="abc2f-173">SDK and module library updates</span></span>](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
