---
title: Baixar configurações do Relatório eletrônico no Lifecycle Services
description: Este tópico explica como baixar configurações de ER (relatório eletrônico) do Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8aaa3be426c0321da7e72d6acc18918d8b0ecee2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570361"
---
# <a name="download-electronic-reporting-configurations-from-lifecycle-services"></a><span data-ttu-id="699aa-103">Baixar configurações de Relatório eletrônico do Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="699aa-103">Download Electronic reporting configurations from Lifecycle Services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="699aa-104">Este tópico explica como baixar a versão mais recente das [configurações de relatório eletrônico (ER)](general-electronic-reporting.md#Configuration) da [biblioteca de ativos compartilhados](../lifecycle-services/asset-library.md) no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="699aa-104">This topic explains how to download the newest version of [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the [Shared asset library](../lifecycle-services/asset-library.md) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="699aa-105">Entre no aplicativo usando uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="699aa-105">Sign in to the application by using one of the following roles:</span></span>

    - <span data-ttu-id="699aa-106">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="699aa-106">Electronic reporting developer</span></span>
    - <span data-ttu-id="699aa-107">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="699aa-107">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="699aa-108">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="699aa-108">System administrator</span></span>

2. <span data-ttu-id="699aa-109">Vá para **Administração da organização** &gt; **Espaços de trabalho** &gt; **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="699aa-109">Go to **Organization administration** &gt; **Workspaces** &gt; **Electronic reporting**.</span></span>
3. <span data-ttu-id="699aa-110">Na seção **Provedores de configuração**, selecione o bloco **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="699aa-110">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
4. <span data-ttu-id="699aa-111">No bloco **Microsoft**, selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="699aa-111">On the **Microsoft** tile, select **Repositories**.</span></span>

    <span data-ttu-id="699aa-112">[![Bloco da Microsoft na página Configurações de localização](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span><span class="sxs-lookup"><span data-stu-id="699aa-112">[![Microsoft tile on the Localization configurations page](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)](./media/update-er-from-lcs-for-ms-open-ms-repositories-list.png)</span></span>

5. <span data-ttu-id="699aa-113">Na página **Repositórios de configuração**, na grade, selecione o repositório existente do tipo **LCS**.</span><span class="sxs-lookup"><span data-stu-id="699aa-113">On the **Configuration repositories** page, in the grid, select the existing repository of the **LCS** type.</span></span> <span data-ttu-id="699aa-114">Se esse repositório não aparecer na grade, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="699aa-114">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="699aa-115">Selecione **Adicionar** para adicionar um repositório.</span><span class="sxs-lookup"><span data-stu-id="699aa-115">Select **Add** to add a repository.</span></span>
    2. <span data-ttu-id="699aa-116">Selecione **LCS** como tipo de repositório.</span><span class="sxs-lookup"><span data-stu-id="699aa-116">Select **LCS** as the repository type.</span></span>
    3. <span data-ttu-id="699aa-117">Selecione **Criar repositório**.</span><span class="sxs-lookup"><span data-stu-id="699aa-117">Select **Create repository**.</span></span>
    4. <span data-ttu-id="699aa-118">Se você for solicitado sobre autorização, siga as instruções na tela.</span><span class="sxs-lookup"><span data-stu-id="699aa-118">If you're prompted about authorization, follow the on-screen instructions.</span></span>
    5. <span data-ttu-id="699aa-119">Insira um nome e uma descrição para o repositório.</span><span class="sxs-lookup"><span data-stu-id="699aa-119">Enter a name and description for the repository.</span></span>
    6. <span data-ttu-id="699aa-120">Selecione **OK** para confirmar a nova entrada do repositório.</span><span class="sxs-lookup"><span data-stu-id="699aa-120">Select **OK** to confirm the new repository entry.</span></span>
    7. <span data-ttu-id="699aa-121">Na grade, selecione o novo repositório do tipo **LCS**.</span><span class="sxs-lookup"><span data-stu-id="699aa-121">In the grid, select the new repository of the **LCS** type.</span></span>

6. <span data-ttu-id="699aa-122">Selecione **Abrir** para exibir a lista de configurações de ER para o repositório selecionado.</span><span class="sxs-lookup"><span data-stu-id="699aa-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    <span data-ttu-id="699aa-123">[![Página Repositórios de configuração](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span><span class="sxs-lookup"><span data-stu-id="699aa-123">[![Configuration repositories page](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)](./media/update-er-from-lcs-for-ms-make-lcs-repository.png)</span></span>

    > [!TIP]
    > <span data-ttu-id="699aa-124">Se você tiver problemas ao acessar o repositório LCS para baixar configurações da biblioteca de ativos compartilhados no LCS, poderá baixar configurações do [Repositório global](er-download-configurations-global-repo.md).</span><span class="sxs-lookup"><span data-stu-id="699aa-124">If you have trouble accessing the LCS repository to download configurations from the Shared asset library in LCS, you can download configurations from the [Global repository](er-download-configurations-global-repo.md) instead.</span></span>

7. <span data-ttu-id="699aa-125">Na árvore de configurações, no painel esquerdo, selecione a configuração ER necessária.</span><span class="sxs-lookup"><span data-stu-id="699aa-125">In the configurations tree in the left pane, select the required ER configuration.</span></span>
8. <span data-ttu-id="699aa-126">Na Guia Rápida **Versões**, selecione a versão necessária da configuração de ER selecionada.</span><span class="sxs-lookup"><span data-stu-id="699aa-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
9. <span data-ttu-id="699aa-127">Selecione **Importar** para baixar a versão selecionada do LCS para a instância atual.</span><span class="sxs-lookup"><span data-stu-id="699aa-127">Select **Import** to download the selected version from LCS to the current instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="699aa-128">O botão **Importar** não está disponível para as versões de configuração do ER que já estão presentes na instância atual.</span><span class="sxs-lookup"><span data-stu-id="699aa-128">The **Import** button is unavailable for ER configuration versions that are already present in the current instance.</span></span>

    <span data-ttu-id="699aa-129">[![Página do repositório de configuração](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="699aa-129">[![Configuration repository page](./media/update-er-from-lcs-for-ms-download-configuration.png)](./media/update-er-from-lcs-for-ms-download-configuration.png)</span></span>

> [!NOTE]
> <span data-ttu-id="699aa-130">Dependendo das configurações de ER, as configurações são validadas depois que são importadas.</span><span class="sxs-lookup"><span data-stu-id="699aa-130">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="699aa-131">Talvez você seja notificado sobre problemas de inconsistências descobertos.</span><span class="sxs-lookup"><span data-stu-id="699aa-131">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="699aa-132">Você deve resolver esses problemas para que possa usar a versão de configuração importada.</span><span class="sxs-lookup"><span data-stu-id="699aa-132">You must resolve those issues before you can use the imported configuration version.</span></span> <span data-ttu-id="699aa-133">Para obter mais informações, consulte a lista de tópicos relacionados deste tópico.</span><span class="sxs-lookup"><span data-stu-id="699aa-133">For more information, see the list of related topics for this topic.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="699aa-134">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="699aa-134">Additional resources</span></span>

[<span data-ttu-id="699aa-135">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="699aa-135">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="699aa-136">Baixar configurações ER do repositório global de serviço de configuração</span><span class="sxs-lookup"><span data-stu-id="699aa-136">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]