---
title: Configurar o SQL Server Reporting Services para implantações locais
description: Este tópico fornece informações sobre como configurar o SQL Server Reporting Services (SSRS) para uma implantação local.
author: PeterRFriis
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: perahlff
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 2577705b04beef1f8b03f83ed8536be2e6ab6e83
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683912"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a><span data-ttu-id="dc19c-103">Configurar o SQL Server Reporting Services para implantações locais</span><span class="sxs-lookup"><span data-stu-id="dc19c-103">Configure SQL Server Reporting Services for on-premises deployments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc19c-104">Siga as etapas deste tópico para configurar o SSRS (SQL Server Reporting Services) para sua implantação do Microsoft Dynamics 365 Finance + Operations (local).</span><span class="sxs-lookup"><span data-stu-id="dc19c-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 Finance + Operations (on-premises) deployment.</span></span>

1. <span data-ttu-id="dc19c-105">Abra o aplicativo Gerenciador de configuração dos serviços de relatório.</span><span class="sxs-lookup"><span data-stu-id="dc19c-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="dc19c-106">Deixe o **Nome do servidor** padrão, que deve ser o nome da máquina atual, e a **Instância do servidor de relatório**, **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span>
3. <span data-ttu-id="dc19c-107">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-107">Click **Connect**.</span></span>

    <span data-ttu-id="dc19c-108">[![Conexão de configuração dos serviços de relatório](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>

4. <span data-ttu-id="dc19c-109">Clique na guia **Conta de serviços** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="dc19c-110">[![Guia de conta de serviços](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>

5. <span data-ttu-id="dc19c-111">Clique na guia **URL de Serviço Web** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="dc19c-112">[![Guia da URL do serviço Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span>

6. <span data-ttu-id="dc19c-113">Clique na guia **Banco de dados** e verifique se o **Nome do banco de dados** e as **Configurações credenciais** correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc19c-114">Será necessário criar um novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="dc19c-114">You will need to create a new database.</span></span> <span data-ttu-id="dc19c-115">Para fazê-lo, clique em **Alterar Banco de Dados** e depois verifique se o nome do novo banco de dados é: **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="dc19c-116">[![Guia de banco de dados](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>

7. <span data-ttu-id="dc19c-117">Clique na guia **URL do Portal Web** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc19c-118">Você deve clicar em **Aplicar** para criar e configurar adequadamente o portal.</span><span class="sxs-lookup"><span data-stu-id="dc19c-118">You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="dc19c-119">[![Guia da URL do Portal Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>

    <span data-ttu-id="dc19c-120">Após a configuração do portal, a guia **Portal da Web** corresponderá ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>

    <span data-ttu-id="dc19c-121">[![guia do portal web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>

8. <span data-ttu-id="dc19c-122">Clique na URL dos relatórios para exibir o portal Web SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dc19c-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span>
9. <span data-ttu-id="dc19c-123">Quando estiver no portal, crie uma pasta nomeada **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="dc19c-124">[![pasta do Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>

10. <span data-ttu-id="dc19c-125">No **Gerenciador de configuração dos serviços de relatório**, clique na guia **Configurações de Email** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="dc19c-126">[![guia de configurações de email](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>

11. <span data-ttu-id="dc19c-127">Clique na guia **Conta de execução** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="dc19c-128">[![guia da conta de execução](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>

    <span data-ttu-id="dc19c-129">Não altere as configurações padrão na guia **Chaves de Criptografia**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-129">Don't change the default settings on the **Encryption Keys** tab.</span></span>

    <span data-ttu-id="dc19c-130">[![guia de chaves de criptografia](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-130">[![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>

12. <span data-ttu-id="dc19c-131">Clique na guia **Configurações da assinatura** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc19c-131">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="dc19c-132">[![guia de configurações da assinatura](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-132">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>

    <span data-ttu-id="dc19c-133">Não altere as configurações padrão na guia **Implantação em Expansão**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-133">Don't change the default settings on the **Scale-out Deployment** tab.</span></span>

    <span data-ttu-id="dc19c-134">[![guia de implantação em expansão](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-134">[![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>

    <span data-ttu-id="dc19c-135">Não altere as configurações padrão na guia **Integração do Power BI**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-135">Don't change the default settings on the **Power BI Integration** tab.</span></span>

    <span data-ttu-id="dc19c-136">[![guia de integração do power bi](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-136">[![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span>

13. <span data-ttu-id="dc19c-137">Clique em **Sair** para fechar o **Gerenciador de configuração dos serviços de relatório**.</span><span class="sxs-lookup"><span data-stu-id="dc19c-137">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="dc19c-138">[![fechar o gerenciador de configuração dos serviços de relatório](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="dc19c-138">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
