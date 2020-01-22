---
title: Configurar recursos opcionais para um ambiente de visualização comercial
description: Este tópico explica como configurar recursos opcionais para um ambiente de visualização do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 2c4872cdebc414eaa865af025237bd9e1d14bfd2
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906107"
---
# <a name="configure-optional-features-for-a-commerce-preview-environment"></a><span data-ttu-id="55604-103">Configurar recursos opcionais para um ambiente de visualização comercial</span><span class="sxs-lookup"><span data-stu-id="55604-103">Configure optional features for a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="55604-104">Este tópico explica como configurar recursos opcionais para um ambiente de visualização do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="55604-104">This topic explains how to configure optional features for a Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55604-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="55604-105">Prerequisites</span></span>

<span data-ttu-id="55604-106">Se quiser avaliar os recursos transacionais de email, os seguintes pré-requisitos deverão ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="55604-106">If you want to evaluate the transactional email features, the following prerequisites must be met:</span></span>

- <span data-ttu-id="55604-107">Você tem um servidor de email disponível (servidor Simple Mail Transfer Protocol \[SMTP\]) que pode ser usado da assinatura de Microsoft Azure onde você provisionou o ambiente de visualização.</span><span class="sxs-lookup"><span data-stu-id="55604-107">You have an available email server (Simple Mail Transfer Protocol \[SMTP\] server) that can be used from the Microsoft Azure subscription where you provisioned the preview environment.</span></span>
- <span data-ttu-id="55604-108">Você tem o nome de domínio totalmente qualificado (FQDN)/endereço IP do servidor, o número da porta SMTP e os detalhes de autenticação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="55604-108">You have the server's fully qualified domain name (FQDN)/IP address, SMTP port number, and authentication details available.</span></span>

<span data-ttu-id="55604-109">Se você deseja avaliar os recursos de gerenciamento de ativos digitais ao incluir novas imagens do Omni Channel, você deve ter o nome do seu locatário sistema de gerenciamento de conteúdo (CMS) disponível.</span><span class="sxs-lookup"><span data-stu-id="55604-109">If you want to evaluate Digital Asset Management features by ingesting new omni-channel images, you must have the name of your content management system (CMS) tenant available.</span></span> <span data-ttu-id="55604-110">As instruções para encontrar esse nome são fornecidas posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="55604-110">Instructions for finding this name are provided later in this topic.</span></span> <span data-ttu-id="55604-111">>>>(P: onde estão as instruções?)</span><span class="sxs-lookup"><span data-stu-id="55604-111">>>>(Q: where are the instructions?)</span></span>

## <a name="configure-the-image-back-end"></a><span data-ttu-id="55604-112">Configurar o back-end de imagem</span><span class="sxs-lookup"><span data-stu-id="55604-112">Configure the image back end</span></span>

### <a name="find-your-media-base-url"></a><span data-ttu-id="55604-113">Encontrar sua URL base da mídia</span><span class="sxs-lookup"><span data-stu-id="55604-113">Find your media base URL</span></span>

> [!NOTE]
> <span data-ttu-id="55604-114">Antes de concluir este procedimento, você deve concluir as etapas em [Configurar seu site no Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span><span class="sxs-lookup"><span data-stu-id="55604-114">Before you can complete this procedure, you must complete the steps in [Set up your site in Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).</span></span>

1. <span data-ttu-id="55604-115">Efetue login na ferramenta de gerenciamento de site do Commerce usando a URL que você fez uma observação ao inicializar o comércio eletrônico durante o provisionamento (consulte [Inicializar comércio eletrônico](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="55604-115">Sign in to the Commerce site management tool by using the URL you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="55604-116">Abra o site **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="55604-116">Open the **Fabrikam** site.</span></span>
1. <span data-ttu-id="55604-117">No menu à esquerda, selecione **Ativos**.</span><span class="sxs-lookup"><span data-stu-id="55604-117">On the menu on the left, select **Assets**.</span></span>
1. <span data-ttu-id="55604-118">Selecione qualquer ativo único da imagem.</span><span class="sxs-lookup"><span data-stu-id="55604-118">Select any single image asset.</span></span>
1. <span data-ttu-id="55604-119">No Inspetor de propriedades à direita, localize a propriedade de **URL pública**.</span><span class="sxs-lookup"><span data-stu-id="55604-119">In the property inspector on the right, find the **Public URL** property.</span></span> <span data-ttu-id="55604-120">O valor é uma URL.</span><span class="sxs-lookup"><span data-stu-id="55604-120">The value is a URL.</span></span> <span data-ttu-id="55604-121">Este é um exemplo:</span><span class="sxs-lookup"><span data-stu-id="55604-121">Here is an example:</span></span>

    <span data-ttu-id="55604-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span><span class="sxs-lookup"><span data-stu-id="55604-122">`https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.</span></span>

1. <span data-ttu-id="55604-123">Substitua o último identificador no URL (**MA1nQC** no exemplo anterior) pela seguinte string **search?fileName=**.</span><span class="sxs-lookup"><span data-stu-id="55604-123">Replace the last identifier in the URL (**MA1nQC** in the preceding example) with the string **search?fileName=**.</span></span> <span data-ttu-id="55604-124">Esta é a aparência da URL de exemplo após esta alteração ser feita:</span><span class="sxs-lookup"><span data-stu-id="55604-124">Here is what the example URL looks like after this change is made:</span></span>

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    <span data-ttu-id="55604-125">Esta URL é sua URL base da mídia.</span><span class="sxs-lookup"><span data-stu-id="55604-125">This URL is your media base URL.</span></span> <span data-ttu-id="55604-126">Anote-o.</span><span class="sxs-lookup"><span data-stu-id="55604-126">Make a note of it.</span></span>

### <a name="update-the-media-base-url"></a><span data-ttu-id="55604-127">Atualize a URL base da mídia</span><span class="sxs-lookup"><span data-stu-id="55604-127">Update the media base URL</span></span>

1. <span data-ttu-id="55604-128">Entre no Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="55604-128">Sign in to Dynamics 365 Retail.</span></span>
1. <span data-ttu-id="55604-129">Use o menu à esquerda, vá para **Módulos \> Varejo \> Configuração do Canal \> Perfis do canal**.</span><span class="sxs-lookup"><span data-stu-id="55604-129">Use the menu on the left to go to **Modules \> Retail \> Channel setup \> Channel profiles**.</span></span>
1. <span data-ttu-id="55604-130">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55604-130">Select **Edit**.</span></span>
1. <span data-ttu-id="55604-131">Em **Propriedades do perfil**, substitua o valor da propriedade da **URL Base do Servidor de Mídia** com a URL Base de Mídia que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="55604-131">Under **Profile properties**, replace the value for the **Media Server Base URL** property with the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="55604-132">Na lista à esquerda, em canal **Padrão**, selecione outro canal.</span><span class="sxs-lookup"><span data-stu-id="55604-132">In the list on the left, under the **Default** channel, select the other channel.</span></span>
1. <span data-ttu-id="55604-133">Em **Propriedades de perfil**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="55604-133">Under **Profile properties**, select **Add**.</span></span>
1. <span data-ttu-id="55604-134">Para a propriedade adicionada, selecione **URL Base do Servidor de Mídia** como a chave de propriedade.</span><span class="sxs-lookup"><span data-stu-id="55604-134">For the property that was added, select **Media Server Base URL** as the property key.</span></span> <span data-ttu-id="55604-135">Como o valor da propriedade, insira a URL base da mídia criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="55604-135">As the property value, enter the media base URL that you created earlier.</span></span>
1. <span data-ttu-id="55604-136">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55604-136">Select **Save**.</span></span>

## <a name="configure-the-email-server"></a><span data-ttu-id="55604-137">Configurar o servidor de email</span><span class="sxs-lookup"><span data-stu-id="55604-137">Configure the email server</span></span>

> [!NOTE]
> <span data-ttu-id="55604-138">Observe que o servidor SMTP ou o serviço de email digitado aqui deve estar acessível na assinatura do Azure que você está usando para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="55604-138">The SMTP server or email service that you enter here must be accessible from the Azure subscription that you're using for the environment.</span></span>

1. <span data-ttu-id="55604-139">Entrar no Varejo.</span><span class="sxs-lookup"><span data-stu-id="55604-139">Sign in to Retail.</span></span>
1. <span data-ttu-id="55604-140">Use o menu à esquerda para acessar **Módulos \> Administração de sistema \> Configuração \> Email \> Parâmetros de email**.</span><span class="sxs-lookup"><span data-stu-id="55604-140">Use the menu on the left to go to **Modules \> System administration \> Setup \> Email \> Email parameters**.</span></span>
1. <span data-ttu-id="55604-141">Na guia **Configurações de SMTP**, no campo**Servidor de email de saída**, insira o FQDN ou o endereço IP do servidor SMTP ou serviço de email.</span><span class="sxs-lookup"><span data-stu-id="55604-141">On the **SMTP settings** tab, in the **Outgoing mail server** field, enter the FQDN or IP address of your SMTP server or email service.</span></span>
1. <span data-ttu-id="55604-142">No campo **Número da porta SMTP**, insira o número da porta.</span><span class="sxs-lookup"><span data-stu-id="55604-142">In the **SMTP port number** field, enter the port number.</span></span> <span data-ttu-id="55604-143">(Se você não estiver usando Secure Sockets Layer \[SSL\], o número da porta padrão é **25**.)</span><span class="sxs-lookup"><span data-stu-id="55604-143">(If you aren't using Secure Sockets Layer \[SSL\], the default port number is **25**.)</span></span>
1. <span data-ttu-id="55604-144">Se a autenticação for necessária, insira os valores nos campos **Nome de usuário** e **Senha**.</span><span class="sxs-lookup"><span data-stu-id="55604-144">If authentication is required, enter values in the **User name** and **Password** fields.</span></span>
1. <span data-ttu-id="55604-145">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55604-145">Select **Save**.</span></span>
1. <span data-ttu-id="55604-146">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="55604-146">Select **Refresh**.</span></span>
1. <span data-ttu-id="55604-147">Na guia **Email de teste**, no campo **Provedor de email**, selecione **SMTP**.</span><span class="sxs-lookup"><span data-stu-id="55604-147">On the **Test email** tab, in the **Email provider** field, select **SMTP**.</span></span>
1. <span data-ttu-id="55604-148">No campo **Enviar a**, insira o endereço de email para o qual você quer que o email de teste seja enviado.</span><span class="sxs-lookup"><span data-stu-id="55604-148">In the **Send to** field, enter the email address that the test email should be delivered to.</span></span>
1. <span data-ttu-id="55604-149">Selecione **Enviar email de teste**.</span><span class="sxs-lookup"><span data-stu-id="55604-149">Select **Send test email**.</span></span>

## <a name="configure-email-templates"></a><span data-ttu-id="55604-150">Configurar modelos de email</span><span class="sxs-lookup"><span data-stu-id="55604-150">Configure email templates</span></span>

<span data-ttu-id="55604-151">Para cada evento transacional para o qual você deseja enviar emails, você deve atualizar o modelo de email com um endereço de email do remetente válido.</span><span class="sxs-lookup"><span data-stu-id="55604-151">For each transactional event that you want to send emails for, you must update the email template with a valid sender email address.</span></span>

1. <span data-ttu-id="55604-152">Entrar no Varejo.</span><span class="sxs-lookup"><span data-stu-id="55604-152">Sign in to Retail.</span></span>
1. <span data-ttu-id="55604-153">Use o menu à esquerda para acessar **Módulos \> Administração da organização \> Configurar \> Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="55604-153">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="55604-154">Selecione **Mostrar lista**.</span><span class="sxs-lookup"><span data-stu-id="55604-154">Select **Show list**.</span></span>
1. <span data-ttu-id="55604-155">Para cada modelo na lista, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="55604-155">For each template in the list, follow these steps:</span></span>

    1. <span data-ttu-id="55604-156">No campo **Email do remetente**, insira o email do remetente.</span><span class="sxs-lookup"><span data-stu-id="55604-156">In the **Sender email** field, enter the sender email address.</span></span>
    1. <span data-ttu-id="55604-157">Opcional: no campo **Nome do remetente**, insira o nome que deve ser usado como o nome do remetente.</span><span class="sxs-lookup"><span data-stu-id="55604-157">Optional: In the **Sender name** field, enter the name that should be used as the sender name.</span></span>

1. <span data-ttu-id="55604-158">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55604-158">Select **Save**.</span></span>

## <a name="customize-email-templates"></a><span data-ttu-id="55604-159">Personalizar modelos de email</span><span class="sxs-lookup"><span data-stu-id="55604-159">Customize email templates</span></span>

<span data-ttu-id="55604-160">Você pode desejar personalizar os modelos de email para que eles usem imagens diferentes.</span><span class="sxs-lookup"><span data-stu-id="55604-160">You might want to customize the email templates so that they use different images.</span></span> <span data-ttu-id="55604-161">Ou, talvez queira atualizar os links nos modelos para que eles possam ir para o seu ambiente de visualização.</span><span class="sxs-lookup"><span data-stu-id="55604-161">Or you might want to update the links in the templates so that they go to your preview environment.</span></span> <span data-ttu-id="55604-162">Esse procedimento explica como baixar os modelos padrão, personalizá-los e atualizar os modelos no sistema.</span><span class="sxs-lookup"><span data-stu-id="55604-162">This procedure explains how to download the default templates, customize them, and update the templates in the system.</span></span>

1. <span data-ttu-id="55604-163">Em um navegador da Web, baixe o arquivo compactado de modelos de email padrão para visualização da [Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) para seu computador local.</span><span class="sxs-lookup"><span data-stu-id="55604-163">In a web browser, download the [Microsoft Dynamics 365 Commerce Preview default email templates zip file](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) to your local computer.</span></span> <span data-ttu-id="55604-164">Esse arquivo contém os seguintes documentos HTML:</span><span class="sxs-lookup"><span data-stu-id="55604-164">This file contains the following HTML documents:</span></span>

    - <span data-ttu-id="55604-165">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="55604-165">Order confirmation template</span></span>
    - <span data-ttu-id="55604-166">Emitir modelo de vale-presente</span><span class="sxs-lookup"><span data-stu-id="55604-166">Issue gift card template</span></span>
    - <span data-ttu-id="55604-167">Novo modelo de ordem</span><span class="sxs-lookup"><span data-stu-id="55604-167">New order template</span></span>
    - <span data-ttu-id="55604-168">Empacotar modelo de ordem</span><span class="sxs-lookup"><span data-stu-id="55604-168">Pack order template</span></span>
    - <span data-ttu-id="55604-169">Separar modelo de ordem</span><span class="sxs-lookup"><span data-stu-id="55604-169">Pick order template</span></span>

1. <span data-ttu-id="55604-170">Personalizar os modelos usando um texto ou editor HTML.</span><span class="sxs-lookup"><span data-stu-id="55604-170">Customize the templates by using a text or HTML editor.</span></span> <span data-ttu-id="55604-171">Consulte a lista de [tokens compatíveis](#supported-tokens-in-the-email-template) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="55604-171">See the list of [supported tokens](#supported-tokens-in-the-email-template) later in this topic.</span></span>
1. <span data-ttu-id="55604-172">Entrar no Varejo.</span><span class="sxs-lookup"><span data-stu-id="55604-172">Sign in to Retail.</span></span>
1. <span data-ttu-id="55604-173">Use o menu à esquerda para acessar **Módulos \> Administração da organização \> Configurar \> Modelos de email da organização**.</span><span class="sxs-lookup"><span data-stu-id="55604-173">Use the menu on the left to go to **Modules \> Organization administration \> Setup \> Organization email templates**.</span></span>
1. <span data-ttu-id="55604-174">Expanda a lista à esquerda para consultar todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="55604-174">Expand the list on the left to see all the templates.</span></span>
1. <span data-ttu-id="55604-175">Para cada modelo que você deseja personalizar, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="55604-175">For each template that you want to customize, follow these steps:</span></span>

    1. <span data-ttu-id="55604-176">Selecione o modelo na lista.</span><span class="sxs-lookup"><span data-stu-id="55604-176">Select the template in the list.</span></span>
    1. <span data-ttu-id="55604-177">Em **Conteúdo da mensagem de email**, selecione a versão do idioma apropriado na lista.</span><span class="sxs-lookup"><span data-stu-id="55604-177">Under **Email message content**, select the appropriate language version in the list.</span></span> <span data-ttu-id="55604-178">(O idioma padrão é **en-us**.)</span><span class="sxs-lookup"><span data-stu-id="55604-178">(The default language is **en-us**.)</span></span>
    1. <span data-ttu-id="55604-179">Em **Conteúdo da mensagem de email**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="55604-179">Under **Email message content**, select **Edit**.</span></span> <span data-ttu-id="55604-180">O painel **Carregar modelo de email** é exibido.</span><span class="sxs-lookup"><span data-stu-id="55604-180">The **Upload email template** pane appears.</span></span>
    1. <span data-ttu-id="55604-181">Selecione **Procurar**e localize o arquivo HTML que tem o conteúdo personalizado.</span><span class="sxs-lookup"><span data-stu-id="55604-181">Select **Browse**, and find the HTML file that has the customized content.</span></span>
    1. <span data-ttu-id="55604-182">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="55604-182">Select **Upload**.</span></span> <span data-ttu-id="55604-183">O modelo será carregado no sistema e a visualização será mostrada.</span><span class="sxs-lookup"><span data-stu-id="55604-183">The template is uploaded into the system, and a preview is shown.</span></span>
    1. <span data-ttu-id="55604-184">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="55604-184">Select **OK**.</span></span>
    1. <span data-ttu-id="55604-185">Opcional: personalize a propriedade **Assunto** do modelo.</span><span class="sxs-lookup"><span data-stu-id="55604-185">Optional: Customize the **Subject** property of the template.</span></span>
    1. <span data-ttu-id="55604-186">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55604-186">Select **Save**.</span></span>

### <a name="supported-tokens-in-the-email-template"></a><span data-ttu-id="55604-187">Tokens suportados no modelo de email</span><span class="sxs-lookup"><span data-stu-id="55604-187">Supported tokens in the email template</span></span>

<span data-ttu-id="55604-188">Quando o email é processado, esses tokens são substituídos com valores reais que se aplicam ao cliente e ao pedido do cliente.</span><span class="sxs-lookup"><span data-stu-id="55604-188">When the email is rendered, these tokens are replaced with actual values that apply to the customer and the customer's order.</span></span>

#### <a name="sales-order"></a><span data-ttu-id="55604-189">Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="55604-189">Sales order</span></span>

<span data-ttu-id="55604-190">Os seguintes tokens se aplicam à ordem de venda geral.</span><span class="sxs-lookup"><span data-stu-id="55604-190">The following tokens apply to the overall sales order.</span></span>

| <span data-ttu-id="55604-191">Nome do token</span><span class="sxs-lookup"><span data-stu-id="55604-191">Name of the token</span></span> | <span data-ttu-id="55604-192">Token </span><span class="sxs-lookup"><span data-stu-id="55604-192">Token</span></span> |
|-------------------|-------|
| <span data-ttu-id="55604-193">Número da ordem</span><span class="sxs-lookup"><span data-stu-id="55604-193">Order number</span></span>      | <span data-ttu-id="55604-194">%salesid%</span><span class="sxs-lookup"><span data-stu-id="55604-194">%salesid%</span></span> |
| <span data-ttu-id="55604-195">Nome do cliente</span><span class="sxs-lookup"><span data-stu-id="55604-195">Customer's name</span></span>   | <span data-ttu-id="55604-196">%customername%</span><span class="sxs-lookup"><span data-stu-id="55604-196">%customername%</span></span> |
| <span data-ttu-id="55604-197">Endereço de entrega</span><span class="sxs-lookup"><span data-stu-id="55604-197">Delivery address</span></span>  | <span data-ttu-id="55604-198">%deliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="55604-198">%deliveryaddress%</span></span> |
| <span data-ttu-id="55604-199">Endereço para cobrança</span><span class="sxs-lookup"><span data-stu-id="55604-199">Billing address</span></span>   | <span data-ttu-id="55604-200">%customeraddress%</span><span class="sxs-lookup"><span data-stu-id="55604-200">%customeraddress%</span></span> |
| <span data-ttu-id="55604-201">Data da ordem</span><span class="sxs-lookup"><span data-stu-id="55604-201">Order date</span></span>        | <span data-ttu-id="55604-202">%shipdate%</span><span class="sxs-lookup"><span data-stu-id="55604-202">%shipdate%</span></span> |
| <span data-ttu-id="55604-203">Modo de entrega</span><span class="sxs-lookup"><span data-stu-id="55604-203">Delivery mode</span></span>     | <span data-ttu-id="55604-204">%modeofdelivery%</span><span class="sxs-lookup"><span data-stu-id="55604-204">%modeofdelivery%</span></span> |
| <span data-ttu-id="55604-205">Desconto</span><span class="sxs-lookup"><span data-stu-id="55604-205">Discount</span></span>          | <span data-ttu-id="55604-206">%discount%</span><span class="sxs-lookup"><span data-stu-id="55604-206">%discount%</span></span> |
| <span data-ttu-id="55604-207">Imposto</span><span class="sxs-lookup"><span data-stu-id="55604-207">Sales tax</span></span>         | <span data-ttu-id="55604-208">%tax%</span><span class="sxs-lookup"><span data-stu-id="55604-208">%tax%</span></span> |
| <span data-ttu-id="55604-209">Total da ordem</span><span class="sxs-lookup"><span data-stu-id="55604-209">Order total</span></span>       | <span data-ttu-id="55604-210">%total%</span><span class="sxs-lookup"><span data-stu-id="55604-210">%total%</span></span> |

#### <a name="sales-line"></a><span data-ttu-id="55604-211">Linha de venda</span><span class="sxs-lookup"><span data-stu-id="55604-211">Sales line</span></span>

<span data-ttu-id="55604-212">Os seguintes tokens são substituídos com valores para cada produto no pedido.</span><span class="sxs-lookup"><span data-stu-id="55604-212">The following tokens are replaced with values for each product in the order.</span></span>

> [!NOTE]
> <span data-ttu-id="55604-213">Coloque o token **Lista de produtos - iniciar** no início do bloqueio de HTML que é repetido para cada produto, e insere o token **Lista de produto - fim** no final do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="55604-213">Put the **Product list - start** token at the beginning of the HTML block that is repeated for every product, and put the **Product list - end** token at the end of the block.</span></span>

| <span data-ttu-id="55604-214">Nome do token</span><span class="sxs-lookup"><span data-stu-id="55604-214">Name of the token</span></span>      | <span data-ttu-id="55604-215">Token </span><span class="sxs-lookup"><span data-stu-id="55604-215">Token</span></span> |
|------------------------|-------|
| <span data-ttu-id="55604-216">Lista de produtos - início</span><span class="sxs-lookup"><span data-stu-id="55604-216">Product list - start</span></span>   | <span data-ttu-id="55604-217">\<!--%tablebegin.salesline% --\></span><span class="sxs-lookup"><span data-stu-id="55604-217">\<!--%tablebegin.salesline% --\></span></span> |
| <span data-ttu-id="55604-218">Lista de produtos - fim</span><span class="sxs-lookup"><span data-stu-id="55604-218">Product list - end</span></span>     | <span data-ttu-id="55604-219">\<!--%tableend.salesline%--\></span><span class="sxs-lookup"><span data-stu-id="55604-219">\<!--%tableend.salesline%--\></span></span> |
| <span data-ttu-id="55604-220">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="55604-220">Product name</span></span>           | <span data-ttu-id="55604-221">%lineproductname%</span><span class="sxs-lookup"><span data-stu-id="55604-221">%lineproductname%</span></span> |
| <span data-ttu-id="55604-222">Descrição</span><span class="sxs-lookup"><span data-stu-id="55604-222">Description</span></span>            | <span data-ttu-id="55604-223">%lineproductdescription%</span><span class="sxs-lookup"><span data-stu-id="55604-223">%lineproductdescription%</span></span> |
| <span data-ttu-id="55604-224">Quantidade</span><span class="sxs-lookup"><span data-stu-id="55604-224">Quantity</span></span>               | <span data-ttu-id="55604-225">%linequantity%</span><span class="sxs-lookup"><span data-stu-id="55604-225">%linequantity%</span></span> |
| <span data-ttu-id="55604-226">Preço unitário da linha</span><span class="sxs-lookup"><span data-stu-id="55604-226">Line unit price</span></span>        | <span data-ttu-id="55604-227">%lineprice% (verificação)</span><span class="sxs-lookup"><span data-stu-id="55604-227">%lineprice% (verify)</span></span> |
| <span data-ttu-id="55604-228">total do item de linha</span><span class="sxs-lookup"><span data-stu-id="55604-228">line item total</span></span>        | <span data-ttu-id="55604-229">%linenetamount%</span><span class="sxs-lookup"><span data-stu-id="55604-229">%linenetamount%</span></span> |
| <span data-ttu-id="55604-230">desconto de linha</span><span class="sxs-lookup"><span data-stu-id="55604-230">line discount</span></span>          | <span data-ttu-id="55604-231">%linediscount%</span><span class="sxs-lookup"><span data-stu-id="55604-231">%linediscount%</span></span> |
| <span data-ttu-id="55604-232">Data da remessa</span><span class="sxs-lookup"><span data-stu-id="55604-232">Ship date</span></span>              | <span data-ttu-id="55604-233">%lineshipdate%</span><span class="sxs-lookup"><span data-stu-id="55604-233">%lineshipdate%</span></span> |
| <span data-ttu-id="55604-234">Método de aquisição</span><span class="sxs-lookup"><span data-stu-id="55604-234">Procurement method</span></span>     | <span data-ttu-id="55604-235">%linedeliverymode%</span><span class="sxs-lookup"><span data-stu-id="55604-235">%linedeliverymode%</span></span> |
| <span data-ttu-id="55604-236">endereço de entrega</span><span class="sxs-lookup"><span data-stu-id="55604-236">delivery address</span></span>       | <span data-ttu-id="55604-237">%linedeliveryaddress%</span><span class="sxs-lookup"><span data-stu-id="55604-237">%linedeliveryaddress%</span></span> |
| <span data-ttu-id="55604-238">Unidade de venda da linha</span><span class="sxs-lookup"><span data-stu-id="55604-238">Sales unit of the line</span></span> | <span data-ttu-id="55604-239">%lineunit%</span><span class="sxs-lookup"><span data-stu-id="55604-239">%lineunit%</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="55604-240">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="55604-240">Additional resources</span></span>

[<span data-ttu-id="55604-241">Visão geral do ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="55604-241">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="55604-242">Provisionar um ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="55604-242">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="55604-243">Configurar um ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="55604-243">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="55604-244">Perguntas frequentes do ambiente de visualização do Commerce</span><span class="sxs-lookup"><span data-stu-id="55604-244">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="55604-245">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="55604-245">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="55604-246">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="55604-246">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="55604-247">Portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="55604-247">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="55604-248">Site do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="55604-248">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="55604-249">Recursos de ajuda do Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="55604-249">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
