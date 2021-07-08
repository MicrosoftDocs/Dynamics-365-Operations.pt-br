---
title: Carregar uma configuração no Lifecycle Services
description: Este tópico explica como criar uma nova configuração de relatório eletrônico (ER) e carregá-la no Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
ms.date: 06/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41a8fcf2592bde4901aba703e0cd124b1155dac6
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270550"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a><span data-ttu-id="2be60-103">Carregar uma configuração no Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="2be60-103">Upload a configuration into Lifecycle Services</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2be60-104">Este tópico explica como um usuário na função de Administrador do sistema ou Desenvolvedor de relatório eletrônico pode criar uma nova [configuração do Relatório eletrônico (ER)](../general-electronic-reporting.md#Configuration) e carregá-la na [biblioteca Ativo em nível de projeto](../../lifecycle-services/asset-library.md) no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="2be60-104">This topic explains how a user in the System administrator or Electronic reporting developer role can create a new [Electronic reporting (ER) configuration](../general-electronic-reporting.md#Configuration) and upload it into the [project-level Asset library](../../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2be60-105">O uso do LCS como repositório de armazenamento para configurações de ER está sendo [preterido](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span><span class="sxs-lookup"><span data-stu-id="2be60-105">The use of LCS as a storage repository for ER configurations is being [deprecated](../../../../finance/get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release).</span></span> <span data-ttu-id="2be60-106">Para mais informações, consulte [Regulatory Configuration Service (RCS) - Suspensão do armazenamento do Lifecycle Services (LCS)](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span><span class="sxs-lookup"><span data-stu-id="2be60-106">For more information, see [Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation](../../../../finance/localizations/rcs-lcs-repo-dep-faq.md).</span></span>

<span data-ttu-id="2be60-107">Neste exemplo, você criará uma configuração e a carregará no LCS para uma empresa de exemplo chamada Litware, Inc. Estas etapas podem ser concluídas em qualquer empresa, pois as configurações ER são compartilhadas entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="2be60-107">In this example, you will create a configuration and upload it into LCS for a sample company that is named Litware, Inc. These steps can be completed in any company, because ER configurations are shared among companies.</span></span> <span data-ttu-id="2be60-108">Para concluir estas etapas, primeiro conclua as etapas em [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="2be60-108">To complete these steps, you must first complete the steps in [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="2be60-109">O acesso ao LCS também é necessário.</span><span class="sxs-lookup"><span data-stu-id="2be60-109">Access to LCS is also required.</span></span>

1. <span data-ttu-id="2be60-110">Entre no aplicativo usando uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="2be60-110">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="2be60-111">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="2be60-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="2be60-112">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="2be60-112">System administrator</span></span>

2. <span data-ttu-id="2be60-113">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2be60-113">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="2be60-114">Selecione **Litware, Inc.** e marque-a como **Ativa**.</span><span class="sxs-lookup"><span data-stu-id="2be60-114">Select **Litware, Inc.**, and mark it as **Active**.</span></span>
4. <span data-ttu-id="2be60-115">Selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="2be60-115">Select **Configurations**.</span></span>

<a name="accessconditions"></a>
> [!NOTE]
> <span data-ttu-id="2be60-116">Verifique se o usuário atual do Dynamics 365 Finance é membro do projeto LCS que contém a [biblioteca de ativos](../../lifecycle-services/asset-library.md#asset-library-support) que é usada para importar configurações ER.</span><span class="sxs-lookup"><span data-stu-id="2be60-116">Make sure that the current Dynamics 365 Finance user is a member of the LCS project that contains the [Asset library](../../lifecycle-services/asset-library.md#asset-library-support) that is used to import ER configurations.</span></span>
>
> <span data-ttu-id="2be60-117">Não é possível acessar um projeto LCS a partir de um repositório ER que representa um domínio diferente daquele usado no Finance.</span><span class="sxs-lookup"><span data-stu-id="2be60-117">You can't access an LCS project from an ER repository that represents a different domain than the domain that is used in Finance.</span></span> <span data-ttu-id="2be60-118">Se você tentar, uma lista vazia de projetos LCS será mostrada e não será possível importar configurações ER da biblioteca de ativos em nível de projeto no LCS.</span><span class="sxs-lookup"><span data-stu-id="2be60-118">If you try, an empty list of LCS projects will be shown, and you won't be able to import ER configurations from the project-level Asset library in LCS.</span></span> <span data-ttu-id="2be60-119">Para acessar as bibliotecas de ativos em nível de projeto a partir de um repositório ER usado para importar configurações ER, entre no Finance usando as credenciais de um usuário que pertença ao locatário (domínio) para o qual a instância do Finance atual foi provisionada.</span><span class="sxs-lookup"><span data-stu-id="2be60-119">To access project-level Asset libraries from an ER repository that is used to import ER configurations, sign in to Finance by using the credentials of a user who belongs to the tenant (domain) that the current Finance instance has been provisioned for.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="2be60-120">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="2be60-120">Create a new data model configuration</span></span>

1. <span data-ttu-id="2be60-121">Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.</span><span class="sxs-lookup"><span data-stu-id="2be60-121">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="2be60-122">Na página **Configurações**, selecione **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="2be60-122">On the **Configurations** page, select **Create configuration** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="2be60-123">Neste exemplo, você criará uma configuração contendo um modelo de dados de exemplo para documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="2be60-123">In this example, you will create a configuration that contains a sample data model for electronic documents.</span></span> <span data-ttu-id="2be60-124">Esta configuração do modelo de dados será carregada no LCS posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2be60-124">This data model configuration will be uploaded into LCS later.</span></span>

3. <span data-ttu-id="2be60-125">No campo **Nome**, insira **Configuração do modelo de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="2be60-125">In the **Name** field, enter **Sample model configuration**.</span></span>
4. <span data-ttu-id="2be60-126">No campo **Descrição**, insira **Configuração do modelo de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="2be60-126">In the **Description** field, enter **Sample model configuration**.</span></span>
5. <span data-ttu-id="2be60-127">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="2be60-127">Select **Create configuration**.</span></span>
6. <span data-ttu-id="2be60-128">Selecione **Designer de modelos**.</span><span class="sxs-lookup"><span data-stu-id="2be60-128">Select **Model designer**.</span></span>
7. <span data-ttu-id="2be60-129">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2be60-129">Select **New**.</span></span>
8. <span data-ttu-id="2be60-130">No campo **Nome**, insira **Ponto de entrada**.</span><span class="sxs-lookup"><span data-stu-id="2be60-130">In the **Name** field, enter **Entry point**.</span></span>
9. <span data-ttu-id="2be60-131">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2be60-131">Select **Add**.</span></span>
10. <span data-ttu-id="2be60-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2be60-132">Select **Save**.</span></span>
11. <span data-ttu-id="2be60-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2be60-133">Close the page.</span></span>
12. <span data-ttu-id="2be60-134">Selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="2be60-134">Select **Change status**.</span></span>
13. <span data-ttu-id="2be60-135">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2be60-135">Select **Complete**.</span></span>
14. <span data-ttu-id="2be60-136">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be60-136">Select **OK**.</span></span>
15. <span data-ttu-id="2be60-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2be60-137">Close the page.</span></span>

## <a name="register-a-new-repository"></a><span data-ttu-id="2be60-138">Registrar um novo repositório</span><span class="sxs-lookup"><span data-stu-id="2be60-138">Register a new repository</span></span>

1. <span data-ttu-id="2be60-139">Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2be60-139">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>

2. <span data-ttu-id="2be60-140">Na seção **Provedores de configuração**, selecione o bloco **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="2be60-140">In the **Configuration providers** section, select the **Litware, Inc.** tile.</span></span>

3. <span data-ttu-id="2be60-141">No bloco **Litware, Inc.**, selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="2be60-141">On the **Litware, Inc.** tile, select **Repositories**.</span></span>

    <span data-ttu-id="2be60-142">Agora é possível abrir a lista de repositórios para o provedor de configuração da Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="2be60-142">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

4. <span data-ttu-id="2be60-143">Selecione **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="2be60-143">Select **Add** to open the drop-down dialog box.</span></span>

    <span data-ttu-id="2be60-144">Agora você pode adicionar um novo repositório.</span><span class="sxs-lookup"><span data-stu-id="2be60-144">You can now add a new repository.</span></span>

5. <span data-ttu-id="2be60-145">No campo **Tipo de repositório de configuração**, selecione **LCS**.</span><span class="sxs-lookup"><span data-stu-id="2be60-145">In the **Configuration repository enter** field, select **LCS**.</span></span>
6. <span data-ttu-id="2be60-146">Selecione **Criar repositório**.</span><span class="sxs-lookup"><span data-stu-id="2be60-146">Select **Create repository**.</span></span>
7. <span data-ttu-id="2be60-147">No campo **Projeto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2be60-147">In the **Project** field, enter or select a value.</span></span>

    <span data-ttu-id="2be60-148">Para este exemplo, selecione o projeto LCS desejado.</span><span class="sxs-lookup"><span data-stu-id="2be60-148">For this example, select the desired LCS project.</span></span> <span data-ttu-id="2be60-149">Você deve ter [acesso](#accessconditions) ao projeto.</span><span class="sxs-lookup"><span data-stu-id="2be60-149">You must have [access](#accessconditions) to the project.</span></span>

8. <span data-ttu-id="2be60-150">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be60-150">Select **OK**.</span></span>

    <span data-ttu-id="2be60-151">Concluir uma nova entrada de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="2be60-151">Complete a new repository entry.</span></span>

9. <span data-ttu-id="2be60-152">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2be60-152">In the list, mark the selected row.</span></span>

    <span data-ttu-id="2be60-153">Para este exemplo, selecione o registro de repositório **LCS**.</span><span class="sxs-lookup"><span data-stu-id="2be60-153">For this example, select the **LCS** repository record.</span></span>

    <span data-ttu-id="2be60-154">Observe que um repositório registrado é marcado pelo provedor atual.</span><span class="sxs-lookup"><span data-stu-id="2be60-154">Note that a registered repository is marked by the current provider.</span></span> <span data-ttu-id="2be60-155">Em outras palavras, somente as configurações pertencentes a esse provedor podem ser colocadas neste repositório e, portanto, carregadas no projeto LCS selecionado.</span><span class="sxs-lookup"><span data-stu-id="2be60-155">In other words, only configurations that are owned by that provider can be put in this repository and therefore uploaded into the selected LCS project.</span></span>

10. <span data-ttu-id="2be60-156">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2be60-156">Select **Open**.</span></span>

    <span data-ttu-id="2be60-157">Você abre o repositório para exibir a lista de configurações ER.</span><span class="sxs-lookup"><span data-stu-id="2be60-157">You open the repository to view the list of ER configurations.</span></span> <span data-ttu-id="2be60-158">Se o projeto selecionado ainda não tiver sido usado para compartilhamento de configurações ER, a lista estará vazia.</span><span class="sxs-lookup"><span data-stu-id="2be60-158">If the selected project hasn't yet been used for ER configurations sharing, the list will be empty.</span></span>

11. <span data-ttu-id="2be60-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2be60-159">Close the page.</span></span>
12. <span data-ttu-id="2be60-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2be60-160">Close the page.</span></span>

## <a name="upload-a-configuration-into-lcs"></a><span data-ttu-id="2be60-161">Carregar uma configuração no LCS</span><span class="sxs-lookup"><span data-stu-id="2be60-161">Upload a configuration into LCS</span></span>

1. <span data-ttu-id="2be60-162">Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.</span><span class="sxs-lookup"><span data-stu-id="2be60-162">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="2be60-163">Na página **Configurações**, na árvore de configurações, selecione **Configuração do modelo de exemplo**.</span><span class="sxs-lookup"><span data-stu-id="2be60-163">On the **Configurations** page, in the configurations tree, select **Sample model configuration**.</span></span>

    <span data-ttu-id="2be60-164">Selecione uma configuração criada que já esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="2be60-164">You must select a created configuration that has been already completed.</span></span>

3. <span data-ttu-id="2be60-165">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="2be60-165">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="2be60-166">Para este exemplo, selecione a versão da configuração selecionada com um status **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2be60-166">For this example, select the version of the selected configuration that has a status of **Completed**.</span></span>

4. <span data-ttu-id="2be60-167">Selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="2be60-167">Select **Change status**.</span></span>
5. <span data-ttu-id="2be60-168">Selecione **Compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="2be60-168">Select **Share**.</span></span>

    <span data-ttu-id="2be60-169">O status da configuração é alterado de **Concluído** para **Compartilhado** quando a configuração é publicada no LCS.</span><span class="sxs-lookup"><span data-stu-id="2be60-169">The status of the configuration is changed from **Completed** to **Shared** when the configuration is published in LCS.</span></span>

6. <span data-ttu-id="2be60-170">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be60-170">Select **OK**.</span></span>
7. <span data-ttu-id="2be60-171">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="2be60-171">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="2be60-172">Neste exemplo, selecione a versão da configuração com status **Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="2be60-172">For this example, select the configuration version that has a status of **Shared**.</span></span>

    <span data-ttu-id="2be60-173">Observe que o status da versão selecionada foi alterado de **Concluído** para **Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="2be60-173">Note that the status of the selected version was changed from **Completed** to **Shared**.</span></span>

8. <span data-ttu-id="2be60-174">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2be60-174">Close the page.</span></span>
9. <span data-ttu-id="2be60-175">Selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="2be60-175">Select **Repositories**.</span></span>

    <span data-ttu-id="2be60-176">Agora é possível abrir a lista de repositórios para o provedor de configuração da Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="2be60-176">You can now open the list of repositories for the Litware, Inc. configuration provider.</span></span>

10. <span data-ttu-id="2be60-177">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2be60-177">Select **Open**.</span></span>

    <span data-ttu-id="2be60-178">Para este exemplo, selecione o repositório **LCS** e abra-o.</span><span class="sxs-lookup"><span data-stu-id="2be60-178">For this example, select the **LCS** repository, and open it.</span></span>

    <span data-ttu-id="2be60-179">Observe que a configuração selecionada será mostrada como um ativo do projeto do LCS selecionado.</span><span class="sxs-lookup"><span data-stu-id="2be60-179">Notice that the selected configuration is shown as an asset of the selected LCS project.</span></span>

11. <span data-ttu-id="2be60-180">Para abrir o LCS, acesse <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="2be60-180">Open LCS by going to <https://lcs.dynamics.com>.</span></span>
12. <span data-ttu-id="2be60-181">Abra um projeto que foi usado anteriormente para registro do repositório.</span><span class="sxs-lookup"><span data-stu-id="2be60-181">Open a project that was used earlier for repository registration.</span></span>
13. <span data-ttu-id="2be60-182">Abra a biblioteca de ativos do projeto.</span><span class="sxs-lookup"><span data-stu-id="2be60-182">Open the Asset library of the project.</span></span>
14. <span data-ttu-id="2be60-183">Selecione o tipo de ativo **Configuração GER**.</span><span class="sxs-lookup"><span data-stu-id="2be60-183">Select the **GER configuration** asset type.</span></span>

    <span data-ttu-id="2be60-184">A configuração do ER que você carregou deve ser listada.</span><span class="sxs-lookup"><span data-stu-id="2be60-184">The ER configuration that you uploaded should be listed.</span></span>

    <span data-ttu-id="2be60-185">Observe que a configuração do LCS carregado poderá ser importada para outra instância se os provedores tiverem acesso a esse projeto do LCS.</span><span class="sxs-lookup"><span data-stu-id="2be60-185">Note that the uploaded LCS configuration can be imported into another instance if providers have access to this LCS project.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
