--- 
title: "Carregar uma configuração no Lifecycle Services para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração do Relatório eletrônico (RE) e carregá-la ao Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3d9c2192bac8477e9c9376aab3e3b561da777569
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---
# <a name="upload-a-configuration-into-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="4dcba-103">Carregar uma configuração no Lifecycle Services para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="4dcba-103">Upload a configuration into Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4dcba-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração do Relatório eletrônico (RE) e carregá-la ao Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4dcba-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration and upload it into Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="4dcba-105">Neste exemplo, você criará e carregará uma configuração para o LCS (Lifecycle Services) da empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa, uma vez que as configurações ER são compartilhadas entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="4dcba-105">In this example, you will create a configuration and upload it to LCS for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="4dcba-106">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="4dcba-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="4dcba-107">O acesso ao LCS também é necessário para a conclusão dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="4dcba-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="4dcba-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4dcba-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="4dcba-109">Selecione 'Litware, Inc.'</span><span class="sxs-lookup"><span data-stu-id="4dcba-109">Select ‘Litware, Inc.’</span></span> <span data-ttu-id="4dcba-110">e defina-a como ativa.</span><span class="sxs-lookup"><span data-stu-id="4dcba-110">and set it as active.</span></span>
3. <span data-ttu-id="4dcba-111">Clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="4dcba-111">Click Configurations.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="4dcba-112">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="4dcba-112">Create a new data model configuration</span></span>
1. <span data-ttu-id="4dcba-113">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4dcba-113">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="4dcba-114">Você irá criar uma configuração que contém um modelo de dados de exemplo para documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="4dcba-114">You will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="4dcba-115">Esta configuração do modelo de dados será carregada no LCS posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4dcba-115">This data model configuration will be uploaded into LCS later.</span></span>  
2. <span data-ttu-id="4dcba-116">No campo Nome, digite "Configuração de modelo de exemplo".</span><span class="sxs-lookup"><span data-stu-id="4dcba-116">In the Name field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="4dcba-117">Configuração do modelo de exemplo</span><span class="sxs-lookup"><span data-stu-id="4dcba-117">Sample model configuration</span></span>  
3. <span data-ttu-id="4dcba-118">No campo Descrição, digite 'Configuração do modelo de exemplo'.</span><span class="sxs-lookup"><span data-stu-id="4dcba-118">In the Description field, type 'Sample model configuration'.</span></span>
    * <span data-ttu-id="4dcba-119">Configuração do modelo de exemplo</span><span class="sxs-lookup"><span data-stu-id="4dcba-119">Sample model configuration</span></span>  
4. <span data-ttu-id="4dcba-120">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="4dcba-120">Click Create configuration.</span></span>
5. <span data-ttu-id="4dcba-121">Clique em Designer de modelo.</span><span class="sxs-lookup"><span data-stu-id="4dcba-121">Click Model designer.</span></span>
6. <span data-ttu-id="4dcba-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4dcba-122">Click New.</span></span>
7. <span data-ttu-id="4dcba-123">No campo Nome, digite "Ponto de entrada".</span><span class="sxs-lookup"><span data-stu-id="4dcba-123">In the Name field, type 'Entry point'.</span></span>
    * <span data-ttu-id="4dcba-124">Ponto de entrada</span><span class="sxs-lookup"><span data-stu-id="4dcba-124">Entry point</span></span>  
8. <span data-ttu-id="4dcba-125">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4dcba-125">Click Add.</span></span>
9. <span data-ttu-id="4dcba-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4dcba-126">Click Save.</span></span>
10. <span data-ttu-id="4dcba-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4dcba-127">Close the page.</span></span>
11. <span data-ttu-id="4dcba-128">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="4dcba-128">Click Change status.</span></span>
12. <span data-ttu-id="4dcba-129">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="4dcba-129">Click Complete.</span></span>
13. <span data-ttu-id="4dcba-130">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4dcba-130">Click OK.</span></span>

## <a name="register-a-new--repository"></a><span data-ttu-id="4dcba-131">Registrar um novo repositório</span><span class="sxs-lookup"><span data-stu-id="4dcba-131">Register a new  repository</span></span>
1. <span data-ttu-id="4dcba-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4dcba-132">Close the page.</span></span>
2. <span data-ttu-id="4dcba-133">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="4dcba-133">Click Repositories.</span></span>
    * <span data-ttu-id="4dcba-134">Isso permite que você abra a lista de repositórios para o provedor de configuração da Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="4dcba-134">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
3. <span data-ttu-id="4dcba-135">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4dcba-135">Click Add to open the drop dialog.</span></span>
    * <span data-ttu-id="4dcba-136">Isso permite que você adicione um novo armazenamento.</span><span class="sxs-lookup"><span data-stu-id="4dcba-136">This allows you to add a new repository.</span></span>  
4. <span data-ttu-id="4dcba-137">No campo Tipo de configuração do repositório, selecione LCS.</span><span class="sxs-lookup"><span data-stu-id="4dcba-137">In the Configuration repository type field, select LCS.</span></span>
5. <span data-ttu-id="4dcba-138">Clique em Criar repositório.</span><span class="sxs-lookup"><span data-stu-id="4dcba-138">Click Create repository.</span></span>
6. <span data-ttu-id="4dcba-139">No campo Projeto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4dcba-139">In the Project field, enter or select a value.</span></span>
    * <span data-ttu-id="4dcba-140">Selecione o projeto LCS desejado.</span><span class="sxs-lookup"><span data-stu-id="4dcba-140">Select the desired LCS project.</span></span> <span data-ttu-id="4dcba-141">Você deve ter acesso ao projeto.</span><span class="sxs-lookup"><span data-stu-id="4dcba-141">You must have access to the project.</span></span>  
7. <span data-ttu-id="4dcba-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4dcba-142">Click OK.</span></span>
    * <span data-ttu-id="4dcba-143">Concluir uma nova entrada de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="4dcba-143">Complete a new repository entry.</span></span>  
8. <span data-ttu-id="4dcba-144">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4dcba-144">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4dcba-145">Selecionar o registro de repositório LCS.</span><span class="sxs-lookup"><span data-stu-id="4dcba-145">Select the LCS repository record.</span></span>  
    * <span data-ttu-id="4dcba-146">Observe que uma loja registrada está marcada por importância atual do fornecedor que as únicas configurações de propriedade do fornecedor podem ser colocadas para esta loja e, consequentemente, ser cobradas no projeto selecionado de LCS.</span><span class="sxs-lookup"><span data-stu-id="4dcba-146">Note that a registered repository is marked by the current provider meaning that the only configurations owned by that provider can be placed to this repository and, consequently, uploaded into the selected LCS project.</span></span>  
9. <span data-ttu-id="4dcba-147">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="4dcba-147">Click Open.</span></span>
    * <span data-ttu-id="4dcba-148">Abra o armazenamento para exibir a lista de configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="4dcba-148">Open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="4dcba-149">Ficará vazio se o projeto ainda não foi usado para compartilhamento das configurações de ER.</span><span class="sxs-lookup"><span data-stu-id="4dcba-149">It will be empty if this project has not yet been used for ER configurations sharing.</span></span>  
10. <span data-ttu-id="4dcba-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4dcba-150">Close the page.</span></span>
11. <span data-ttu-id="4dcba-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4dcba-151">Close the page.</span></span>

## <a name="upload-configuration-into-lcs"></a><span data-ttu-id="4dcba-152">Carregar configuração para o LCS</span><span class="sxs-lookup"><span data-stu-id="4dcba-152">Upload configuration into LCS</span></span>
1. <span data-ttu-id="4dcba-153">Clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="4dcba-153">Click Configurations.</span></span>
2. <span data-ttu-id="4dcba-154">Na árvore, selecione "Configuração do modelo de exemplo".</span><span class="sxs-lookup"><span data-stu-id="4dcba-154">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="4dcba-155">Selecione uma configuração criada que já esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="4dcba-155">Select a created configuration that has been already completed.</span></span>  
3. <span data-ttu-id="4dcba-156">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="4dcba-156">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4dcba-157">Selecione a versão da configuração selecionada com o status de "Concluído".</span><span class="sxs-lookup"><span data-stu-id="4dcba-157">Select the version of the selected configuration with the status of ‘Completed’.</span></span>  
4. <span data-ttu-id="4dcba-158">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="4dcba-158">Click Change status.</span></span>
5. <span data-ttu-id="4dcba-159">Clique em Compartilhar.</span><span class="sxs-lookup"><span data-stu-id="4dcba-159">Click Share.</span></span>
    * <span data-ttu-id="4dcba-160">O status da configuração será alterado de "Concluído" para "Compartilhado" quando for publicado no LCS.</span><span class="sxs-lookup"><span data-stu-id="4dcba-160">The configuration status will change from ‘Completed’ to ‘Shared’ when it is published in LCS.</span></span>  
6. <span data-ttu-id="4dcba-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4dcba-161">Click OK.</span></span>
7. <span data-ttu-id="4dcba-162">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="4dcba-162">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4dcba-163">Selecione a versão da configuração com o status de "Compartilhado".</span><span class="sxs-lookup"><span data-stu-id="4dcba-163">Select the configuration version with the status of 'Shared'.</span></span>  
    * <span data-ttu-id="4dcba-164">Observe que o status da versão selecionada foi alterado de "Concluído" para "Compartilhado".</span><span class="sxs-lookup"><span data-stu-id="4dcba-164">Note that the status of the selected version has changed from ‘Completed’ to ‘Shared’.</span></span>  
8. <span data-ttu-id="4dcba-165">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4dcba-165">Close the page.</span></span>
9. <span data-ttu-id="4dcba-166">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="4dcba-166">Click Repositories.</span></span>
    * <span data-ttu-id="4dcba-167">Isso permite que você abra a lista de repositórios para o provedor de configuração da Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="4dcba-167">This enables you to open the list of repositories for the Litware, Inc. configuration provider.</span></span>  
10. <span data-ttu-id="4dcba-168">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="4dcba-168">Click Open.</span></span>
    * <span data-ttu-id="4dcba-169">Selecione a loja de LCS e a abra.</span><span class="sxs-lookup"><span data-stu-id="4dcba-169">Select the LCS repository and open it.</span></span>  
    * <span data-ttu-id="4dcba-170">Observe que a configuração selecionada será mostrada como um ativo do projeto selecionado de LCS.</span><span class="sxs-lookup"><span data-stu-id="4dcba-170">Note that the selected configuration is shown as an asset of the selected LCS project.</span></span>  
    * <span data-ttu-id="4dcba-171">Abrir LCS usando https://lcs.dynamics.com. Abra um projeto que tenha sido usado anteriormente para registro do repositório, abra a "Biblioteca de ativo" deste projeto, e expanda o conteúdo do tipo de ativo "Configuração GER" - a configuração ER carregada estará disponível.</span><span class="sxs-lookup"><span data-stu-id="4dcba-171">Open LCS using https://lcs.dynamics.com. Open a project that was used earlier for repository registration, open the ‘Asset library’ of this project, and expand the content of the ‘GER configuration’ asset type – the uploaded ER configuration will be available.</span></span> <span data-ttu-id="4dcba-172">Observe que a configuração do LCS carregada pode ser importada para outra instância do Microsoft Dynamics 365 for Finance and Operations, se os fornecedores tiverem acesso a este projeto do LCS.</span><span class="sxs-lookup"><span data-stu-id="4dcba-172">Note that the uploaded LCS configuration can be imported to another Microsoft Dynamics 365 for Finance and Operations instance if providers have access to this LCS project.</span></span>  


