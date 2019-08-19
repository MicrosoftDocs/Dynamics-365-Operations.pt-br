---
title: Guia de solução de problemas para integração de dados
description: Este tópico fornece informações de solução de problemas para integração de dados entre o Microsoft Dynamics 365 for Finance and Operations e o Common Data Service.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797266"
---
# <a name="troubleshooting-guide-for-data-integration"></a><span data-ttu-id="681f1-103">Guia de solução de problemas para integração de dados</span><span class="sxs-lookup"><span data-stu-id="681f1-103">Troubleshooting guide for data integration</span></span>

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a><span data-ttu-id="681f1-104">Habilite o Rastreamento de Plug-in no Common Data Service e verifique os detalhes de erro do Plug-in de gravação dupla</span><span class="sxs-lookup"><span data-stu-id="681f1-104">Enable Plugin Trace in Common Data Service and check the dual-write Plugin error details</span></span>

<span data-ttu-id="681f1-105">Se estiver enfrentando um problema ou erro de sincronização de gravação dupla, você poderá inspecionar os erros no log de rastreamento:</span><span class="sxs-lookup"><span data-stu-id="681f1-105">If you are facing an issue or error with dual-write synchronization, you can inspect the errors in the trace log:</span></span>

1. <span data-ttu-id="681f1-106">Para poder inspecionar os erros, você deve habilitar o rastreamento de plug-in usando as instruções em [Registrar plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) para habilitar o rastreamento de plug-in.</span><span class="sxs-lookup"><span data-stu-id="681f1-106">Before you can inspect the errors, you must enable Plugin trace using the instructions in [Register plug-in](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) to enable Plugin trace.</span></span> <span data-ttu-id="681f1-107">Agora você pode inspecionar os erros.</span><span class="sxs-lookup"><span data-stu-id="681f1-107">Now you can inspect the errors.</span></span>
2. <span data-ttu-id="681f1-108">Faça logon no Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="681f1-108">Login to Dynamics 365 for Sales.</span></span>
3. <span data-ttu-id="681f1-109">Clique no ícone Configurações (uma engrenagem) e selecione **Configurações Avançadas**.</span><span class="sxs-lookup"><span data-stu-id="681f1-109">Click on the Settings icon (a gear), and select **Advanced Settings**.</span></span>
4. <span data-ttu-id="681f1-110">No menu **Configurações**, escolha **Personalização > Log de Rastreamento de Plug-In**.</span><span class="sxs-lookup"><span data-stu-id="681f1-110">In the **Settings** menu, choose **Customization > Plug-In Trace Log**.</span></span>
5. <span data-ttu-id="681f1-111">Clique no nome do tipo **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** para exibir os detalhes do erro.</span><span class="sxs-lookup"><span data-stu-id="681f1-111">Click the type name **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** to display the error details.</span></span>

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a><span data-ttu-id="681f1-112">Verifique erros de sincronização de gravação dupla no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="681f1-112">Check dual-write synchronization errors in Finance and Operations</span></span>

<span data-ttu-id="681f1-113">Você pode verificar os erros durante os testes seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="681f1-113">You can check the errors during testing by following these steps:</span></span>

+ <span data-ttu-id="681f1-114">Faça logon no Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="681f1-114">Login to LifeCycle Services (LCS).</span></span>
+ <span data-ttu-id="681f1-115">Abra o projeto LCS escolhido para realizar testes de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="681f1-115">Open the LCS project that you chose to perform dual-write testing.</span></span>
+ <span data-ttu-id="681f1-116">Vá para Ambientes Hospedados na Nuvem</span><span class="sxs-lookup"><span data-stu-id="681f1-116">Go to Cloud Hosted Environments.</span></span>
+ <span data-ttu-id="681f1-117">Área de trabalho remota para VM do Finance and Operations usando a conta local que é exibida no LCS.</span><span class="sxs-lookup"><span data-stu-id="681f1-117">Remote desktop to Finance and Operations VM using local account that is displayed in LCS.</span></span>
+ <span data-ttu-id="681f1-118">Abra o visualizador de eventos.</span><span class="sxs-lookup"><span data-stu-id="681f1-118">Open the event viewer.</span></span> 
+ <span data-ttu-id="681f1-119">Navegue para **Logs de Aplicações e Serviços > Microsoft > Dynamics > AX-DualWriteSync > Operacional**.</span><span class="sxs-lookup"><span data-stu-id="681f1-119">Navigate to **Applications and Services logs > Microsoft > Dynamics > AX-DualWriteSync > Operational**.</span></span> <span data-ttu-id="681f1-120">Os erros e os detalhes são exibidos.</span><span class="sxs-lookup"><span data-stu-id="681f1-120">The errors and details are displayed.</span></span>

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a><span data-ttu-id="681f1-121">Como desvincular e vincular outro ambiente do Common Data Service a partir do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="681f1-121">How to unlink and link another Common Data Service environment from Finance and Operations</span></span>

<span data-ttu-id="681f1-122">Você pode atualizar links executando estas etapas:</span><span class="sxs-lookup"><span data-stu-id="681f1-122">You can update links by following these steps:</span></span>

+ <span data-ttu-id="681f1-123">Navegue para o ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="681f1-123">Navigate to the Finance and Operations environment.</span></span>
+ <span data-ttu-id="681f1-124">Abra o Gerenciamento de Dados.</span><span class="sxs-lookup"><span data-stu-id="681f1-124">Open Data Management.</span></span>
+ <span data-ttu-id="681f1-125">Clique em **Link para o CDS para aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="681f1-125">Click on **Link to CDS for apps**.</span></span>
+ <span data-ttu-id="681f1-126">Selecione todos os mapeamentos em execução e clique em **Parar**.</span><span class="sxs-lookup"><span data-stu-id="681f1-126">Select all the running mappings and click **Stop**.</span></span> 
+ <span data-ttu-id="681f1-127">Selecione todos os mapeamentos e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="681f1-127">Select all the mappings and click **Delete**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="681f1-128">A opção **Excluir** não aparecerá se o modelo **CustomerV3-Account** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="681f1-128">The **Delete** option will not appear if **CustomerV3-Account** template is selected.</span></span> <span data-ttu-id="681f1-129">Desmarque-o se necessário.</span><span class="sxs-lookup"><span data-stu-id="681f1-129">Unselect it if needed.</span></span> <span data-ttu-id="681f1-130">**CustomerV3-Account** é um modelo provisionado mais antigo e funciona com a solução Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="681f1-130">**CustomerV3-Account** is an older provisioned template and works with the Prospect to Cash solution.</span></span> <span data-ttu-id="681f1-131">Como ele é liberado globalmente, aparece em todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="681f1-131">Because it is globally released, it shows up under all templates.</span></span>

+ <span data-ttu-id="681f1-132">Clique em **Desvincular ambiente**.</span><span class="sxs-lookup"><span data-stu-id="681f1-132">Click **Unlink environment**.</span></span>
+ <span data-ttu-id="681f1-133">Clique em **Sim** para confirmação.</span><span class="sxs-lookup"><span data-stu-id="681f1-133">Click **Yes** for confirmation.</span></span>
+ <span data-ttu-id="681f1-134">Para vincular o novo ambiente, siga as etapas do [guia de instalação](https://aka.ms/dualwrite-docs).</span><span class="sxs-lookup"><span data-stu-id="681f1-134">To link the new environment, follow the steps in the [installation guide](https://aka.ms/dualwrite-docs).</span></span>

