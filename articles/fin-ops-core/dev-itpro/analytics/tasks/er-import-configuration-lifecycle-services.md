---
title: Importar uma configuração do Lifecycle Services
description: Este tópico descreve como importar uma nova versão de uma configuração de relatório eletrônico (ER) do Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
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
ms.openlocfilehash: b58ecb8a7d6f52631dbca7642a4acbcf6ff895a3
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270828"
---
# <a name="import-a-configuration-from-lifecycle-services"></a><span data-ttu-id="c1d5e-103">Importar uma configuração do Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="c1d5e-103">Import a configuration from Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c1d5e-104">Este tópico explica como um usuário na função de Administrador do sistema ou Desenvolvedor de relatório eletrônico pode importar uma nova versão de uma [configuração do Relatório eletrônico (ER)](../general-electronic-reporting.md#Configuration) a partir da [biblioteca Ativo em nível de projeto](../../lifecycle-services/asset-library.md) no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c1d5e-104">This topic explains how a user in the System administrator or Electronic reporting developer role can import a new version of an [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) from the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1d5e-105">O uso do LCS como repositório de armazenamento para configurações de ER está sendo [preterido](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="c1d5e-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="c1d5e-106">Para mais informações, consulte [Regulatory Configuration Service (RCS) - Suspensão do armazenamento do Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span><span class="sxs-lookup"><span data-stu-id="c1d5e-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="c1d5e-107">Neste exemplo, você selecionará a versão desejada da configuração de ER e a importará para uma empresa de exemplo chamada Litware, Inc. Essas etapas podem ser concluídas em qualquer empresa, pois as configurações ER são compartilhadas entre as empresas.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-107">In this example, you will select the desired version of the ER configuration and import it for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="c1d5e-108">Para completar essas etapas, você deve primeiro completar as etapas em [Carregar uma configuração ER no Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1d5e-108">To complete these steps, you must first complete the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="c1d5e-109">O acesso ao LCS também é necessário.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="c1d5e-110">Entre no aplicativo usando uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="c1d5e-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="c1d5e-111">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="c1d5e-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="c1d5e-112">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="c1d5e-112">System administrator</span></span>

2. <span data-ttu-id="c1d5e-113">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="c1d5e-114">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-114">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="c1d5e-115">Verifique se o usuário atual do Dynamics 365 Finance é membro do projeto LCS que contém a biblioteca de ativos que o usuário deseja [acessar](../../lifecycle-services/asset-library.md#asset-library-support) para importar configurações ER.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-115">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the Asset library that the user wants to [access](../../lifecycle-services/asset-library.md#asset-library-support) to import ER configurations.</span></span>
>
> <span data-ttu-id="c1d5e-116">Não é possível acessar um projeto LCS a partir de um repositório ER que representa um domínio diferente daquele usado no Finance.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-116">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="c1d5e-117">Se você tentar, uma lista vazia de projetos LCS será mostrada e não será possível importar configurações ER da biblioteca de ativos em nível de projeto no LCS.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-117">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="c1d5e-118">Para acessar as bibliotecas de ativos em nível de projeto a partir de um repositório ER usado para importar configurações ER, entre no Finance usando as credenciais de um usuário que pertença ao locatário (domínio) para o qual a instância do Finance atual foi provisionada.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-118">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a><span data-ttu-id="c1d5e-119">Excluir uma versão compartilhada de uma configuração do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="c1d5e-119">Delete a shared version of a data model configuration</span></span>

1. <span data-ttu-id="c1d5e-120">Na página **Configurações**, na árvore de configurações, selecione **Configuração do modelo de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-120">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="c1d5e-121">Você criou a primeira versão de uma configuração do modelo de dados de exemplo e publicou-a no LCS ao concluir as etapas em [Carregar uma configuração no Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1d5e-121">You created the first version of a sample data model configuration and published it to LCS when you completed the steps in [Upload a configuration into Lifecycle Services](er-upload-configuration-into-lifecycle-services.md).</span></span> <span data-ttu-id="c1d5e-122">Nesse procedimento, você excluirá esta versão da configuração ER.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-122">In this procedure, you will delete that version of the ER configuration.</span></span> <span data-ttu-id="c1d5e-123">Você importará essa versão do LCS mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-123">You will then import that version from LCS later in this topic.</span></span>

2. <span data-ttu-id="c1d5e-124">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-124">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c1d5e-125">Neste exemplo, selecione a versão da configuração com status **Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-125">For this example, select the version of the configuration that has a status of **Shared**.</span></span> <span data-ttu-id="c1d5e-126">Este status indica que a configuração esteve publicada ao LCS.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-126">This status indicates that the configuration has been published to LCS.</span></span>

3. <span data-ttu-id="c1d5e-127">Selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-127">Select **Change status**.</span></span>
4. <span data-ttu-id="c1d5e-128">Selecione **Descontinuar**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-128">Select **Discontinue**.</span></span>

    <span data-ttu-id="c1d5e-129">Ao alterar o status da versão selecionada de **Compartilhado** para **Descontinuado**, você disponibiliza a versão para exclusão.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-129">By changing the status of the selected version from **Shared** to **Discontinued**, you make the version available for deletion.</span></span>

5. <span data-ttu-id="c1d5e-130">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-130">Select **OK**.</span></span>
6. <span data-ttu-id="c1d5e-131">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-131">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c1d5e-132">Neste exemplo, selecione a versão da configuração com status **Descontinuado**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-132">For this example, select the version of the configuration that has a status of **Discontinued**.</span></span>

7. <span data-ttu-id="c1d5e-133">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-133">Select **Delete**.</span></span>
8. <span data-ttu-id="c1d5e-134">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-134">Select **Yes**.</span></span>

    <span data-ttu-id="c1d5e-135">Observe que somente a versão de rascunho 2 da configuração do modelo de dados selecionado está disponível agora.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-135">Notice that the only draft version 2 of the selected data model configuration is now available.</span></span>

9. <span data-ttu-id="c1d5e-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-136">Close the page.</span></span>

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a><span data-ttu-id="c1d5e-137">Importar uma versão compartilhada de uma configuração do modelo de dados do LCS</span><span class="sxs-lookup"><span data-stu-id="c1d5e-137">Import a shared version of a data model configuration from LCS</span></span>

1. <span data-ttu-id="c1d5e-138">Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-138">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="c1d5e-139">Na seção **Provedores de configuração**, selecione o bloco **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-139">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="c1d5e-140">No bloco **Litware, Inc.**, selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-140">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="c1d5e-141">Agora é possível abrir a lista de repositórios para o provedor de configuração da Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-141">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="c1d5e-142">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-142">Select **Open**.</span></span>

    <span data-ttu-id="c1d5e-143">Para este exemplo, selecione o repositório **LCS** e abra-o.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-143">For this example, select the **LCS** repository, and open it.</span></span> <span data-ttu-id="c1d5e-144">Você deve ter [acesso](#accessconditions) ao projeto LCS e à biblioteca de ativos que é acessada pelo repositório ER selecionado.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-144">You must have [access](#accessconditions) to the LCS project and to the Asset library that is accessed by the selected ER repository.</span></span>

5. <span data-ttu-id="c1d5e-145">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-145">In the list, mark the selected row.</span></span>

    <span data-ttu-id="c1d5e-146">Para este exemplo, selecione a primeira versão da **Configuração de modelo de exemplo** na lista de versões.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-146">For this example, select the first version of **Sample model configuration** in the version list.</span></span>

6. <span data-ttu-id="c1d5e-147">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-147">Select **Import**.</span></span>
7. <span data-ttu-id="c1d5e-148">Selecione **Sim** para confirmar a importação da versão selecionada de LCS.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-148">Select **Yes** to confirm the import of the selected version from LCS.</span></span>

    <span data-ttu-id="c1d5e-149">Uma mensagem informativa confirma que a versão selecionada foi importada com êxito.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-149">An informational message confirms that the selected version was successfully imported.</span></span>

8. <span data-ttu-id="c1d5e-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-150">Close the page.</span></span>
9. <span data-ttu-id="c1d5e-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-151">Close the page.</span></span>
10. <span data-ttu-id="c1d5e-152">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-152">Select **Configurations**.</span></span>
11. <span data-ttu-id="c1d5e-153">Na árvore, selecione **Configuração do modelo de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-153">In the tree, select **Sample model configuration**.</span></span>
12. <span data-ttu-id="c1d5e-154">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-154">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="c1d5e-155">Neste exemplo, selecione a versão da configuração com status **Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-155">For this example, select the version of the configuration that has a status of **Shared**.</span></span>

    <span data-ttu-id="c1d5e-156">Observe que versão 1 compartilhada da configuração do modelo de dados selecionado agora também está disponível.</span><span class="sxs-lookup"><span data-stu-id="c1d5e-156">Notice that shared version 1 of the selected data model configuration is also available now.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
