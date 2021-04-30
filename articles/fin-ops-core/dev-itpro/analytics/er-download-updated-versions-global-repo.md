---
title: Importar versões atualizadas de configurações de ER
description: Este tópico explica como importar versões atualizadas das configurações de relatório eletrônico (ER) do repositório global do serviço de configuração.
author: NickSelin
ms.date: 06/09/2020
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
ms.openlocfilehash: 724048991fc8864ef72a5155af66b9c709f4b875
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893947"
---
# <a name="import-updated-versions-of-er-configurations"></a><span data-ttu-id="25d10-103">Importar versões atualizadas de configurações de ER</span><span class="sxs-lookup"><span data-stu-id="25d10-103">Import updated versions of ER configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25d10-104">Os [repositórios](general-electronic-reporting.md#Repository) de relatórios eletrônicos (ER) são usados para compartilhar [configurações de ER](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="25d10-104">Electronic reporting (ER) [repositories](general-electronic-reporting.md#Repository) are used to share [ER configurations](general-electronic-reporting.md#Configuration).</span></span> <span data-ttu-id="25d10-105">Você pode [importar](download-electronic-reporting-configuration-lcs.md) configurações de ER de diferentes repositórios para sua instância do Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="25d10-105">You can [import](download-electronic-reporting-configuration-lcs.md) ER configurations from different repositories into your instance of Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="25d10-106">Quando você importa configurações de ER, os [provedores de configuração](general-electronic-reporting.md#Provider) podem publicar novos repositórios de [versões](general-electronic-reporting.md#component-versioning) para que eles sejam compartilhados.</span><span class="sxs-lookup"><span data-stu-id="25d10-106">When you import ER configurations, [configuration providers](general-electronic-reporting.md#Provider) can publish new [versions](general-electronic-reporting.md#component-versioning) repositories so that they can be shared.</span></span>

<span data-ttu-id="25d10-107">Este tópico explica como importar versões atualizadas de configurações de ER do repositório global do serviço de configuração.</span><span class="sxs-lookup"><span data-stu-id="25d10-107">This topic explains how to import updated versions of ER configurations from the Global repository of the Configuration service.</span></span> <span data-ttu-id="25d10-108">Para obter mais informações, consulte [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, serviço de configuração](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="25d10-108">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="review-the-available-updated-versions"></a><span data-ttu-id="25d10-109">Examinar as versões atualizadas disponíveis</span><span class="sxs-lookup"><span data-stu-id="25d10-109">Review the available updated versions</span></span>

1. <span data-ttu-id="25d10-110">Entre no Finance usando uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="25d10-110">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="25d10-111">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="25d10-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="25d10-112">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="25d10-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="25d10-113">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="25d10-113">System administrator</span></span>

2. <span data-ttu-id="25d10-114">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="25d10-114">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="25d10-115">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Importar atualizações de versões de configurações**.</span><span class="sxs-lookup"><span data-stu-id="25d10-115">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>

    ![Página Configurações de localização](./media/er-download-updated-versions-global-repo1.png)

4. <span data-ttu-id="25d10-117">Na caixa de diálogo **Importar atualizações de versões de configurações de relatório eletrônico**, no campo **Modo de execução**, selecione **Mostrar somente as atualizações disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="25d10-117">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Only show available updates**.</span></span> <span data-ttu-id="25d10-118">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="25d10-118">Then select **OK**.</span></span> 

    ![Campo de modo de execução definido como Mostrar somente as atualizações disponíveis](./media/er-download-updated-versions-global-repo2.png)

5. <span data-ttu-id="25d10-120">Examine as mensagens recebidas.</span><span class="sxs-lookup"><span data-stu-id="25d10-120">Review the messages that you receive.</span></span> <span data-ttu-id="25d10-121">Essas mensagens fornecem as seguintes informações sobre as configurações de ER na instância atual do Finance e uma comparação com o conteúdo do repositório global:</span><span class="sxs-lookup"><span data-stu-id="25d10-121">These messages provide the following information about the ER configurations in the current Finance instance and how they compare to the content of the Global repository:</span></span>

    - <span data-ttu-id="25d10-122">O número total de configurações de ER</span><span class="sxs-lookup"><span data-stu-id="25d10-122">The total number of ER configurations</span></span>
    - <span data-ttu-id="25d10-123">As configurações de ER que não estão presentes no repositório global</span><span class="sxs-lookup"><span data-stu-id="25d10-123">ER configurations that aren't present in the Global repository</span></span>
    - <span data-ttu-id="25d10-124">As configurações de ER cuja versão mais recente já está disponível na instância atual do Finance (para ver a lista completa dessas configurações de ER, selecione o link **Detalhes da mensagem**.)</span><span class="sxs-lookup"><span data-stu-id="25d10-124">ER configurations for which the latest version is already available in the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Mensagem "As versões mais recentes das configurações a seguir já foram importadas" e detalhes da mensagem](./media/er-download-updated-versions-global-repo3.png)

    - <span data-ttu-id="25d10-126">As configurações de ER cuja versão mais recente está disponível no repositório global e pode ser importada para a instância atual do Finance (para ver a lista completa dessas configurações de ER, selecione o link **Detalhes da mensagem**.)</span><span class="sxs-lookup"><span data-stu-id="25d10-126">ER configurations for which the latest version is available in the Global repository and can be imported into the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Mensagem "Atualizações disponíveis" e detalhes da mensagem](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a><span data-ttu-id="25d10-128">Importar as versões atualizadas disponíveis</span><span class="sxs-lookup"><span data-stu-id="25d10-128">Import available updated versions</span></span>

1. <span data-ttu-id="25d10-129">Entre no Finance usando uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="25d10-129">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="25d10-130">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="25d10-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="25d10-131">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="25d10-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="25d10-132">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="25d10-132">System administrator</span></span>

2. <span data-ttu-id="25d10-133">Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="25d10-133">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="25d10-134">Na página **Configurações de localização**, na seção **Links relacionados**, selecione **Importar atualizações de versões de configurações**.</span><span class="sxs-lookup"><span data-stu-id="25d10-134">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>
4. <span data-ttu-id="25d10-135">Na caixa de diálogo **Importar atualizações de versões de configurações de relatório eletrônico**, no campo **Modo de execução**, selecione **Importar atualizações mais recentes** para importar as versões mais recentes das configurações de ER do repositório global para a instância atual do Finance.</span><span class="sxs-lookup"><span data-stu-id="25d10-135">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Import latest updates** to import the latest versions of ER configurations from the Global repository into the current Finance instance.</span></span>
5. <span data-ttu-id="25d10-136">Para programar um trabalho em lotes para a importação, na FastTab **Executar em segundo plano**, defina a opção **Processamento em lotes** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="25d10-136">To schedule a batch job for the import, on the **Run in the background** FastTab, set the **Batch processing** option to **Yes**.</span></span> <span data-ttu-id="25d10-137">Se quiser repetir a importação periodicamente, configure a recorrência necessária.</span><span class="sxs-lookup"><span data-stu-id="25d10-137">If you want to repeat the import periodically, configure the required recurrence.</span></span>

    ![Campo Modo de execução definido como Importar atualizações mais recentes](./media/er-download-updated-versions-global-repo5.png)

6. <span data-ttu-id="25d10-139">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="25d10-139">Select **OK**.</span></span>
7. <span data-ttu-id="25d10-140">Para saber quais versões de configuração foram importadas, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="25d10-140">To learn what configuration versions have been imported, follow one of these steps:</span></span>

    - <span data-ttu-id="25d10-141">Se você executar a importação interativamente em vez de usar um trabalho em lotes, examine as mensagens recebidas.</span><span class="sxs-lookup"><span data-stu-id="25d10-141">If you run the import interactively instead of using a batch job, review the messages that you receive.</span></span>

        ![Mensagens recebidas durante uma execução de importação interativa](./media/er-download-updated-versions-global-repo6.png)

    - <span data-ttu-id="25d10-143">Se você executar a importação no modo de lotes, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="25d10-143">If you run the import in batch mode, follow these steps:</span></span>

        1. <span data-ttu-id="25d10-144">Vá para **Comum** \> **Consultas** \> **Trabalhos em lotes** \> **Meus trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="25d10-144">Go to **Common** \> **Inquiries** \> **Batch jobs** \> **My batch jobs**.</span></span>
        2. <span data-ttu-id="25d10-145">Encontre e selecione o trabalho **Importar atualizações de versões de configurações de relatório eletrônico** e, no Painel de Ação, na guia **Trabalho em lotes**, selecione **Histórico de trabalho em lotes** para ver o histórico de trabalho.</span><span class="sxs-lookup"><span data-stu-id="25d10-145">Find and select the **Import electronic reporting configurations versions updates** job, and then, on the Action Pane, on the **Batch job** tab, select **Batch job history** to view the job history.</span></span>
        3. <span data-ttu-id="25d10-146">Na página **Histórico de trabalho em lotes**, selecione **Log**.</span><span class="sxs-lookup"><span data-stu-id="25d10-146">On the **Batch job history** page, select **Log**.</span></span> <span data-ttu-id="25d10-147">Em seguida, na mensagem recebida, selecione o link **Detalhes da mensagem** para ver o log do trabalho.</span><span class="sxs-lookup"><span data-stu-id="25d10-147">Then, in the message that you receive, select the **Message details** link to view the job log.</span></span>

        ![Log do trabalho](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> <span data-ttu-id="25d10-149">Não recomendamos agendar um trabalho em lotes recorrente para importar versões atualizadas das configurações de ER diretamente do repositório global para um ambiente de produção, pois as versões importadas estarão disponíveis imediatamente para uso.</span><span class="sxs-lookup"><span data-stu-id="25d10-149">We don't recommend that you schedule a recurring batch job to import updated versions of ER configurations directly from the Global repository into a production environment, because the imported versions will immediately be available for use.</span></span> <span data-ttu-id="25d10-150">Em vez disso, use esta abordagem para implantar versões de configurações de ER em um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="25d10-150">Instead, use this approach to deploy versions of ER configurations to a sandbox environment.</span></span> <span data-ttu-id="25d10-151">Elas poderão ser avaliadas no ambiente de área restrita antes de serem implantadas em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="25d10-151">They can then be evaluated in the sandbox environment before they are deployed to a production environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25d10-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="25d10-152">Additional resources</span></span>

- [<span data-ttu-id="25d10-153">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="25d10-153">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="25d10-154">Baixar configurações ER do repositório global de serviço de configuração</span><span class="sxs-lookup"><span data-stu-id="25d10-154">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]