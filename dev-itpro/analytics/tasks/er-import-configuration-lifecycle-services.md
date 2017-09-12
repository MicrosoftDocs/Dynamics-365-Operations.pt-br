--- 
title: "Importar uma configuração do Lifecycle Services para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode importar uma nova versão de uma configuração do Relatório eletrônico (RE) do Microsoft Lifecycle Services (LCS)."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0ea1e70f94e4b81919512127578d5927b36db56f
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a><span data-ttu-id="9760c-103">Importar uma configuração do Lifecycle Services para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="9760c-103">Import a configuration from Lifecycle Services for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9760c-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode importar uma nova versão de uma configuração do Relatório eletrônico (RE) do Microsoft Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9760c-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Lifecycle Services (LCS).</span></span>

<span data-ttu-id="9760c-105">Neste exemplo, você selecionará a versão desejada da configuração de ER e a importará para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em qualquer empresa, uma vez que as configurações de ER são compartilhadas entre as empresas.</span><span class="sxs-lookup"><span data-stu-id="9760c-105">In this example, you will select the desired version of the ER configuration and import it for sample company, Litware, Inc. These steps can be performed in any company as ER configurations are shared among companies.</span></span> <span data-ttu-id="9760c-106">Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Carregar uma configuração de ER no Lifecycle Services".</span><span class="sxs-lookup"><span data-stu-id="9760c-106">To complete these steps, you must first complete the steps in the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="9760c-107">O acesso ao LCS também é necessário para a conclusão dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="9760c-107">Access to LCS is also required for completion of these steps.</span></span>

1. <span data-ttu-id="9760c-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9760c-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9760c-109">Clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="9760c-109">Click Configurations.</span></span>

## <a name="delete-a-shared-version-of-data-model-configuration"></a><span data-ttu-id="9760c-110">Excluir uma versão compartilhada de configuração do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="9760c-110">Delete a shared version of data model configuration</span></span>
1. <span data-ttu-id="9760c-111">Na árvore, selecione "Configuração do modelo de exemplo".</span><span class="sxs-lookup"><span data-stu-id="9760c-111">In the tree, select 'Sample model configuration'.</span></span>
    * <span data-ttu-id="9760c-112">A primeira versão de uma configuração do modelo de dados de amostra foi criada e publicada ao LCS durante o procedimento "Carregamento de uma configuração ER em um Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="9760c-112">The first version of a sample data model configuration has been created and published to LCS during the “Upload an ER configuration into Lifecycle Services” procedure.</span></span> <span data-ttu-id="9760c-113">Nesse procedimento, você excluirá esta versão da configuração de ER.</span><span class="sxs-lookup"><span data-stu-id="9760c-113">In this procedure, you will delete this version of the ER configuration.</span></span> <span data-ttu-id="9760c-114">Esta versão de configuração do modelo de dados de amostra será importada posteriormente do LCS.</span><span class="sxs-lookup"><span data-stu-id="9760c-114">This version of a sample data model configuration will be imported later from LCS.</span></span>  
2. <span data-ttu-id="9760c-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9760c-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9760c-116">Selecione a versão dessa configuração que tem um status "Compartilhado".</span><span class="sxs-lookup"><span data-stu-id="9760c-116">Select the version of this configuration that is in the ‘Shared’ status.</span></span> <span data-ttu-id="9760c-117">Este status indica que a configuração esteve publicada ao LCS.</span><span class="sxs-lookup"><span data-stu-id="9760c-117">This status indicates that the configuration has been published to LCS.</span></span>  
3. <span data-ttu-id="9760c-118">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="9760c-118">Click Change status.</span></span>
4. <span data-ttu-id="9760c-119">Clique em Descontinuar.</span><span class="sxs-lookup"><span data-stu-id="9760c-119">Click Discontinue.</span></span>
    * <span data-ttu-id="9760c-120">Altere o status da versão selecionada de "Compartilhado" para "Interrompido" para tornar a exclusão disponível.</span><span class="sxs-lookup"><span data-stu-id="9760c-120">Change the status of the selected version from ‘Shared’ to ‘Discontinued’ to make it available for deletion.</span></span>  
5. <span data-ttu-id="9760c-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9760c-121">Click OK.</span></span>
6. <span data-ttu-id="9760c-122">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9760c-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9760c-123">Selecione a versão dessa configuração que tem um status "Interrompido".</span><span class="sxs-lookup"><span data-stu-id="9760c-123">Select the version of this configuration that has a status of ‘Discontinued’.</span></span>  
7. <span data-ttu-id="9760c-124">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="9760c-124">Click Delete.</span></span>
8. <span data-ttu-id="9760c-125">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="9760c-125">Click Yes.</span></span>
    * <span data-ttu-id="9760c-126">Observe que somente a versão de rascunho 2 da configuração selecionada do modelo de dados está disponível.</span><span class="sxs-lookup"><span data-stu-id="9760c-126">Note that the only draft version 2 of the selected data model configuration is available.</span></span>  
9. <span data-ttu-id="9760c-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9760c-127">Close the page.</span></span>

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a><span data-ttu-id="9760c-128">Importar uma versão compartilhada de configuração do modelo de dados do LCS</span><span class="sxs-lookup"><span data-stu-id="9760c-128">Import a shared version of data model configuration from LCS</span></span>
1. <span data-ttu-id="9760c-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9760c-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9760c-130">Abra a lista de repositórios para a 'Litware, Inc.'.</span><span class="sxs-lookup"><span data-stu-id="9760c-130">Open the list of repositories for the ‘Litware, Inc.’</span></span> <span data-ttu-id="9760c-131">provedor de configuração.</span><span class="sxs-lookup"><span data-stu-id="9760c-131">configuration provider.</span></span>  
2. <span data-ttu-id="9760c-132">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="9760c-132">Click Repositories.</span></span>
3. <span data-ttu-id="9760c-133">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="9760c-133">Click Open.</span></span>
    * <span data-ttu-id="9760c-134">Selecione a loja de LCS e a abra.</span><span class="sxs-lookup"><span data-stu-id="9760c-134">Select the LCS repository and open it.</span></span>  
4. <span data-ttu-id="9760c-135">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9760c-135">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="9760c-136">Selecione a primeira versão da "Configuração de modelo de exemplo" na lista de versões.</span><span class="sxs-lookup"><span data-stu-id="9760c-136">Select the first version of the 'Sample model configuration' in the versions list.</span></span>  
5. <span data-ttu-id="9760c-137">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="9760c-137">Click Import.</span></span>
6. <span data-ttu-id="9760c-138">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="9760c-138">Click Yes.</span></span>
    * <span data-ttu-id="9760c-139">Confirme a importação da versão selecionada de LCS.</span><span class="sxs-lookup"><span data-stu-id="9760c-139">Confirm the import of the selected version from LCS .</span></span>  
    * <span data-ttu-id="9760c-140">Observe que a mensagem informativa (acima do formulário) confirma a conclusão bem-sucedida de importação da versão selecionada.</span><span class="sxs-lookup"><span data-stu-id="9760c-140">Note that the information message (above the form) confirms the successful completion of the import of the selected version.</span></span>  
7. <span data-ttu-id="9760c-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9760c-141">Close the page.</span></span>
8. <span data-ttu-id="9760c-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9760c-142">Close the page.</span></span>
9. <span data-ttu-id="9760c-143">Clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="9760c-143">Click Configurations.</span></span>
10. <span data-ttu-id="9760c-144">Na árvore, selecione "Configuração do modelo de exemplo".</span><span class="sxs-lookup"><span data-stu-id="9760c-144">In the tree, select 'Sample model configuration'.</span></span>
11. <span data-ttu-id="9760c-145">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9760c-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9760c-146">Selecione a versão dessa configuração que tem um status "Compartilhado".</span><span class="sxs-lookup"><span data-stu-id="9760c-146">Select the version of this configuration that has a status of ‘Shared’.</span></span>  
    * <span data-ttu-id="9760c-147">Observe que versão 1 compartilhada da configuração do modelo de dados selecionada agora também está disponível.</span><span class="sxs-lookup"><span data-stu-id="9760c-147">Note that the shared version 1 of the selected data model configuration is available now as well.</span></span>  


