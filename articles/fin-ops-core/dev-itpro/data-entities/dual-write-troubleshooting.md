---
title: Guia de solução de problemas para integração de dados
description: Este tópico fornece informações de solução de problemas para a integração de dados entre aplicativos do Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: c16268338085d414468f17362294fb7e933d1b57
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249100"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="22961-103">Guia de solução de problemas para integração de dados</span><span class="sxs-lookup"><span data-stu-id="22961-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a><span data-ttu-id="22961-104">Habilite o rastreamento de plug-in no Common Data Service e inspecione os detalhes de erro do plug-in de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="22961-104">Enable plug-in trace logs in Common Data Service and inspect the dual-write plug-in error details</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="22961-105">Se você tiver um problema ou erro durante a sincronização de gravação dupla, siga estas etapas para inspecionar os erros no log de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="22961-105">If you experience an issue or error during dual-write synchronization, follow these steps to inspect the errors in the trace log.</span></span>

1. <span data-ttu-id="22961-106">Antes de poder inspecionar os erros, você deve ativar os logs de rastreamento de plug-in.</span><span class="sxs-lookup"><span data-stu-id="22961-106">Before you can inspect the errors, you must enable plug-in trace logs.</span></span> <span data-ttu-id="22961-107">Para obter instruções, consulte a seção "Exibir logs de rastreamento" do [Tutorial: crie e registre um plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span><span class="sxs-lookup"><span data-stu-id="22961-107">For instructions, see the "View trace logs" section of [Tutorial: Write and register a plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).</span></span>

    <span data-ttu-id="22961-108">Agora você pode inspecionar os erros.</span><span class="sxs-lookup"><span data-stu-id="22961-108">You can now inspect the errors.</span></span>

2. <span data-ttu-id="22961-109">Entre no Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="22961-109">Sign in to Microsoft Dynamics 365 Sales.</span></span>
3. <span data-ttu-id="22961-110">Selecione o botão **Configurações** (o símbolo da engrenagem) e selecione **Configurações Avançadas**.</span><span class="sxs-lookup"><span data-stu-id="22961-110">Select the **Settings** button (the gear symbol), and then select **Advanced Settings**.</span></span>
4. <span data-ttu-id="22961-111">No menu **Configurações**, selecione **Personalização \> Log de Rastreamento de Plug-In**.</span><span class="sxs-lookup"><span data-stu-id="22961-111">On the **Settings** menu, select **Customization \> Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="22961-112">Selecione **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** como o nome do tipo para mostrar os detalhes do erro.</span><span class="sxs-lookup"><span data-stu-id="22961-112">Select **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** as the type name to show the error details.</span></span>

## <a name="inspect-dual-write-synchronization-errors"></a><span data-ttu-id="22961-113">Verificar erros de sincronização de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="22961-113">Inspect dual-write synchronization errors</span></span>

<span data-ttu-id="22961-114">Siga estas etapas para inspecionar erros durante o teste.</span><span class="sxs-lookup"><span data-stu-id="22961-114">Follow these steps to inspect errors during testing.</span></span>

1. <span data-ttu-id="22961-115">Entre Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="22961-115">Sign in to Microsoft Dynamics Lifecycle Services (LCS).</span></span>
2. <span data-ttu-id="22961-116">Abra o projeto do LCS que será submetido a testes de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="22961-116">Open the LCS project to do dual-write testing for.</span></span>
3. <span data-ttu-id="22961-117">Selecione **Ambientes hospedados na nuvem**.</span><span class="sxs-lookup"><span data-stu-id="22961-117">Select **Cloud-hosted environments**.</span></span>
4. <span data-ttu-id="22961-118">Estabeleça uma conexão de área de trabalho remota com a máquina virtual (VM) do aplicativo usando uma conta local que é mostrada no LCS.</span><span class="sxs-lookup"><span data-stu-id="22961-118">Make a Remote desktop connection to the application virtual machine (VM) by using local account that is shown in LCS.</span></span>
5. <span data-ttu-id="22961-119">Abra o Visualizador de Eventos.</span><span class="sxs-lookup"><span data-stu-id="22961-119">Open Event Viewer.</span></span> 
6. <span data-ttu-id="22961-120">Vá para **Registros de aplicativos e serviços \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.</span><span class="sxs-lookup"><span data-stu-id="22961-120">Go to **Applications and Services Logs \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operational**.</span></span> <span data-ttu-id="22961-121">Os erros e os detalhes são exibidos.</span><span class="sxs-lookup"><span data-stu-id="22961-121">The errors and details are shown.</span></span>

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a><span data-ttu-id="22961-122">Desvincular um ambiente do Common Data Service do aplicativo e vincular outro ambiente</span><span class="sxs-lookup"><span data-stu-id="22961-122">Unlink one Common Data Service environment from the application and link another environment</span></span>

<span data-ttu-id="22961-123">Siga as etapas a seguir para atualizar os links.</span><span class="sxs-lookup"><span data-stu-id="22961-123">Follow these steps to update links.</span></span>

1. <span data-ttu-id="22961-124">Vá para o ambiente do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="22961-124">Go to the application environment.</span></span>
2. <span data-ttu-id="22961-125">Abra o Gerenciamento de Dados.</span><span class="sxs-lookup"><span data-stu-id="22961-125">Open Data Management.</span></span>
3. <span data-ttu-id="22961-126">Selecione **Link para o CDS para aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="22961-126">Select **Link to CDS for apps**.</span></span>
4. <span data-ttu-id="22961-127">Selecione todos os mapeamentos em execução e depois **Parar**.</span><span class="sxs-lookup"><span data-stu-id="22961-127">Select all the mappings that are running, and then select **Stop**.</span></span>
5. <span data-ttu-id="22961-128">Selecione todos os mapeamentos e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="22961-128">Select all the mappings, and then select **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="22961-129">A opção **Excluir** não estará disponível se o modelo **CustomerV3-Account** estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="22961-129">The **Delete** option isn't available if the **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="22961-130">Limpe a seleção desse modelo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="22961-130">Clear the selection of this template as required.</span></span> <span data-ttu-id="22961-131">**CustomerV3-Account** é um modelo provisionado mais antigo e funciona com a solução Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="22961-131">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="22961-132">Como ele é liberado globalmente, aparece em todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="22961-132">Because it's globally released, it appears under all templates.</span></span>

6. <span data-ttu-id="22961-133">Selecione **Desvincular ambiente**.</span><span class="sxs-lookup"><span data-stu-id="22961-133">Select **Unlink environment**.</span></span>
7. <span data-ttu-id="22961-134">Selecione **Sim** para confirmar a operação.</span><span class="sxs-lookup"><span data-stu-id="22961-134">Select **Yes** to confirm the operation.</span></span>
8. <span data-ttu-id="22961-135">Para vincular o novo ambiente, siga as etapas do [guia de instalação](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="22961-135">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>
