---
title: Configurar o SQL Server Reporting Services para implantações locais
description: Este tópico fornece informações sobre como configurar o SQL Server Reporting Services (SSRS) para uma implantação local.
author: PeterRFriis
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: peterfriis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: cc8bb6c3a993274f70316145f2ec8a6217e6886c
ms.sourcegitcommit: d7c18228256daeefbf6518c3ef82fed4f7dbc161
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5571695"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a><span data-ttu-id="d0a40-103">Configurar o SQL Server Reporting Services para implantações locais</span><span class="sxs-lookup"><span data-stu-id="d0a40-103">Configure SQL Server Reporting Services for on-premises deployments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0a40-104">Siga as etapas deste tópico para configurar o SSRS (SQL Server Reporting Services) para sua implantação do Microsoft Dynamics 365 Finance + Operations (local).</span><span class="sxs-lookup"><span data-stu-id="d0a40-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 Finance + Operations (on-premises) deployment.</span></span>

1. <span data-ttu-id="d0a40-105">Abra o aplicativo Gerenciador de configuração dos serviços de relatório.</span><span class="sxs-lookup"><span data-stu-id="d0a40-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="d0a40-106">Deixe o **Nome do servidor** padrão, que deve ser o nome da máquina atual, e a **Instância do servidor de relatório**, **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span>
3. <span data-ttu-id="d0a40-107">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-107">Click **Connect**.</span></span>

    <span data-ttu-id="d0a40-108">[![Conexão de configuração dos serviços de relatório](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>

4. <span data-ttu-id="d0a40-109">Clique na guia **Conta de serviços** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="d0a40-110">[![Guia de conta de serviços](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>

5. <span data-ttu-id="d0a40-111">Clique na guia **URL de Serviço Web** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="d0a40-112">[![Guia da URL do serviço Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span>

6. <span data-ttu-id="d0a40-113">Clique na guia **Banco de dados** e verifique se o **Nome do banco de dados** e as **Configurações credenciais** correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0a40-114">Será necessário criar um novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d0a40-114">You will need to create a new database.</span></span> <span data-ttu-id="d0a40-115">Para fazê-lo, clique em **Alterar Banco de Dados** e depois verifique se o nome do novo banco de dados é: **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="d0a40-116">[![Guia de banco de dados](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>

7. <span data-ttu-id="d0a40-117">Clique na guia **URL do Portal Web** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0a40-118">Você deve clicar em **Aplicar** para criar e configurar adequadamente o portal.</span><span class="sxs-lookup"><span data-stu-id="d0a40-118">You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="d0a40-119">[![Guia da URL do Portal Web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>

    <span data-ttu-id="d0a40-120">Após a configuração do portal, a guia **Portal da Web** corresponderá ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>

    <span data-ttu-id="d0a40-121">[![guia do portal web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>

8. <span data-ttu-id="d0a40-122">Clique na URL dos relatórios para exibir o portal Web SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d0a40-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span>
9. <span data-ttu-id="d0a40-123">Quando estiver no portal, crie uma pasta nomeada **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="d0a40-124">[![pasta do Dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>

10. <span data-ttu-id="d0a40-125">No **Gerenciador de configuração dos serviços de relatório**, clique na guia **Configurações de Email** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="d0a40-126">[![guia de configurações de email](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>

11. <span data-ttu-id="d0a40-127">Clique na guia **Conta de execução** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="d0a40-128">[![guia da conta de execução](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>

    <span data-ttu-id="d0a40-129">Não altere as configurações padrão na guia **Chaves de Criptografia**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-129">Don't change the default settings on the **Encryption Keys** tab.</span></span>

    <span data-ttu-id="d0a40-130">[![guia de chaves de criptografia](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-130">[![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>

12. <span data-ttu-id="d0a40-131">Clique na guia **Configurações da assinatura** e verifique se as configurações correspondem ao gráfico a seguir.</span><span class="sxs-lookup"><span data-stu-id="d0a40-131">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="d0a40-132">[![guia de configurações da assinatura](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-132">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>

    <span data-ttu-id="d0a40-133">Não altere as configurações padrão na guia **Implantação em Expansão**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-133">Don't change the default settings on the **Scale-out Deployment** tab.</span></span>

    <span data-ttu-id="d0a40-134">[![guia de implantação em expansão](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-134">[![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>

    <span data-ttu-id="d0a40-135">Não altere as configurações padrão na guia **Integração do Power BI**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-135">Don't change the default settings on the **Power BI Integration** tab.</span></span>

    <span data-ttu-id="d0a40-136">[![guia de integração do power bi](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-136">[![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span>

13. <span data-ttu-id="d0a40-137">Clique em **Sair** para fechar o **Gerenciador de configuração dos serviços de relatório**.</span><span class="sxs-lookup"><span data-stu-id="d0a40-137">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="d0a40-138">[![fechar o gerenciador de configuração dos serviços de relatório](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="d0a40-138">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
