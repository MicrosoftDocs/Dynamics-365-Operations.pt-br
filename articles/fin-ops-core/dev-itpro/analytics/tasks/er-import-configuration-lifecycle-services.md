---
title: Importar uma configuração do Lifecycle Services
description: Este tópico descreve como importar uma nova versão de uma configuração de relatório eletrônico (ER) do Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 636ed27c157c8322cc1be4ca8eca10ef37eb8bbc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569500"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="7d028-103">Importar uma configuração do Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="7d028-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7d028-104">Este tópico explica como um usuário na função de Administrador do sistema ou Desenvolvedor de relatório eletrônico pode importar uma nova versão de uma [configuração do Relatório eletrônico (ER)](../general-electronic-reporting.md#Configuration) a partir da [biblioteca Ativo em nível de projeto](../../lifecycle-services/asset-library.md) no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="7d028-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="7d028-105">Neste exemplo, você selecionará a versão desejada da configuração de ER e a importará para uma empresa de exemplo chamada Litware, Inc. Essas etapas podem ser concluídas em qualquer empresa, pois as configurações ER são compartilhadas entre as empresas.</span><span class="sxs-lookup"><span data-stu-id="7d028-105">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="7d028-106">Para completar essas etapas, você deve primeiro completar as etapas em [Carregar uma configuração ER no Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="7d028-106">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="7d028-107">O acesso ao LCS também é necessário.</span><span class="sxs-lookup"><span data-stu-id="7d028-107">Access to LCS is also required.</span></span>

1. <span data-ttu-id="7d028-108">Entre no aplicativo usando uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="7d028-108">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="7d028-109">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="7d028-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="7d028-110">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="7d028-110">System administrator</span></span>

2. <span data-ttu-id="7d028-111">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="7d028-111">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="7d028-112">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="7d028-112">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="7d028-113">Verifique se o usuário atual do Dynamics 365 Finance é membro do projeto LCS que contém a biblioteca de ativos que o usuário deseja [acessar](../../lifecycle-services/asset-library.md#asset-library-support) para importar configurações ER.</span><span class="sxs-lookup"><span data-stu-id="7d028-113">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="7d028-114">Não é possível acessar um projeto LCS a partir de um repositório ER que representa um domínio diferente daquele usado no Finance.</span><span class="sxs-lookup"><span data-stu-id="7d028-114">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="7d028-115">Se você tentar, uma lista vazia de projetos LCS será mostrada e não será possível importar configurações ER da biblioteca de ativos em nível de projeto no LCS.</span><span class="sxs-lookup"><span data-stu-id="7d028-115">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="7d028-116">Para acessar as bibliotecas de ativos em nível de projeto a partir de um repositório ER usado para importar configurações ER, entre no Finance usando as credenciais de um usuário que pertença ao locatário (domínio) para o qual a instância do Finance atual foi provisionada.</span><span class="sxs-lookup"><span data-stu-id="7d028-116">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="7d028-117">Excluir uma versão compartilhada de uma configuração do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="7d028-117">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="7d028-118">Na página **Configurações**, na árvore de configurações, selecione **Configuração do modelo de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="7d028-118">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="7d028-119">Você criou a primeira versão de uma configuração do modelo de dados de exemplo e publicou-a no LCS ao concluir as etapas em [Carregar uma configuração no Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="7d028-119">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="7d028-120">Nesse procedimento, você excluirá esta versão da configuração ER.</span><span class="sxs-lookup"><span data-stu-id="7d028-120">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="7d028-121">Você importará essa versão do LCS mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7d028-121">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="7d028-122">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="7d028-122">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7d028-123">Neste exemplo, selecione a versão da configuração com status **Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="7d028-123">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="7d028-124">Este status indica que a configuração esteve publicada ao LCS.</span><span class="sxs-lookup"><span data-stu-id="7d028-124">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="7d028-125">Selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="7d028-125">Select **Change status**.</span></span>
4. <span data-ttu-id="7d028-126">Selecione **Descontinuar**.</span><span class="sxs-lookup"><span data-stu-id="7d028-126">Select **Discontinue**.</span></span>

    <span data-ttu-id="7d028-127">Ao alterar o status da versão selecionada de **Compartilhado** para **Descontinuado**, você disponibiliza a versão para exclusão.</span><span class="sxs-lookup"><span data-stu-id="7d028-127">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="7d028-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d028-128">Select **OK**.</span></span>
6. <span data-ttu-id="7d028-129">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="7d028-129">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7d028-130">Neste exemplo, selecione a versão da configuração com status **Descontinuado**.</span><span class="sxs-lookup"><span data-stu-id="7d028-130">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="7d028-131">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7d028-131">Select **Delete**.</span></span>
8. <span data-ttu-id="7d028-132">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="7d028-132">Select **Yes**.</span></span>

    <span data-ttu-id="7d028-133">Observe que somente a versão de rascunho 2 da configuração do modelo de dados selecionado está disponível agora.</span><span class="sxs-lookup"><span data-stu-id="7d028-133">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="7d028-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7d028-134">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="7d028-135">Importar uma versão compartilhada de uma configuração do modelo de dados do LCS</span><span class="sxs-lookup"><span data-stu-id="7d028-135">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="7d028-136">Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="7d028-136">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="7d028-137">Na seção **Provedores de configuração**, selecione o bloco **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="7d028-137">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="7d028-138">No bloco **Litware, Inc.**, selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="7d028-138">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="7d028-139">Agora é possível abrir a lista de repositórios para o provedor de configuração da Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="7d028-139">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="7d028-140">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="7d028-140">Select **Open**.</span></span>

    <span data-ttu-id="7d028-141">Para este exemplo, selecione o repositório **LCS** e abra-o.</span><span class="sxs-lookup"><span data-stu-id="7d028-141">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="7d028-142">Você deve ter [acesso](#accessconditions) ao projeto LCS e à biblioteca de ativos que é acessada pelo repositório ER selecionado.</span><span class="sxs-lookup"><span data-stu-id="7d028-142">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="7d028-143">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7d028-143">In the list, mark the selected row.</span></span>

    <span data-ttu-id="7d028-144">Para este exemplo, selecione a primeira versão da **Configuração de modelo de exemplo** na lista de versões.</span><span class="sxs-lookup"><span data-stu-id="7d028-144">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="7d028-145">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="7d028-145">Select **Import**.</span></span>
7. <span data-ttu-id="7d028-146">Selecione **Sim** para confirmar a importação da versão selecionada de LCS.</span><span class="sxs-lookup"><span data-stu-id="7d028-146">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="7d028-147">Uma mensagem informativa confirma que a versão selecionada foi importada com êxito.</span><span class="sxs-lookup"><span data-stu-id="7d028-147">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="7d028-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7d028-148">Close the page.</span></span>
9. <span data-ttu-id="7d028-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7d028-149">Close the page.</span></span>
10. <span data-ttu-id="7d028-150">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="7d028-150">Select **Configurations**.</span></span>
11. <span data-ttu-id="7d028-151">Na árvore, selecione **Configuração do modelo de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="7d028-151">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="7d028-152">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="7d028-152">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="7d028-153">Neste exemplo, selecione a versão da configuração com status **Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="7d028-153">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="7d028-154">Observe que versão 1 compartilhada da configuração do modelo de dados selecionado agora também está disponível.</span><span class="sxs-lookup"><span data-stu-id="7d028-154">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]