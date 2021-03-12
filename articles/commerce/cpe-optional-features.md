---
title: Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico explica como configurar recursos opcionais para um ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6639de250557ce9a25fc2cde3807abf64b0ddc18
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993441"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="803fe-103">Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="803fe-103">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="803fe-104">Este tópico explica como configurar recursos opcionais para um ambiente de avaliação do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="803fe-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="803fe-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="803fe-105">Prerequisites</span></span>

<span data-ttu-id="803fe-106">Se quiser avaliar os recursos transacionais de email, os seguintes pré-requisitos deverão ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="803fe-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="803fe-107">Há um servidor de email disponível (servidor Simple Mail Transfer Protocol \[SMTP\]) que pode ser usado da assinatura do Microsoft Azure onde você provisionou o ambiente de avaliação.</span><span class="sxs-lookup"><span data-stu-id="803fe-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the evaluation environment.</span></span>
- <span data-ttu-id="803fe-108">Você tem o nome de domínio totalmente qualificado (FQDN)/endereço IP do servidor, o número da porta SMTP e os detalhes de autenticação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="803fe-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="803fe-109">Configurar o back-end de imagem</span><span class="sxs-lookup"><span data-stu-id="803fe-109">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="803fe-110">Encontrar sua URL base da mídia</span><span class="sxs-lookup"><span data-stu-id="803fe-110">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="803fe-111">Antes de concluir este procedimento, você deve concluir as etapas em [Configurar seu site no Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="803fe-111">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="803fe-112">Entre no construtor de sites do Commerce usando a URL que você anotou ao inicializar o e-Commerce durante o provisionamento (consulte [Inicializar o e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="803fe-112">Sign in to the Commerce site builder by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="803fe-113">Abra o site **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="803fe-113">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="803fe-114">No menu à esquerda, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="803fe-114">On the menu on the left, select **Media Library**.</span></span>
1. <span data-ttu-id="803fe-115">Selecione qualquer ativo único da imagem.</span><span class="sxs-lookup"><span data-stu-id="803fe-115">Select any single image asset.</span></span>
1. <span data-ttu-id="803fe-116">No Inspetor de propriedades à direita, localize a propriedade de **URL pública**.</span><span class="sxs-lookup"><span data-stu-id="803fe-116">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="803fe-117">O valor é uma URL.</span><span class="sxs-lookup"><span data-stu-id="803fe-117">The value is a URL.</span></span> <span data-ttu-id="803fe-118">Este é um exemplo:</span><span class="sxs-lookup"><span data-stu-id="803fe-118">Here is an example:</span></span>

    <span data-ttu-id="803fe-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="803fe-119">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="803fe-120">Substitua o último identificador no URL (**MA1nQC** no exemplo anterior) pela seguinte string **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="803fe-120">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="803fe-121">Esta é a aparência da URL de exemplo após esta alteração ser feita:</span><span class="sxs-lookup"><span data-stu-id="803fe-121">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="803fe-122">Esta URL é sua URL base da mídia.</span><span class="sxs-lookup"><span data-stu-id="803fe-122">This URL is your media base URL.</span></span> <span data-ttu-id="803fe-123">Anote-o.</span><span class="sxs-lookup"><span data-stu-id="803fe-123">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="803fe-124">Atualize a URL base da mídia</span><span class="sxs-lookup"><span data-stu-id="803fe-124">Update the media base URL</span></span>

1. <span data-ttu-id="803fe-125">Entre na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="803fe-125">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="803fe-126">Use o menu à esquerda, vá para **Módulos \> Varejo e comércio \> Configuração do Canal \> Perfis do canal**.</span><span class="sxs-lookup"><span data-stu-id="803fe-126">Use the menu on the left to go to **Modules \> Retail and commerce \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="803fe-127">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-127">Select **Edit**.</span></span>
1. <span data-ttu-id="803fe-128">Em **Propriedades do perfil**, substitua o valor da propriedade da **URL Base do Servidor de Mídia** com a URL Base de Mídia que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="803fe-128">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="803fe-129">Selecione o canal chamado **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="803fe-129">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="803fe-130">Em **Propriedades de perfil**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-130">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="803fe-131">Para a propriedade adicionada, selecione **URL Base do Servidor de Mídia** como a chave de propriedade.</span><span class="sxs-lookup"><span data-stu-id="803fe-131">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="803fe-132">Como o valor da propriedade, insira a URL base da mídia criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="803fe-132">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="803fe-133">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-133">Select **Save**.</span></span>

## <a name="configure-and-test-the-email-server"></a><span data-ttu-id="803fe-134">Configurar e testar o servidor de email</span><span class="sxs-lookup"><span data-stu-id="803fe-134">Configure and test the email server</span></span>

> [!NOTE]
> <span data-ttu-id="803fe-135">Observe que o servidor SMTP ou o serviço de email digitado aqui deve estar acessível na assinatura do Azure que você está usando para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="803fe-135">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="803fe-136">Entre na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="803fe-136">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="803fe-137">Use o menu à esquerda para acessar **Módulos \> Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros de email**.</span><span class="sxs-lookup"><span data-stu-id="803fe-137">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Email parameters**.</span></span>
1. <span data-ttu-id="803fe-138">Na guia **Configurações de SMTP**, no campo **Servidor de email de saída**, insira o FQDN ou o endereço IP do servidor SMTP ou serviço de email.</span><span class="sxs-lookup"><span data-stu-id="803fe-138">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="803fe-139">No campo **Número da porta SMTP**, insira o número da porta.</span><span class="sxs-lookup"><span data-stu-id="803fe-139">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="803fe-140">(Se você não estiver usando Secure Sockets Layer \[SSL\], o número da porta padrão é **25**.)</span><span class="sxs-lookup"><span data-stu-id="803fe-140">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="803fe-141">Se a autenticação for necessária, insira os valores nos campos **Nome de usuário** e **Senha**.</span><span class="sxs-lookup"><span data-stu-id="803fe-141">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="803fe-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-142">Select **Save**.</span></span>
1. <span data-ttu-id="803fe-143">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-143">Select **Refresh**.</span></span>
1. <span data-ttu-id="803fe-144">Na guia **Email de teste**, no campo **Provedor de email**, selecione **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="803fe-144">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="803fe-145">No campo **Enviar a**, insira o endereço de email para o qual você quer que o email de teste seja enviado.</span><span class="sxs-lookup"><span data-stu-id="803fe-145">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="803fe-146">Selecione **Enviar email de teste**.</span><span class="sxs-lookup"><span data-stu-id="803fe-146">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="803fe-147">Configurar modelos de email</span><span class="sxs-lookup"><span data-stu-id="803fe-147">Configure email templates</span></span>

<span data-ttu-id="803fe-148">Para cada evento transacional para o qual você deseja enviar emails, você deve atualizar o modelo de email com um endereço de email do remetente válido.</span><span class="sxs-lookup"><span data-stu-id="803fe-148">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="803fe-149">Entre na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="803fe-149">Sign in to Commerce headquarters.</span></span>
1. <span data-ttu-id="803fe-150">Use o menu à esquerda para acessar **Módulos \> Retail e Commerce \> Configuração da sede \> Parâmetros \> Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="803fe-150">Use the menu on the left to go to **Modules \> Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="803fe-151">Selecione **Mostrar lista**.</span><span class="sxs-lookup"><span data-stu-id="803fe-151">Select **Show list**.</span></span>
1. <span data-ttu-id="803fe-152">Para cada modelo na lista, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="803fe-152">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="803fe-153">No campo **Email do remetente**, insira o email do remetente.</span><span class="sxs-lookup"><span data-stu-id="803fe-153">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="803fe-154">Opcional: no campo **Nome do remetente**, insira o nome que deve ser usado como o nome do remetente.</span><span class="sxs-lookup"><span data-stu-id="803fe-154">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="803fe-155">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-155">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="803fe-156">Personalizar modelos de email</span><span class="sxs-lookup"><span data-stu-id="803fe-156">Customize email templates</span></span>

<span data-ttu-id="803fe-157">Você pode desejar personalizar os modelos de email para que eles usem imagens diferentes.</span><span class="sxs-lookup"><span data-stu-id="803fe-157">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="803fe-158">Ou, talvez queira atualizar os links nos modelos para que eles levem você ao seu ambiente de avaliação.</span><span class="sxs-lookup"><span data-stu-id="803fe-158">Or you might want to update the links in the templates so that they go to your evaluation environment.</span></span> <span data-ttu-id="803fe-159">Esse procedimento explica como baixar os modelos padrão, personalizá-los e atualizar os modelos no sistema.</span><span class="sxs-lookup"><span data-stu-id="803fe-159">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="803fe-160">Em um navegador da Web, baixe o [arquivo zip de modelos de email padrão para Avaliação do Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="803fe-160">In a web browser, download the [Microsoft Dynamics 365 Commerce Evaluation default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="803fe-161">Esse arquivo contém os seguintes documentos HTML:</span><span class="sxs-lookup"><span data-stu-id="803fe-161">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="803fe-162">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="803fe-162">Order confirmation template</span></span>
    - <span data-ttu-id="803fe-163">Emitir modelo de vale-presente</span><span class="sxs-lookup"><span data-stu-id="803fe-163">Issue gift card template</span></span>
    - <span data-ttu-id="803fe-164">Novo modelo de ordem</span><span class="sxs-lookup"><span data-stu-id="803fe-164">New order template</span></span>
    - <span data-ttu-id="803fe-165">Empacotar modelo de ordem</span><span class="sxs-lookup"><span data-stu-id="803fe-165">Pack order template</span></span>
    - <span data-ttu-id="803fe-166">Separar modelo de ordem</span><span class="sxs-lookup"><span data-stu-id="803fe-166">Pick order template</span></span>

1. <span data-ttu-id="803fe-167">Personalizar os modelos usando um texto ou editor HTML.</span><span class="sxs-lookup"><span data-stu-id="803fe-167">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="803fe-168">Consulte a lista de [tokens compatíveis](#supported-tokens-in-the-email-template) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="803fe-168">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="803fe-169">Entre no Commerce.</span><span class="sxs-lookup"><span data-stu-id="803fe-169">Sign in to Commerce.</span></span>
1. <span data-ttu-id="803fe-170">Use o menu à esquerda para acessar **Módulos \> Administração da organização \> Configurar \> Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="803fe-170">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="803fe-171">Expanda a lista à esquerda para consultar todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="803fe-171">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="803fe-172">Para cada modelo que você deseja personalizar, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="803fe-172">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="803fe-173">Selecione o modelo na lista.</span><span class="sxs-lookup"><span data-stu-id="803fe-173">Select the template in the list.</span></span>
    1. <span data-ttu-id="803fe-174">Em **Conteúdo da mensagem de email**, selecione a versão do idioma apropriado na lista.</span><span class="sxs-lookup"><span data-stu-id="803fe-174">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="803fe-175">(O idioma padrão é **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="803fe-175">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="803fe-176">Em **Conteúdo da mensagem de email**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-176">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="803fe-177">O painel **Carregar modelo de email** é exibido.</span><span class="sxs-lookup"><span data-stu-id="803fe-177">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="803fe-178">Selecione **Procurar** e localize o arquivo HTML que tem o conteúdo personalizado.</span><span class="sxs-lookup"><span data-stu-id="803fe-178">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="803fe-179">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-179">Select **Upload**.</span></span> <span data-ttu-id="803fe-180">O modelo será carregado no sistema e a visualização será mostrada.</span><span class="sxs-lookup"><span data-stu-id="803fe-180">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="803fe-181">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="803fe-181">Select **OK**.</span></span>
    1. <span data-ttu-id="803fe-182">Opcional: personalize a propriedade **Assunto** do modelo.</span><span class="sxs-lookup"><span data-stu-id="803fe-182">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="803fe-183">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="803fe-183">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="803fe-184">Tokens suportados no modelo de email</span><span class="sxs-lookup"><span data-stu-id="803fe-184">Supported tokens in the email template</span></span>

<span data-ttu-id="803fe-185">Quando o email é processado, esses tokens são substituídos com valores reais que se aplicam ao cliente e ao pedido do cliente.</span><span class="sxs-lookup"><span data-stu-id="803fe-185">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="803fe-186">Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="803fe-186">Sales order</span></span>

<span data-ttu-id="803fe-187">Os seguintes tokens se aplicam à ordem de venda geral.</span><span class="sxs-lookup"><span data-stu-id="803fe-187">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="803fe-188">Nome do token</span><span class="sxs-lookup"><span data-stu-id="803fe-188">Name of the token</span></span> | <span data-ttu-id="803fe-189">Token </span><span class="sxs-lookup"><span data-stu-id="803fe-189">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="803fe-190">Número da ordem</span><span class="sxs-lookup"><span data-stu-id="803fe-190">Order number</span></span>      | <span data-ttu-id="803fe-191">%salesid%</span><span class="sxs-lookup"><span data-stu-id="803fe-191">%salesid%</span></span> |
| <span data-ttu-id="803fe-192">Nome do cliente</span><span class="sxs-lookup"><span data-stu-id="803fe-192">Customer's name</span></span>   | <span data-ttu-id="803fe-193">%customername%</span><span class="sxs-lookup"><span data-stu-id="803fe-193">%customername%</span></span> |
| <span data-ttu-id="803fe-194">Endereço de entrega</span><span class="sxs-lookup"><span data-stu-id="803fe-194">Delivery address</span></span>  | <span data-ttu-id="803fe-195">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="803fe-195">%deliveryaddress%</span></span> |
| <span data-ttu-id="803fe-196">Endereço para cobrança</span><span class="sxs-lookup"><span data-stu-id="803fe-196">Billing address</span></span>   | <span data-ttu-id="803fe-197">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="803fe-197">%customeraddress%</span></span> |
| <span data-ttu-id="803fe-198">Data da ordem</span><span class="sxs-lookup"><span data-stu-id="803fe-198">Order date</span></span>        | <span data-ttu-id="803fe-199">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="803fe-199">%shipdate%</span></span> |
| <span data-ttu-id="803fe-200">Modo de entrega</span><span class="sxs-lookup"><span data-stu-id="803fe-200">Delivery mode</span></span>     | <span data-ttu-id="803fe-201">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="803fe-201">%modeofdelivery%</span></span> |
| <span data-ttu-id="803fe-202">Desconto</span><span class="sxs-lookup"><span data-stu-id="803fe-202">Discount</span></span>          | <span data-ttu-id="803fe-203">%discount%</span><span class="sxs-lookup"><span data-stu-id="803fe-203">%discount%</span></span> |
| <span data-ttu-id="803fe-204">Imposto</span><span class="sxs-lookup"><span data-stu-id="803fe-204">Sales tax</span></span>         | <span data-ttu-id="803fe-205">%tax%</span><span class="sxs-lookup"><span data-stu-id="803fe-205">%tax%</span></span> |
| <span data-ttu-id="803fe-206">Total da ordem</span><span class="sxs-lookup"><span data-stu-id="803fe-206">Order total</span></span>       | <span data-ttu-id="803fe-207">%total%</span><span class="sxs-lookup"><span data-stu-id="803fe-207">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="803fe-208">Linha de venda</span><span class="sxs-lookup"><span data-stu-id="803fe-208">Sales line</span></span>

<span data-ttu-id="803fe-209">Os seguintes tokens são substituídos com valores para cada produto no pedido.</span><span class="sxs-lookup"><span data-stu-id="803fe-209">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="803fe-210">Coloque o token **Lista de produtos - iniciar** no início do bloqueio de HTML que é repetido para cada produto, e insere o token **Lista de produto - fim** no final do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="803fe-210">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="803fe-211">Nome do token</span><span class="sxs-lookup"><span data-stu-id="803fe-211">Name of the token</span></span>      | <span data-ttu-id="803fe-212">Token</span><span class="sxs-lookup"><span data-stu-id="803fe-212">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="803fe-213">Lista de produtos - início</span><span class="sxs-lookup"><span data-stu-id="803fe-213">Product list - start</span></span>   | \<!--%tablebegin.salesline% --\> |
| <span data-ttu-id="803fe-214">Lista de produtos - fim</span><span class="sxs-lookup"><span data-stu-id="803fe-214">Product list - end</span></span>     | \<!--%tableend.salesline%--\> |
| <span data-ttu-id="803fe-215">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="803fe-215">Product name</span></span>           | <span data-ttu-id="803fe-216">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="803fe-216">%lineproductname%</span></span> |
| <span data-ttu-id="803fe-217">descrição</span><span class="sxs-lookup"><span data-stu-id="803fe-217">Description</span></span>            | <span data-ttu-id="803fe-218">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="803fe-218">%lineproductdescription%</span></span> |
| <span data-ttu-id="803fe-219">Quantidade</span><span class="sxs-lookup"><span data-stu-id="803fe-219">Quantity</span></span>               | <span data-ttu-id="803fe-220">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="803fe-220">%linequantity%</span></span> |
| <span data-ttu-id="803fe-221">Preço unitário da linha</span><span class="sxs-lookup"><span data-stu-id="803fe-221">Line unit price</span></span>        | <span data-ttu-id="803fe-222">%lineprice% (verificação)</span><span class="sxs-lookup"><span data-stu-id="803fe-222">%lineprice% (verify)</span></span> |
| <span data-ttu-id="803fe-223">total do item de linha</span><span class="sxs-lookup"><span data-stu-id="803fe-223">line item total</span></span>        | <span data-ttu-id="803fe-224">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="803fe-224">%linenetamount%</span></span> |
| <span data-ttu-id="803fe-225">desconto de linha</span><span class="sxs-lookup"><span data-stu-id="803fe-225">line discount</span></span>          | <span data-ttu-id="803fe-226">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="803fe-226">%linediscount%</span></span> |
| <span data-ttu-id="803fe-227">Data da remessa</span><span class="sxs-lookup"><span data-stu-id="803fe-227">Ship date</span></span>              | <span data-ttu-id="803fe-228">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="803fe-228">%lineshipdate%</span></span> |
| <span data-ttu-id="803fe-229">Método de aquisição</span><span class="sxs-lookup"><span data-stu-id="803fe-229">Procurement method</span></span>     | <span data-ttu-id="803fe-230">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="803fe-230">%linedeliverymode%</span></span> |
| <span data-ttu-id="803fe-231">endereço de entrega</span><span class="sxs-lookup"><span data-stu-id="803fe-231">delivery address</span></span>       | <span data-ttu-id="803fe-232">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="803fe-232">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="803fe-233">Unidade de venda da linha</span><span class="sxs-lookup"><span data-stu-id="803fe-233">Sales unit of the line</span></span> | <span data-ttu-id="803fe-234">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="803fe-234">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="803fe-235">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="803fe-235">Additional resources</span></span>

[<span data-ttu-id="803fe-236">Visão geral do ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="803fe-236">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="803fe-237">Provisionar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="803fe-237">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="803fe-238">Configurar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="803fe-238">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="803fe-239">Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="803fe-239">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="803fe-240">Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="803fe-240">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="803fe-241">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="803fe-241">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="803fe-242">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="803fe-242">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="803fe-243">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="803fe-243">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="803fe-244">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="803fe-244">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
