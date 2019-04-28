---
title: Postar trabalhos em sites de carreira externos a partir do Attract
description: Este tópico explica como usar o Dynamics 365 for Talent - Attract para postar trabalhos em sites de recrutamento externos.
author: pganapmsft
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-03-19
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: eca599ad189edae29ef2de496196b08799a5e745
ms.sourcegitcommit: 1653d1e28d02f8a9a4bea8df562ac98d7a350ed1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2019
ms.locfileid: "993659"
---
# <a name="post-jobs-to-external-career-sites-from-attract"></a><span data-ttu-id="b015c-103">Postar trabalhos em sites de carreira externos a partir do Attract</span><span class="sxs-lookup"><span data-stu-id="b015c-103">Post jobs to external career sites from Attract</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b015c-104">Você quer divulgar posições em aberto para o maior número possível de candidatos qualificados.</span><span class="sxs-lookup"><span data-stu-id="b015c-104">You want to get your open positions in front of as many qualified candidates as possible.</span></span> <span data-ttu-id="b015c-105">Sites de recrutamento como o Broadbean ajudam a atingir esse objetivo.</span><span class="sxs-lookup"><span data-stu-id="b015c-105">Recruiting sites such as Broadbean help you accomplish this goal.</span></span> <span data-ttu-id="b015c-106">Agora o Microsoft Dynamics 365 Talent Attract permite postar trabalhos no Broadbean, e a Microsoft está constantemente apresentando novas ofertas nessa área.</span><span class="sxs-lookup"><span data-stu-id="b015c-106">Microsoft Dynamics 365 Talent: Attract now lets you post jobs to Broadbean, and Microsoft is constantly providing new offerings in this area.</span></span>

## <a name="post-jobs-to-broadbean"></a><span data-ttu-id="b015c-107">Postar trabalhos no Broadbean</span><span class="sxs-lookup"><span data-stu-id="b015c-107">Post jobs to Broadbean</span></span>

<span data-ttu-id="b015c-108">Antes de postar trabalhos no Broadbean, você deve configurar a integração dele.</span><span class="sxs-lookup"><span data-stu-id="b015c-108">Before you can post jobs to Broadbean, you must configure the Broadbean integration.</span></span>

> [!NOTE]
> - <span data-ttu-id="b015c-109">Para postar trabalhos em sites externos, você deve ter o [complemento de Contratação abrangente](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span><span class="sxs-lookup"><span data-stu-id="b015c-109">To post jobs to external sites, you must have the [Comprehensive hiring add-on](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).</span></span>
> - <span data-ttu-id="b015c-110">Este recurso está atualmente em visualização.</span><span class="sxs-lookup"><span data-stu-id="b015c-110">This feature is currently in preview.</span></span> <span data-ttu-id="b015c-111">Para experimentá-lo, você deve [ativá-lo nas configurações de administrador do Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span><span class="sxs-lookup"><span data-stu-id="b015c-111">If you want to try it, you must [turn it on in the Attract admin settings](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).</span></span>

### <a name="configure-broadbean-integration"></a><span data-ttu-id="b015c-112">Configurar a integração do Broadbean</span><span class="sxs-lookup"><span data-stu-id="b015c-112">Configure Broadbean integration</span></span>

1. <span data-ttu-id="b015c-113">Entre no Attract como administrador.</span><span class="sxs-lookup"><span data-stu-id="b015c-113">Sign in to Attract as an admin.</span></span>
2. <span data-ttu-id="b015c-114">Selecione o botão **Configurações** (o símbolo de engrenagem) no canto superior direito da página e selecione **Centro de administração**.</span><span class="sxs-lookup"><span data-stu-id="b015c-114">Select the **Settings** button (the gear symbol) in the upper-right corner of the page, and then select **Admin center**.</span></span>
3. <span data-ttu-id="b015c-115">Na guia **Configurações do quadro de trabalho**, na seção **Habilitar a integração do Broadbean**, ative a integração.</span><span class="sxs-lookup"><span data-stu-id="b015c-115">On the **Job board settings** tab, in the **Enable Broadbean integration** section, turn on the integration.</span></span>
4. <span data-ttu-id="b015c-116">Entre em contato com o Broadbean e insira suas informações em **Nome de Usuário, Cliente, Token de Criptografia**.</span><span class="sxs-lookup"><span data-stu-id="b015c-116">Contact Broadbean, and enter your information in **Username, Client ID, Encryption Token**.</span></span>

> [!WARNING]
> <span data-ttu-id="b015c-117">Suas credenciais do Broadbean são confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b015c-117">Your Broadbean credentials are sensitive and confidential.</span></span> <span data-ttu-id="b015c-118">Por esse motivo você deve armazená-las e compartilhá-las de forma responsável.</span><span class="sxs-lookup"><span data-stu-id="b015c-118">Therefore, store and share them responsibly.</span></span> <span data-ttu-id="b015c-119">Qualquer pessoa que tenha a função Administrador no Attract pode ver essas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b015c-119">Anyone who has an Administrator role in Attract can view these credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="b015c-120">A Microsoft e o Attract não estão envolvidos na criação e na manutenção desses valores.</span><span class="sxs-lookup"><span data-stu-id="b015c-120">Microsoft and Attract aren't involved in creating and maintaining these values.</span></span> <span data-ttu-id="b015c-121">É sua responsabilidade mantê-los atualizados no Attract e trabalhar com o Broadbean para resolver quaisquer problemas que envolvam suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b015c-121">It's your responsibility to keep them up to date in Attract and to work with Broadbean to resolve any issues that involve your credentials.</span></span>

### <a name="post-a-job-to-broadbean"></a><span data-ttu-id="b015c-122">Postar um trabalho no Broadbean</span><span class="sxs-lookup"><span data-stu-id="b015c-122">Post a job to Broadbean</span></span>

<span data-ttu-id="b015c-123">Depois que o Broadbean é ativado, os recrutadores e administradores podem postar trabalhos nele.</span><span class="sxs-lookup"><span data-stu-id="b015c-123">After Broadbean has been turned on, recruiters and admins can post a job to it.</span></span> <span data-ttu-id="b015c-124">Você deve ter uma URL de solicitação do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b015c-124">You must have an apply URL for the job.</span></span>

1. <span data-ttu-id="b015c-125">No Attract, abra o trabalho que você quer postar no Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-125">In Attract, open the job that you want to post to Broadbean.</span></span>
2. <span data-ttu-id="b015c-126">Na seção **Postagens**, selecione o botão **Lançar Agora** que corresponde ao Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-126">In the **Postings** section, select the **Post Now** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="b015c-127">Siga as instruções na janela do Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-127">Follow the instructions in the Broadbean window.</span></span>

<span data-ttu-id="b015c-128">O Attract passa as seguintes informações para o Broadbean:</span><span class="sxs-lookup"><span data-stu-id="b015c-128">Attract passes the following information to Broadbean:</span></span>

- <span data-ttu-id="b015c-129">ID da solicitação</span><span class="sxs-lookup"><span data-stu-id="b015c-129">Request ID</span></span>
- <span data-ttu-id="b015c-130">Cargo</span><span class="sxs-lookup"><span data-stu-id="b015c-130">Job title</span></span>
- <span data-ttu-id="b015c-131">Descrição de trabalho</span><span class="sxs-lookup"><span data-stu-id="b015c-131">Job description</span></span>
- <span data-ttu-id="b015c-132">Local de trabalho</span><span class="sxs-lookup"><span data-stu-id="b015c-132">Job location</span></span>
- <span data-ttu-id="b015c-133">URL de solicitação</span><span class="sxs-lookup"><span data-stu-id="b015c-133">Apply URL</span></span>
- <span data-ttu-id="b015c-134">Informações do recrutador</span><span class="sxs-lookup"><span data-stu-id="b015c-134">Recruiter information</span></span>

<span data-ttu-id="b015c-135">Depois que o Broadbean conclui a postagem com êxito, a seção **Postagens** do trabalho no Attract mostra o status do Broadbean como **Enviado**.</span><span class="sxs-lookup"><span data-stu-id="b015c-135">After Broadbean successfully completes the posting, the **Postings** section of the job in Attract shows the Broadbean status as **Posted**.</span></span>

> [!NOTE]
> - <span data-ttu-id="b015c-136">O preenchimento do campo **Indústria** é obrigatório no Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-136">Broadbean requires the **Industry** field.</span></span> <span data-ttu-id="b015c-137">No momento, esse campo é definido como **Tecnologia da Informação** por padrão.</span><span class="sxs-lookup"><span data-stu-id="b015c-137">Currently, this field is set to **IT** by default.</span></span> <span data-ttu-id="b015c-138">Entretanto, você pode alterar o valor para a indústria correta na janela da postagem de trabalho do Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-138">However, you can change the value to the correct industry in the window for Broadbean job posting.</span></span>
> - <span data-ttu-id="b015c-139">O Broadbean precisa de algum tempo para concluir a postagem do trabalho em todos os quadros de trabalho selecionados por você.</span><span class="sxs-lookup"><span data-stu-id="b015c-139">It takes some time for Broadbean to finish posting your job to all the job boards that you selected.</span></span> <span data-ttu-id="b015c-140">Por isso pode haver um pequeno atraso para que o Attract possa mostrar uma atualização do status do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b015c-140">Therefore, there might be a slight delay before Attract provides a status update for the job.</span></span>

### <a name="view-a-broadbean-job-posting"></a><span data-ttu-id="b015c-141">Exibir uma postagem de trabalho do Broadbean</span><span class="sxs-lookup"><span data-stu-id="b015c-141">View a Broadbean job posting</span></span>

<span data-ttu-id="b015c-142">Depois de postar um trabalho no Broadbean, você pode exibi-lo no Attract.</span><span class="sxs-lookup"><span data-stu-id="b015c-142">After you post a job to Broadbean, you can view it from Attract.</span></span>

1. <span data-ttu-id="b015c-143">No Attract, abra o trabalho que você quer exibir no Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-143">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="b015c-144">Na seção **Postagens**, selecione o botão de reticências (**…**) que corresponde ao Broadbean e selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="b015c-144">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>

<span data-ttu-id="b015c-145">A postagem de trabalho do Broadbean aparece em uma nova janela.</span><span class="sxs-lookup"><span data-stu-id="b015c-145">The Broadbean job posting appears in a new window.</span></span>

### <a name="update-a-broadbean-job-posting"></a><span data-ttu-id="b015c-146">Atualizar uma postagem de trabalho do Broadbean</span><span class="sxs-lookup"><span data-stu-id="b015c-146">Update a Broadbean job posting</span></span>

<span data-ttu-id="b015c-147">Você pode atualizar uma postagem de trabalho do Broadbean de duas formas.</span><span class="sxs-lookup"><span data-stu-id="b015c-147">You can update a Broadbean job posting in two ways.</span></span>

1. <span data-ttu-id="b015c-148">No Attract, abra o trabalho que você quer atualizar.</span><span class="sxs-lookup"><span data-stu-id="b015c-148">In Attract, open the job that you want to update.</span></span>
2. <span data-ttu-id="b015c-149">Na seção **Postagens**, selecione o botão **Atualizar Postagem** que corresponde ao Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-149">In the **Postings** section, select the **Update Post** button that corresponds to Broadbean.</span></span>
3. <span data-ttu-id="b015c-150">Edite a postagem na janela do Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-150">Edit the posting in the Broadbean window.</span></span>

<span data-ttu-id="b015c-151">–ou–</span><span class="sxs-lookup"><span data-stu-id="b015c-151">–or–</span></span>

1. <span data-ttu-id="b015c-152">No Attract, abra o trabalho que você quer exibir no Broadbean.</span><span class="sxs-lookup"><span data-stu-id="b015c-152">In Attract, open the job that you want to view on Broadbean.</span></span>
2. <span data-ttu-id="b015c-153">Na seção **Postagens**, selecione o botão de reticências (**…**) que corresponde ao Broadbean e selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="b015c-153">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **View**.</span></span>
3. <span data-ttu-id="b015c-154">Na janela do Broadbean, edite os detalhes do trabalho e repita a postagem.</span><span class="sxs-lookup"><span data-stu-id="b015c-154">In the Broadbean window, edit the job details, and then repost the job.</span></span> <span data-ttu-id="b015c-155">Os detalhes do trabalho no Attract não são modificados.</span><span class="sxs-lookup"><span data-stu-id="b015c-155">The job details in Attract aren't changed.</span></span>

### <a name="remove-a-broadbean-job-posting"></a><span data-ttu-id="b015c-156">Remover uma postagem de trabalho do Broadbean</span><span class="sxs-lookup"><span data-stu-id="b015c-156">Remove a Broadbean job posting</span></span>

<span data-ttu-id="b015c-157">Você pode remover uma postagem de trabalho do Broadbean conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b015c-157">You can remove a job posting from Broadbean as you require.</span></span>

1. <span data-ttu-id="b015c-158">No Attract, abra o trabalho que você quer remover.</span><span class="sxs-lookup"><span data-stu-id="b015c-158">In Attract, open the job that you want to remove.</span></span>
2. <span data-ttu-id="b015c-159">Na seção **Postagens**, selecione o botão de reticências (**…**) que corresponde ao Broadbean e selecione **Remover Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b015c-159">In the **Postings** section, select the ellipsis button (**...**) that corresponds to Broadbean, and then select **Remove Post**.</span></span>

<span data-ttu-id="b015c-160">Depois que o Broadbean remove o trabalho, o item do Broadbean no Attract tem um botão **Lançar Agora**.</span><span class="sxs-lookup"><span data-stu-id="b015c-160">After Broadbean removes the job, the Broadbean item in Attract has a **Post Now** button.</span></span> <span data-ttu-id="b015c-161">A presença desse botão indica que o trabalho foi removido e pode ser postado novamente.</span><span class="sxs-lookup"><span data-stu-id="b015c-161">The presence of this button indicates that the job has been removed and can be posted again.</span></span>

### <a name="troubleshoot-the-broadbean-integration"></a><span data-ttu-id="b015c-162">Solucionar problemas da integração do Broadbean</span><span class="sxs-lookup"><span data-stu-id="b015c-162">Troubleshoot the Broadbean integration</span></span>

<span data-ttu-id="b015c-163">Se tiver dificuldade para postar um trabalho no Broadbean, tente executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b015c-163">If you're having trouble posting a job to Broadbean, try these steps.</span></span>

1. <span data-ttu-id="b015c-164">Verifique se as credenciais do Broadbean que você inseriu no Attract são válidas e estão corretas.</span><span class="sxs-lookup"><span data-stu-id="b015c-164">Verify that the Broadbean credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="b015c-165">Se as credenciais forem válidas e estiverem corretas, entre em contato com o [suporte do Broadbean](https://www.broadbean.com/resources/support/).</span><span class="sxs-lookup"><span data-stu-id="b015c-165">If the credentials are valid and correct, contact [Broadbean support](https://www.broadbean.com/resources/support/).</span></span>
3. <span data-ttu-id="b015c-166">Se o problema persistir, entre em contato com o [suporte da Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="b015c-166">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>
