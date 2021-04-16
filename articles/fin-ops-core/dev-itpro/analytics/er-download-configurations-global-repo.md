---
title: Baixar configurações ER do repositório global de serviço de configuração
description: Este tópico explica como baixar as configurações de relatório eletrônico (ER) do repositório global do serviço de configuração.
author: NickSelin
ms.date: 06/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 3a232cd319970e572580bc11f2dbaccbe208f127
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753375"
---
# <a name="download-er-configurations-from-the-global-repository-of-configuration-service"></a><span data-ttu-id="518db-103">Baixar configurações ER do repositório global de serviço de configuração</span><span class="sxs-lookup"><span data-stu-id="518db-103">Download ER configurations from the Global repository of Configuration service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="518db-104">Este tópico explica como baixar as [configurações de relatório eletrônico (ER)](general-electronic-reporting.md#Configuration) do repositório global do serviço de configuração.</span><span class="sxs-lookup"><span data-stu-id="518db-104">This topic explains how to download [Electronic reporting (ER) configurations](general-electronic-reporting.md#Configuration) from the Global repository of configuration service.</span></span> <span data-ttu-id="518db-105">Para obter mais informações, consulte [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, serviço de configuração](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="518db-105">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="open-configurations-repository"></a><span data-ttu-id="518db-106">Abra o repositório de configurações</span><span class="sxs-lookup"><span data-stu-id="518db-106">Open configurations repository</span></span>

1. <span data-ttu-id="518db-107">Entre no aplicativo Dynamics 365 Finance usando uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="518db-107">Sign in to the Dynamics 365 Finance application using one of the following roles:</span></span>

    - <span data-ttu-id="518db-108">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="518db-108">Electronic reporting developer</span></span>
    - <span data-ttu-id="518db-109">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="518db-109">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="518db-110">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="518db-110">System administrator</span></span>

2. <span data-ttu-id="518db-111">Vá par **Administração da organização > Espaços de trabalho > Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="518db-111">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="518db-112">Na seção **Provedores de configuração**, selecione o bloco **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="518db-112">In the **Configuration providers** section, select the **Microsoft** tile.</span></span>
3. <span data-ttu-id="518db-113">No bloco **Microsoft**, selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="518db-113">On the **Microsoft** tile, select **Repositories**.</span></span>

    ![Espaço de trabalho de relatório eletrônico](./media/er-download-configurations-global-repo-er-workspace.png)

4. <span data-ttu-id="518db-115">Na página **Repositórios de configuração**, na grade, selecione o repositório existente do tipo **Global**.</span><span class="sxs-lookup"><span data-stu-id="518db-115">On the **Configuration repositories** page, in the grid, select the existing repository of the **Global** type.</span></span> <span data-ttu-id="518db-116">Se esse repositório não aparecer na grade, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="518db-116">If this repository doesn't appear in the grid, follow these steps:</span></span>

    1. <span data-ttu-id="518db-117">Selecione **Adicionar** para adicionar um novo repositório.</span><span class="sxs-lookup"><span data-stu-id="518db-117">Select **Add** to add a new repository.</span></span>
    2. <span data-ttu-id="518db-118">Selecione **Global** como o tipo de repositório e, em seguida, selecione **Criar repositório**.</span><span class="sxs-lookup"><span data-stu-id="518db-118">Select **Global** as the repository type, and then select **Create repository**.</span></span>
    3. <span data-ttu-id="518db-119">Se solicitado, siga as instruções de autorização.</span><span class="sxs-lookup"><span data-stu-id="518db-119">If prompted, follow the authorization instructions.</span></span>
    4. <span data-ttu-id="518db-120">Insira um nome e uma descrição para o repositório e, em seguida, selecione **OK** para confirmar a nova entrada de repositório.</span><span class="sxs-lookup"><span data-stu-id="518db-120">Enter a name and description for the repository and then select **OK** to confirm the new repository entry.</span></span>
    5. <span data-ttu-id="518db-121">Na grade, selecione o novo repositório do tipo **Global**.</span><span class="sxs-lookup"><span data-stu-id="518db-121">In the grid, select the new repository of the **Global** type.</span></span>

5. <span data-ttu-id="518db-122">Selecione **Abrir** para exibir a lista de configurações de ER para o repositório selecionado.</span><span class="sxs-lookup"><span data-stu-id="518db-122">Select **Open** to view the list of ER configurations for the selected repository.</span></span>

    ![Página Repositórios de configuração](./media/er-download-configurations-global-repo-repositories-list.png)

## <a name="import-a-single-configuration"></a><span data-ttu-id="518db-124">Importar uma única configuração</span><span class="sxs-lookup"><span data-stu-id="518db-124">Import a single configuration</span></span>

1. <span data-ttu-id="518db-125">Na página **Repositórios de configuração**, na árvore de configurações, selecione a configuração ER desejada.</span><span class="sxs-lookup"><span data-stu-id="518db-125">On the **Configuration repositories** page, in the configurations tree, select the ER configuration that you want.</span></span>
2. <span data-ttu-id="518db-126">Na Guia Rápida **Versões**, selecione a versão necessária da configuração de ER selecionada.</span><span class="sxs-lookup"><span data-stu-id="518db-126">On the **Versions** FastTab, select the required version of the selected ER configuration.</span></span>
3. <span data-ttu-id="518db-127">Selecione **Importar** para baixar a versão selecionada do repositório global para a instância atual do Finance.</span><span class="sxs-lookup"><span data-stu-id="518db-127">Select **Import** to download the selected version from Global repository to the current Finance instance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="518db-128">O botão **Importar** não está disponível para as versões de configuração do ER que já estão presentes na instância atual do Finance.</span><span class="sxs-lookup"><span data-stu-id="518db-128">The **Import** button is unavailable for ER configuration versions that are already present in the current Finance instance.</span></span>

    ![Página do repositório de configuração](./media/er-download-configurations-global-repo-repository-content.png)

## <a name="import-filtered-configurations"></a><span data-ttu-id="518db-130">Importar configurações filtradas</span><span class="sxs-lookup"><span data-stu-id="518db-130">Import filtered configurations</span></span>

1. <span data-ttu-id="518db-131">Na página **Repositórios de configuração**, na árvore configurações, expanda a FastTab **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="518db-131">On the **Configuration repositories** page, in the configurations tree, expand the **Filter** FastTab.</span></span>
2. <span data-ttu-id="518db-132">Na grade **Marcas**, adicione as marcas necessárias.</span><span class="sxs-lookup"><span data-stu-id="518db-132">In the **Tags** grid, add any tags that are needed.</span></span>
3. <span data-ttu-id="518db-133">No campo **Aplicabilidade de país/região**, selecione os códigos de país/região adequados e selecione **Aplicar filtro**.</span><span class="sxs-lookup"><span data-stu-id="518db-133">In the **Country/region applicability** field, select the appropriate country/region codes, and then select  **Apply filter**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="518db-134">A FastTab **Configurações** mostra todas as configurações que atendem às condições de seleção especificadas.</span><span class="sxs-lookup"><span data-stu-id="518db-134">The **Configurations** FastTab shows all the configurations that satisfy the specified selection conditions.</span></span>

4. <span data-ttu-id="518db-135">Na FastTab **Configurações**, selecione **Importar** para baixar as configurações filtradas do repositório global para a instância atual.</span><span class="sxs-lookup"><span data-stu-id="518db-135">On the **Configurations** FastTab, select **Import** to download the filtered configurations from the Global repository to the current instance.</span></span>
5. <span data-ttu-id="518db-136">Na guia **Configurações**, selecione **Redefinir filtro** para limpar as condições de seleção especificadas.</span><span class="sxs-lookup"><span data-stu-id="518db-136">On the **Configurations** FastTab, select **Reset filter** to clean up the specified selection conditions.</span></span>

    ![Página do repositório de configuração](./media/er-download-configurations-global-repo-filtered-configurations.png)

> [!NOTE]
> <span data-ttu-id="518db-138">Dependendo das configurações de ER, as configurações são validadas depois que são importadas.</span><span class="sxs-lookup"><span data-stu-id="518db-138">Depending on the ER settings, configurations are validated after they are imported.</span></span> <span data-ttu-id="518db-139">Talvez você seja notificado sobre problemas de inconsistências descobertos.</span><span class="sxs-lookup"><span data-stu-id="518db-139">You might be notified about any inconsistency issues that are discovered.</span></span> <span data-ttu-id="518db-140">Antes de poder usar a versão de configuração importada, você precisa resolver os problemas.</span><span class="sxs-lookup"><span data-stu-id="518db-140">Before you can use the imported configuration version, you must resolve the issues.</span></span> <span data-ttu-id="518db-141">Para obter mais informações, consulte a lista de recursos relacionados deste tópico.</span><span class="sxs-lookup"><span data-stu-id="518db-141">For more information, see the list of related resources for this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="518db-142">As configurações de ER podem ser definidas como dependentes de outras configurações.</span><span class="sxs-lookup"><span data-stu-id="518db-142">ER configurations can be configured as being dependent on other configurations.</span></span> <span data-ttu-id="518db-143">Portanto, juntamente com uma configuração selecionada, outras configurações podem ser importadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="518db-143">Therefore, along with a selected configuration, other configurations might be automatically imported.</span></span> <span data-ttu-id="518db-144">Para saber mais sobre dependências de configuração, consulte [Definir a dependência de configurações do ER em outros componentes](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span><span class="sxs-lookup"><span data-stu-id="518db-144">For more about configuration dependencies, see [Define the dependency of ER configurations on other components](tasks/er-define-dependency-er-configurations-from-other-components-july-2017.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="518db-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="518db-145">Additional resources</span></span>

[<span data-ttu-id="518db-146">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="518db-146">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]