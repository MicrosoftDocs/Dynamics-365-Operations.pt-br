---
title: Defina configurações de email no Microsoft Dynamics 365 for Talent - Attract
description: Este tópico explica como definir configurações para o email enviado pelo Microsoft Dynamcis 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: a8cf59064dd2f66ee50a0b0566aa712ba1f72dea
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739486"
---
# <a name="configure-email-settings"></a><span data-ttu-id="7c0ab-103">Definir configurações de email</span><span class="sxs-lookup"><span data-stu-id="7c0ab-103">Configure email settings</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7c0ab-104">Sua marca estabelece confiança e ajuda você a construir um relacionamento com candidatos antes de se candidatarem às suas posições.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-104">Your brand establishes trust and helps you build a relationship with candidates before they even apply for your positions.</span></span> <span data-ttu-id="7c0ab-105">A percepção positiva da marca atrai os maiores talentos e aumenta a fidelidade dos funcionários existentes.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-105">Positive brand perception attracts top talent and increases the loyalty of existing employees.</span></span> <span data-ttu-id="7c0ab-106">Microsoft Dynamics 365 for Talent: o Attract permite que você configure emails para que reflitam a marca da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-106">Microsoft Dynamics 365 for Talent: Attract lets you configure emails so that they reflect your company's brand.</span></span> <span data-ttu-id="7c0ab-107">Portanto, você pode fornecer uma experiência consistente a candidatos ao trabalho à medida que avancem no processo de solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-107">Therefore, you can provide a consistent experience to job candidates as they progress through the application process.</span></span>

<span data-ttu-id="7c0ab-108">O Attract permite que você execute estas ações:</span><span class="sxs-lookup"><span data-stu-id="7c0ab-108">Attract lets you perform these actions:</span></span>

- <span data-ttu-id="7c0ab-109">Defina configurações de email para que a conta de serviço de email do Microsoft Exchange da sua empresa seja usada.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-109">Configure email settings so that your company's Microsoft Exchange email service account is used.</span></span> <span data-ttu-id="7c0ab-110">Assim, os candidatos sabem que os emails vêm da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-110">In this way, candidates know that the emails are coming from your company.</span></span> <span data-ttu-id="7c0ab-111">Por exemplo, você pode definir suas configurações para que os candidatos recebam email do `recruiting@contoso.com` em vez do `contoso@microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-111">For example, you can configure your settings so that candidates receive emails from `recruiting@contoso.com` instead of `contoso@microsoft.com`.</span></span>
- <span data-ttu-id="7c0ab-112">Crie marcas consistentes para todas as suas comunicações por email, definindo um cabeçalho e rodapé globais para os modelos de email.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-112">Create consistent branding for all your email communications by setting a global header and footer for email templates.</span></span> 

> [!NOTE]
> <span data-ttu-id="7c0ab-113">Para configurar o Attract de forma que ele utilize a conta de serviço de email da sua empresa para enviar emails, você precisa do complemento de contratação abrangente.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-113">To configure Attract so that it uses your company's email service account to send email, you need the Comprehensive hiring add-on.</span></span>

## <a name="connect-an-email-service-account"></a><span data-ttu-id="7c0ab-114">Conecte uma conta de serviço de email</span><span class="sxs-lookup"><span data-stu-id="7c0ab-114">Connect an email service account</span></span>

<span data-ttu-id="7c0ab-115">Ao conectar a conta de serviço de email da sua empresa, você pode criar uma experiência de email de marca para os candidatos ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-115">By connecting your company's email service account, you can create a branded email experience for your job candidates.</span></span> <span data-ttu-id="7c0ab-116">Se você não conectar a conta da sua empresa, o Attract utilizará a conta de serviço de email padrão com a marca da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-116">If you don't connect your company account, Attract uses the default Microsoft-branded email service account.</span></span>

1. <span data-ttu-id="7c0ab-117">Selecione **Configurações** (o símbolo de engrenagem no canto superior direito) e selecione **Centro de administração**.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-117">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="7c0ab-118">Na guia **Configurações de email**, em **Contas do serviço de email**, selecione **Conectar-se a uma conta de empresa**.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-118">On the **Email settings** tab, under **Email service accounts**, select **Connect a company account**.</span></span>

    ![Como conectar a conta de serviço de email da sua empresa no Attract](./media/attract-admin-email-service-accounts.png)

    <span data-ttu-id="7c0ab-120">Para obter mais informações sobre como criar uma conta de email compartilhada, consulte [Caixas de correio compartilhadas em Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="7c0ab-120">For more information about how to create a shared email account, see [Shared mailboxes in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).</span></span>

3. <span data-ttu-id="7c0ab-121">Na janela de entrada da Microsoft, entre usando suas credenciais corporativas.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-121">In the Microsoft sign-in window, sign in by using your corporate credentials.</span></span>
4. <span data-ttu-id="7c0ab-122">Se você ainda não tiver configurado uma conta de serviço de email ou se desejar adicionar uma nova conta, selecione **Adicionar nova conta de serviço** e insira as informações de seu email.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-122">If you haven't yet set up an email service account, or if you want to add a new one, select **Add new service account**, and then enter your email information.</span></span> <span data-ttu-id="7c0ab-123">Se você já configurou a conta de serviço de email que deseja usar, selecione-a.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-123">If you've already set up the email service account that you want to use, select it.</span></span>

<span data-ttu-id="7c0ab-124">Quando sua conta de serviço de email for configurada com êxito, você a verá listada em **Contas de serviço de email**.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-124">When your email service account is successfully configured, you will see it listed under **Email service accounts**.</span></span>

## <a name="disconnect-an-email-service-account"></a><span data-ttu-id="7c0ab-125">Desconecte uma conta de serviço de email</span><span class="sxs-lookup"><span data-stu-id="7c0ab-125">Disconnect an email service account</span></span>

<span data-ttu-id="7c0ab-126">Se desejar parar de usar o domínio da empresa em comunicações por email por meio do Attract, você poderá desconectar uma conta de serviço de email.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-126">If you want to stop using your company's domain in email communications through Attract, you can disconnect an email service account.</span></span>

1. <span data-ttu-id="7c0ab-127">Selecione **Configurações** (o símbolo de engrenagem no canto superior direito) e selecione **Centro de administração**.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-127">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="7c0ab-128">Na guia **Configurações de email**, em **Contas do serviço de email**, selecione o botão **Mais** (três pontos verticais) ao lado da conta de serviço de email a ser desconectada.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-128">On the **Email settings** tab, under **Email service accounts**, select the **More** button (three vertical dots) next to the email service account that you want to disconnect.</span></span>
3. <span data-ttu-id="7c0ab-129">Selecione **Desconectar a conta de email**.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-129">Select **Disconnect email account**.</span></span>

    ![Como desconectar a conta de serviço de email da sua empresa](./media/attract-admin-disconnect-email-account.png)

4. <span data-ttu-id="7c0ab-131">Quando for solicitado a confirmar a operação, selecione **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-131">When you're prompted to confirm the operation, select **Disconnect**.</span></span>

    ![Confirmando a desconexão da conta de serviço de email da sua empresa](./media/attract-admin-email-confirm-disconnect.png)

<span data-ttu-id="7c0ab-133">Se você não conectar uma conta de serviço de email diferente, os emails enviados do Attract usarão a conta de serviço de email padrão com a marca da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-133">If you don't connect a different email service account, emails that are sent from Attract will use the default Microsoft-branded email service account.</span></span>

## <a name="configure-email-template-settings"></a><span data-ttu-id="7c0ab-134">Defina configurações de modelo de email</span><span class="sxs-lookup"><span data-stu-id="7c0ab-134">Configure email template settings</span></span>

<span data-ttu-id="7c0ab-135">Você pode carregar uma imagem do logotipo da sua empresa e outras informações como um cabeçalho com marca para seus emails.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-135">You can upload an image of your company's logo and other information as a branded header for your emails.</span></span> <span data-ttu-id="7c0ab-136">Você também pode fornecer links para sua política de privacidade e termos de uso em rodapés de email.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-136">You can also provide links to your privacy policy and terms of use in email footers.</span></span>

> [!NOTE]
> <span data-ttu-id="7c0ab-137">Você deve estar em conformidade com todas as leis aplicáveis de seu país ou região e também com o país ou região que rege o destinatário do email.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-137">You must comply with all applicable laws of your country or region, and also the country or region that governs the email recipient.</span></span> <span data-ttu-id="7c0ab-138">Essas leis incluem regulamentações antispam.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-138">These laws include anti-spam regulations.</span></span>

1. <span data-ttu-id="7c0ab-139">Selecione **Configurações** (o símbolo de engrenagem no canto superior direito) e selecione **Centro de administração**.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-139">Select **Settings** (the gear symbol in the upper-right corner), and then select **Admin center**.</span></span>
2. <span data-ttu-id="7c0ab-140">Na guia **Configurações de email**, em **Configurações de modelo de email**, arraste a imagem que você deseja usar como o cabeçalho do email até a caixa de imagem ou clique na caixa de imagem para procurar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-140">On the **Email settings** tab, under **Email template settings**, drag the image that you want to use as your email header into the image box, or click in the image box to browse for the file.</span></span> <span data-ttu-id="7c0ab-141">Para substituir uma imagem existente, primeiro selecione **Remover** ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-141">To replace an existing image, you must first select **Remove** next to it.</span></span> <span data-ttu-id="7c0ab-142">A imagem pode ser um arquivo JPEG JPG, PNG ou SVG.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-142">The image must be a JPEG, JPG, PNG, or SVG file.</span></span> <span data-ttu-id="7c0ab-143">É recomendável que as imagens tenham entre 25 e 800 pixels de largura e entre 25 e 150 pixels de altura.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-143">The recommended size for images is between 25 and 800 pixels wide, and between 25 and 150 pixels high.</span></span> <span data-ttu-id="7c0ab-144">O tamanho máximo do arquivo para o cabeçalho é de 1 megabyte (MB).</span><span class="sxs-lookup"><span data-stu-id="7c0ab-144">The maximum file size for the header is 1 megabyte (MB).</span></span>

    ![Como adicionar uma imagem ao cabeçalho de email da sua empresa](./media/attract-admin-email-header.png)

3. <span data-ttu-id="7c0ab-146">Em **Sua política de privacidade para comunicações**, forneça um link para a política de privacidade da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-146">Under **Your Privacy policy for communications**, provide a link to your company's privacy policy.</span></span> <span data-ttu-id="7c0ab-147">Em **Seus termos e condições para comunicações**, forneça um link para os termos de uso da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-147">Under **Your Terms and conditions for communication**, provide a link to your company's terms of use.</span></span>

    ![Como adicionar links para a política de privacidade e os termos de uso da sua empresa para o rodapé de email](./media/attract-admin-email-footer.png)

4. <span data-ttu-id="7c0ab-149">Selecione **Salvar** para salvar as suas configurações de modelo de email.</span><span class="sxs-lookup"><span data-stu-id="7c0ab-149">Select **Save** to save your email template settings.</span></span>
