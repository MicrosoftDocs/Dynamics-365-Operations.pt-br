---
title: Compartilhar configurações de ER no RCS/Repositório global com organizações externas
description: Este tópico explica como compartilhar as configurações de relatório eletrônico (ER) no Microsoft Regulatory Configuration Services/o Repositório global diretamente com organizações externas.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 04c46824123906eccbfff18a03974c8043729e0a
ms.sourcegitcommit: 204cec8ca2a6c4474d21dbcd408e369131a47856
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "3371230"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a><span data-ttu-id="85dc1-103">Compartilhar as configurações de relatório eletrônico (ER) no Regulatory Configuration Services/Repositório global diretamente com organizações externas</span><span class="sxs-lookup"><span data-stu-id="85dc1-103">Share Electronic reporting (ER) configurations in Regulatory Configuration Services (RCS) Global repository with external organizations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="85dc1-104">Você pode usar o Microsoft Regulatory Configuration Services (RCS) para compartilhar configurações de relatório eletrônico (ER) e publicá-los em organizações externas.</span><span class="sxs-lookup"><span data-stu-id="85dc1-104">You can use Microsoft Regulatory Configuration Services (RCS) to share Electronic reporting (ER) configurations and then publish them to external organizations.</span></span>

<span data-ttu-id="85dc1-105">Os procedimentos a seguir explicam como um usuário RCS pode compartilhar uma versão de uma configuração ER que foi configurada em uma instância RCS com uma organização externa.</span><span class="sxs-lookup"><span data-stu-id="85dc1-105">The following procedures explain how an RCS user can share a version of an ER configuration that has been configured in an RCS instance with an external organization.</span></span> <span data-ttu-id="85dc1-106">Antes de concluir esses procedimentos, conclua os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="85dc1-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="85dc1-107">Acessar uma instância RCS.</span><span class="sxs-lookup"><span data-stu-id="85dc1-107">Access an RCS instance.</span></span>
- <span data-ttu-id="85dc1-108">Criar um fornecedor de configuração ativa.</span><span class="sxs-lookup"><span data-stu-id="85dc1-108">Create an active configuration provider.</span></span> <span data-ttu-id="85dc1-109">Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="85dc1-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
- <span data-ttu-id="85dc1-110">Criar e carregar uma nova versão de uma configuração ER.</span><span class="sxs-lookup"><span data-stu-id="85dc1-110">Create and upload a new version of an ER configuration.</span></span> <span data-ttu-id="85dc1-111">Para obter mais informações, consulte [Criar e carregar uma nova versão de uma configuração de relatório eletrônico (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="85dc1-111">For more information, see [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

<span data-ttu-id="85dc1-112">Você também deve verificar se um ambiente RCS foi provisionado para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="85dc1-112">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="85dc1-113">Em um aplicativo do Finance and Operations, acesse **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="85dc1-113">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="85dc1-114">Se não tiver o ambiente do RCS provisionado para sua empresa, clique no link externo **Regulatory services – Configuração** e siga as instruções para provisionar um.</span><span class="sxs-lookup"><span data-stu-id="85dc1-114">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="85dc1-115">Se um ambiente RCS já foi provisionado para sua empresa, use a URL da página para acessá-lo, selecionando a opção de entrada.</span><span class="sxs-lookup"><span data-stu-id="85dc1-115">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="verify-the-configuration-that-you-want-to-share"></a><span data-ttu-id="85dc1-116">Verificar a configuração que você deseja compartilhar</span><span class="sxs-lookup"><span data-stu-id="85dc1-116">Verify the configuration that you want to share</span></span>

<span data-ttu-id="85dc1-117">Siga estas etapas para verificar se a configuração que você deseja compartilhar já foi carregada no repositório global.</span><span class="sxs-lookup"><span data-stu-id="85dc1-117">Follow these steps to verify that the configuration that you want to share has already been uploaded to the Global repository.</span></span>

1. <span data-ttu-id="85dc1-118">No espaço de trabalho **Relatório eletrônico**, selecione **Repositórios** para o provedor de configuração.</span><span class="sxs-lookup"><span data-stu-id="85dc1-118">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>

    ![Provedores de configuração](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_config_provider.JPG)

2. <span data-ttu-id="85dc1-120">Selecione **Repositório global** \> **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="85dc1-120">Select **Global repository** \> **Open**.</span></span>
3. <span data-ttu-id="85dc1-121">Pesquise pela configuração que você deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="85dc1-121">Search for the configuration that you want to share.</span></span> <span data-ttu-id="85dc1-122">Você pode usar o campo de filtro para restringir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="85dc1-122">You can use the filter field to narrow your search.</span></span> <span data-ttu-id="85dc1-123">Se você não conseguir localizar a configuração no repositório global, siga as etapas em [Criar e carregar uma nova versão de uma configuração de relatório eletrônico (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="85dc1-123">If you can't find the configuration in the Global repository, follow the steps in [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

## <a name="share-er-configurations-with-external-organizations"></a><span data-ttu-id="85dc1-124">Compartilhar configurações de ER com organizações externas</span><span class="sxs-lookup"><span data-stu-id="85dc1-124">Share ER configurations with external organizations</span></span>

<span data-ttu-id="85dc1-125">Depois que uma configuração é criada no provedor de configuração, você pode compartilhá-la diretamente com as organizações externas usando a Guia Rápida **Compartilhado com** na página **Repositório de configuração global**.</span><span class="sxs-lookup"><span data-stu-id="85dc1-125">After a configuration has been created under your configuration provider, you can share it directly with external organizations by using the **Shared with** FastTab on the **Global configuration repository** page.</span></span>

1. <span data-ttu-id="85dc1-126">No espaço de trabalho **Relatório eletrônico**, selecione **Repositórios** para o provedor de configuração.</span><span class="sxs-lookup"><span data-stu-id="85dc1-126">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>
2. <span data-ttu-id="85dc1-127">Selecione **Repositório global** \> **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="85dc1-127">Select **Global repository** \> **Open**.</span></span> 
3. <span data-ttu-id="85dc1-128">Selecionar a configuração que você deseja compartilhar.</span><span class="sxs-lookup"><span data-stu-id="85dc1-128">Select the configuration that you want to share.</span></span>
4. <span data-ttu-id="85dc1-129">Na Guia Rápida **Compartilhado com**, selecione **Organização**.</span><span class="sxs-lookup"><span data-stu-id="85dc1-129">On the **Shared with** FastTab, select **Organization**.</span></span>

    ![Compartilhado com Guia Rápida](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_org.JPG)

5. <span data-ttu-id="85dc1-131">Na caixa de diálogo, insira o nome do domínio para a organização externa e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="85dc1-131">In the dialog box, enter the domain name for the external organization, and then select **OK**.</span></span>

    ![Compartilhar versão de configuração com caixa de diálogo de organização externa](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_form.JPG)

<span data-ttu-id="85dc1-133">A configuração é compartilhada com a organização externa e está disponível para aquela organização no repositório global.</span><span class="sxs-lookup"><span data-stu-id="85dc1-133">The configuration is shared with the external organization and is available to that organization in the Global repository.</span></span> <span data-ttu-id="85dc1-134">A partir daí, ele pode ser importado para a instância da organização do RCS ou para suas instâncias de aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="85dc1-134">From there, it can be imported into the organization's instance of RCS or into its instances of Finance and Operations apps.</span></span>

![Configuração compartilhada com uma organização externa](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_test.com)

6. <span data-ttu-id="85dc1-136">Para cancelar o compartilhamento uma configuração que já tenha sido compartilhada com uma organização externa, selecione a configuração e clique em **Cancelar compartilhamento** e selecione **OK**</span><span class="sxs-lookup"><span data-stu-id="85dc1-136">To unshare a configuration that has been previously shared with an external organization, select the configuration and click **Unshare**, and then select **OK**</span></span>