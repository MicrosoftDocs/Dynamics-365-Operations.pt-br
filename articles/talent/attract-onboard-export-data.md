---
title: Exportar dados do Attract e do Onboard
description: Exporte dados do Dynamics 365 Talent - Attract e Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
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
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460274"
---
# <a name="export-data-from-attract-and-onboard"></a><span data-ttu-id="e6f5c-103">Exportar dados do Attract e do Onboard</span><span class="sxs-lookup"><span data-stu-id="e6f5c-103">Export data from Attract and Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e6f5c-104">Como anunciado em [Desativar os aplicativos Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), vamos desativar o Dynamics 365 Talent: Attract e o Dynamics 365 Talent: Onboard em 1º de fevereiro de 2022.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-104">As announced in [Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), we're retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard on February 1, 2022.</span></span> <span data-ttu-id="e6f5c-105">Para ajudar na migração para outro produto, agora os dois aplicativos têm recursos de exportação de dados.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-105">To help with your migration to another product, both apps now provide data export capabilities.</span></span>

## <a name="export-data-from-attract"></a><span data-ttu-id="e6f5c-106">Exportar dados do Attract</span><span class="sxs-lookup"><span data-stu-id="e6f5c-106">Export data from Attract</span></span>

<span data-ttu-id="e6f5c-107">Você pode exportar dados sem restringir o acesso ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-107">You can export your data without restricting access to your environment.</span></span> <span data-ttu-id="e6f5c-108">Convém fazer isso para fins de teste ou para compreender nossa estrutura de dados.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-108">You might want to do this for testing purposes or to understand our data structure.</span></span> <span data-ttu-id="e6f5c-109">Quando estiver pronto para migrar, restrinja o acesso ao ambiente do Attract seguindo as instruções depois deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-109">When you're ready to migrate, restrict access to your Attract environment using the instructions after this procedure.</span></span> <span data-ttu-id="e6f5c-110">Certifique-se de exportar os dados novamente.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-110">Be sure to export your data again.</span></span> 

1. <span data-ttu-id="e6f5c-111">Acesse [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="e6f5c-111">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="e6f5c-112">Em **Exportação de dados**, selecione **Solicitar exportação de dados**.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-112">Under **Data export**, select **Request a data export**.</span></span>

   ![[<span data-ttu-id="e6f5c-113">Solicitar exportação de dados do Attract</span><span class="sxs-lookup"><span data-stu-id="e6f5c-113">Request a data export from Attract</span></span>](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. <span data-ttu-id="e6f5c-114">Quando a caixa de mensagem **Sua solicitação está sendo processada** for exibida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-114">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="e6f5c-115">A exportação de dados pode levar até 20 minutos, dependendo do tamanho.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-115">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="e6f5c-116">Quando a exportação for concluída, selecione o botão **Baixar** ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-116">When your export completes, select the **Download** button next to it.</span></span> 

   >[!NOTE]
   ><span data-ttu-id="e6f5c-117">Todas as exportações de dados ficam disponíveis por sete dias, quando então o link **Baixar** expira.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-117">All data exports are available for seven days, at which point the **Download** link expires.</span></span></br>
   
<span data-ttu-id="e6f5c-118">O download contém um arquivo. zip com os dados do Attract, incluindo as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="e6f5c-118">The download contains a .zip file with your Attract data, including the following folders:</span></span>

| <span data-ttu-id="e6f5c-119">Nome da pasta</span><span class="sxs-lookup"><span data-stu-id="e6f5c-119">Folder name</span></span> | <span data-ttu-id="e6f5c-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6f5c-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="e6f5c-121">Configurações do administrador</span><span class="sxs-lookup"><span data-stu-id="e6f5c-121">Admin settings</span></span> | <span data-ttu-id="e6f5c-122">Configurações do centro de administração do Attract.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-122">Attract admin center configurations.</span></span> |
| <span data-ttu-id="e6f5c-123">Candidatos</span><span class="sxs-lookup"><span data-stu-id="e6f5c-123">Candidates</span></span> | <span data-ttu-id="e6f5c-124">Todos os candidatos adicionados a trabalhos ou grupos de talentos.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-124">All candidates that were added to jobs or talent pools.</span></span> |
| <span data-ttu-id="e6f5c-125">Modelos de email</span><span class="sxs-lookup"><span data-stu-id="e6f5c-125">Email templates</span></span> | <span data-ttu-id="e6f5c-126">Todos os modelos de email configurados para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-126">All email templates that were configured for the environment.</span></span> |
| <span data-ttu-id="e6f5c-127">Modelos de pacote de oferta de trabalho</span><span class="sxs-lookup"><span data-stu-id="e6f5c-127">Job offer package templates</span></span> | <span data-ttu-id="e6f5c-128">Todos os modelos de pacote de oferta de trabalho que foram criados e as configurações associadas.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-128">All job offer package templates that were created, plus their associated configurations.</span></span> |
| <span data-ttu-id="e6f5c-129">Conjuntos de regras de oferta de trabalho</span><span class="sxs-lookup"><span data-stu-id="e6f5c-129">Job offer rule sets</span></span> |  <span data-ttu-id="e6f5c-130">Todos os arquivos de conjunto de regras carregados para gerenciamento de ofertas.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-130">All rule set files that were uploaded for offer management.</span></span> |
| <span data-ttu-id="e6f5c-131">Modelos de oferta de trabalho</span><span class="sxs-lookup"><span data-stu-id="e6f5c-131">Job offer templates</span></span> | <span data-ttu-id="e6f5c-132">Todos os modelos de documento de oferta de trabalho criados para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-132">All job offer document templates created for the environment.</span></span> |
| <span data-ttu-id="e6f5c-133">Oportunidades de emprego</span><span class="sxs-lookup"><span data-stu-id="e6f5c-133">Job openings</span></span> | <span data-ttu-id="e6f5c-134">Todos os trabalhos criados.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-134">All created jobs.</span></span> <span data-ttu-id="e6f5c-135">Os trabalhos excluídos não são exportados.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-135">Deleted jobs aren't exported.</span></span> <span data-ttu-id="e6f5c-136">As subpastas contêm solicitações de emprego de candidatos, com subpastas para os anexos dessas solicitações e pacotes de oferta, quando aplicável.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-136">The sub-folders contain candidate applications, with sub-folders for candidate application attachments and offer packages, where applicable.</span></span> |
| <span data-ttu-id="e6f5c-137">Modelos de oportunidade de emprego</span><span class="sxs-lookup"><span data-stu-id="e6f5c-137">Job opening templates</span></span> | <span data-ttu-id="e6f5c-138">Os modelos de processo de trabalho configurados no ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-138">Job process templates that were configured in the environment.</span></span> |
| <span data-ttu-id="e6f5c-139">Grupos de talentos</span><span class="sxs-lookup"><span data-stu-id="e6f5c-139">Talent pools</span></span> | <span data-ttu-id="e6f5c-140">Todos os grupos de talentos criados, as respectivas listas de colaboradores e as listas de candidatos para os grupos de talentos.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-140">All created talent pools, their contributors lists, and the candidates lists for the talent pools.</span></span> |
| <span data-ttu-id="e6f5c-141">Trabalhadores</span><span class="sxs-lookup"><span data-stu-id="e6f5c-141">Workers</span></span> | <span data-ttu-id="e6f5c-142">Lista de todos os trabalhadores presentes no ambiente, além de suas funções.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-142">List of all the workers who are present in the environment, plus their roles.</span></span> |
| <span data-ttu-id="e6f5c-143">(pasta raiz)</span><span class="sxs-lookup"><span data-stu-id="e6f5c-143">(root folder)</span></span> | <span data-ttu-id="e6f5c-144">Um arquivo de esquema JSON que descreve os campos da estrutura de dados.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-144">A JSON schema file that describes the data structure fields.</span></span> |

### <a name="restrict-access-to-attract"></a><span data-ttu-id="e6f5c-145">Restringir acesso ao Attract</span><span class="sxs-lookup"><span data-stu-id="e6f5c-145">Restrict access to Attract</span></span>

<span data-ttu-id="e6f5c-146">Quando estiver pronto para migrar, restrinja o acesso de não administradores ao ambiente do Attract e exporte os dados.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-146">When you're ready to migrate, restrict non-admins from accessing your Attract environment and export your data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e6f5c-147">A restrição do acesso ao ambiente do Attract é permanente e não pode ser desfeita.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-147">Restricting access to your Attract environment is permanent and can't be undone.</span></span> <span data-ttu-id="e6f5c-148">Se você quiser que os usuários que não são administradores continuem acessando o ambiente, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-148">If you want non-admin users to continue accessing your environment, skip this step.</span></span>

1. <span data-ttu-id="e6f5c-149">Acesse [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="e6f5c-149">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="e6f5c-150">Para impedir o acesso de usuários que não são administradores ao ambiente do Attract, em **Restringir acesso a este aplicativo**, selecione **Restringir acesso agora**.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-150">To restrict non-admins from accessing your Attract environment, under **Restrict access to this app**, select **Restrict access now**.</span></span> <span data-ttu-id="e6f5c-151">A restrição do acesso também cancelará o lançamento de todos os trabalhos ativos já lançados.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-151">Restricting access also unposts any active jobs that have been posted.</span></span>

   ![[<span data-ttu-id="e6f5c-152">Restringir acesso de não administradores ao Attract</span><span class="sxs-lookup"><span data-stu-id="e6f5c-152">Restrict non-admin access to Attract</span></span>](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. <span data-ttu-id="e6f5c-153">Quando você vir o aviso **Esta é uma alteração permanente**, selecione **Restringir acesso** para restringir permanentemente os usuários não administradores do ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-153">When you see the warning **This is a permanent change**, select **Restrict access** to permanently restrict non-admin users from this environment.</span></span> <span data-ttu-id="e6f5c-154">Se você não estiver pronto para realizar esta etapa, selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-154">If you're not ready to complete this step, select **Cancel**.</span></span>

   ![[<span data-ttu-id="e6f5c-155">Aviso que a restrição de acesso é uma alteração permanente</span><span class="sxs-lookup"><span data-stu-id="e6f5c-155">Warning that restricting access is a permanent change</span></span>](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   ><span data-ttu-id="e6f5c-156">Os administradores podem continuar acessando as páginas de exportação de dados e de relatório de pessoas depois que você restringir o acesso ao ambiente do Attract.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-156">Admins can continue to access the data export and person report pages after you restrict access to the Attract environment.</span></span>

## <a name="export-data-from-onboard"></a><span data-ttu-id="e6f5c-157">Exportar dados do Onboard</span><span class="sxs-lookup"><span data-stu-id="e6f5c-157">Export data from Onboard</span></span>

<span data-ttu-id="e6f5c-158">Quando estiver pronto, você poderá baixar modelos, guias e dados de candidatos do Onboard.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-158">When you're ready, you can download templates, guides, and candidate data from Onboard.</span></span>

1. <span data-ttu-id="e6f5c-159">Acesse [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span><span class="sxs-lookup"><span data-stu-id="e6f5c-159">Go to [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span></span>

2. <span data-ttu-id="e6f5c-160">Em **Exportação de dados**, selecione **Solicitar exportação de dados**.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-160">Under **Data export**, select **Request a data export**.</span></span> 

   ![[<span data-ttu-id="e6f5c-161">Solicitar exportação de dados do Onboard</span><span class="sxs-lookup"><span data-stu-id="e6f5c-161">Request a data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. <span data-ttu-id="e6f5c-162">Quando a caixa de mensagem **Sua solicitação está sendo processada** for exibida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-162">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="e6f5c-163">A exportação de dados pode levar até 20 minutos, dependendo do tamanho.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-163">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="e6f5c-164">Quando a exportação for concluída, selecione o botão **Baixar** ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-164">When your export completes, select the **Download** button next to it.</span></span> 

   ![[<span data-ttu-id="e6f5c-165">Baixar exportação de dados do Onboard</span><span class="sxs-lookup"><span data-stu-id="e6f5c-165">Download data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   ><span data-ttu-id="e6f5c-166">A exportação de dados fica disponível por sete dias.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-166">Your data export is available for seven days.</span></span> <span data-ttu-id="e6f5c-167">Após sete dias, o link **Baixar** expira e você deverá solicitar uma nova exportação se precisar baixar os dados novamente.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-167">After seven days, the **Download** link expires, and you must request a new export if you need to download your data again.</span></span> <span data-ttu-id="e6f5c-168">Quando você iniciar uma nova exportação de dados, todos os downloads existentes expirarão depois que a nova exportação for concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-168">When you start a new data export, any existing downloads will expire after the new export succeeds.</span></span>

<span data-ttu-id="e6f5c-169">O download é um arquivo. zip que contém o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e6f5c-169">The download is a .zip file that contains:</span></span>

- <span data-ttu-id="e6f5c-170">Uma pasta **Modelos**, que contém os modelos do Onboard no formato de documento do Word.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-170">A **Templates** folder that contains your Onboard templates in Word document format.</span></span>

- <span data-ttu-id="e6f5c-171">Uma pasta **Guias**, que contém os guias do Onboard no formato de documento do Word.</span><span class="sxs-lookup"><span data-stu-id="e6f5c-171">A **Guides** folder that contains your Onboard guides in Word document format.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6f5c-172">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e6f5c-172">See also</span></span>

[<span data-ttu-id="e6f5c-173">Desativar os aplicativos Dynamics 365 Talent: Attract e Dynamics 365 Talent: Onboard</span><span class="sxs-lookup"><span data-stu-id="e6f5c-173">Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)