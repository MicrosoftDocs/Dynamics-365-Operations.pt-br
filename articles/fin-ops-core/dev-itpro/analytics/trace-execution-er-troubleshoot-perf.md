---
title: Rastrear a execução de formatos de ER para solucionar problemas de desempenho
description: Este tópico fornece informações sobre como usar o recurso de rastreamento de desempenho no relatório eletrônico (ER) para solucionar problemas de desempenho.
author: NickSelin
manager: AnnBe
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6585e44701160bf31c107c07226f992b12cf035e
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550639"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a><span data-ttu-id="50f2e-103">Rastrear a execução dos formatos ER para solucionar problemas de desempenho</span><span class="sxs-lookup"><span data-stu-id="50f2e-103">Trace the execution of ER formats to troubleshoot performance issues</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="50f2e-104">Como parte do processo de designar configurações de relatórios eletrônicos (ER) para gerar documentos eletrônicos, você define o método usado para obter dados do aplicativo e inseri-los na saída gerada.</span><span class="sxs-lookup"><span data-stu-id="50f2e-104">As part of the process of designing Electronic reporting (ER) configurations to generate electronic documents, you define the method that is used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="50f2e-105">O recurso de rastreamento de desempenho de ER ajuda a reduzir significativamente o tempo e o custo envolvidos na coleta dos detalhes da execução do formato ER e o uso deles para solucionar problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-105">The ER performance trace feature helps significantly reduce the time and cost that are involved in collecting the details of ER format execution and using them to troubleshoot performance issues.</span></span> <span data-ttu-id="50f2e-106">Este tutorial fornece diretrizes sobre como obter rastreamentos de desempenho para formatos ER executados e como usar as informações desses rastreamentos para ajudar a melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-106">This tutorial provides guidelines about how to take performance traces for executed ER formats, and how to use the information from these traces to help improve performance.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50f2e-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="50f2e-107">Prerequisites</span></span>

<span data-ttu-id="50f2e-108">Para concluir os exemplos neste tutorial, você deve ter o seguinte acesso:</span><span class="sxs-lookup"><span data-stu-id="50f2e-108">To complete the examples in this tutorial, you must have the following access:</span></span>

- <span data-ttu-id="50f2e-109">Acesso a uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="50f2e-109">Access to one of the following roles:</span></span>

    - <span data-ttu-id="50f2e-110">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="50f2e-110">Electronic reporting developer</span></span>
    - <span data-ttu-id="50f2e-111">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="50f2e-111">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="50f2e-112">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="50f2e-112">System administrator</span></span>

- <span data-ttu-id="50f2e-113">Acesso à instância de Regulatory Configuration Services (RCS) que foi provisionado para o mesmo locatário como o aplicativo, para uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="50f2e-113">Access to the instance of Regulatory Configuration Services (RCS) that has been provisioned for the same tenant as the application, for one of the following roles:</span></span>

    - <span data-ttu-id="50f2e-114">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="50f2e-114">Electronic reporting developer</span></span>
    - <span data-ttu-id="50f2e-115">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="50f2e-115">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="50f2e-116">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="50f2e-116">System administrator</span></span>

<span data-ttu-id="50f2e-117">Você também deve baixar e armazenar localmente os arquivos a seguir.</span><span class="sxs-lookup"><span data-stu-id="50f2e-117">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="50f2e-118">Arquivo</span><span class="sxs-lookup"><span data-stu-id="50f2e-118">File</span></span>                                  | <span data-ttu-id="50f2e-119">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="50f2e-119">Content</span></span>                               |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="50f2e-120">Rastreamento de desempenho model.version.1</span><span class="sxs-lookup"><span data-stu-id="50f2e-120">Performance trace model.version.1</span></span>     | [<span data-ttu-id="50f2e-121">Configuração do modelo de dados de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="50f2e-121">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)    |
| <span data-ttu-id="50f2e-122">Rastreamento de desempenho metadata.version.1</span><span class="sxs-lookup"><span data-stu-id="50f2e-122">Performance trace metadata.version.1</span></span>  | [<span data-ttu-id="50f2e-123">Configuração de metadados de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="50f2e-123">Sample ER metadata configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)      |
| <span data-ttu-id="50f2e-124">Rastreamento de desempenho mapping.version.1.1</span><span class="sxs-lookup"><span data-stu-id="50f2e-124">Performance trace mapping.version.1.1</span></span> | [<span data-ttu-id="50f2e-125">Configuração do mapeamento do modelo de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="50f2e-125">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="50f2e-126">Rastreamento de desempenho format.version.1.1</span><span class="sxs-lookup"><span data-stu-id="50f2e-126">Performance trace format.version.1.1</span></span>  | [<span data-ttu-id="50f2e-127">Configuração de formato de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="50f2e-127">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg)       |

### <a name="configure-er-parameters"></a><span data-ttu-id="50f2e-128">Configurar parâmetros de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-128">Configure ER parameters</span></span>

<span data-ttu-id="50f2e-129">Cada rastreamento de desempenho de ER gerado no aplicativo é armazenado como um anexo do registro do log de execução.</span><span class="sxs-lookup"><span data-stu-id="50f2e-129">Each ER performance trace that is generated in the application is stored as an attachment of the execution log record.</span></span> <span data-ttu-id="50f2e-130">A estrutura de gerenciamento de documentos (DM) é usada para gerenciar esses anexos.</span><span class="sxs-lookup"><span data-stu-id="50f2e-130">The Document management (DM) framework is used to manage these attachments.</span></span> <span data-ttu-id="50f2e-131">Você deve configurar os parâmetros do ER antecipadamente para especificar o tipo de documento DM que deve ser usado para anexar rastreamentos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-131">You must configure ER parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="50f2e-132">No espaço de trabalho **Relatório eletrônico**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-132">In the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="50f2e-133">Depois, na página **Parâmetros de relatório eletrônico**, na guia **Anexos**, no campo **Outros**, selecione o tipo de documento DM a ser usado para rastreamentos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-133">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Página de parâmetros de relatórios eletrônicos](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

<span data-ttu-id="50f2e-135">Para estar disponível no campo de pesquisa **Outros**, um tipo de documento DM deve ser configurado da seguinte maneira na página **Tipos de documento** (**Administração da organização \> Gerenciamento de documentos \> Tipos de documento**):</span><span class="sxs-lookup"><span data-stu-id="50f2e-135">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="50f2e-136">**Classe:** anexar arquivo</span><span class="sxs-lookup"><span data-stu-id="50f2e-136">**Class:** Attach file</span></span>
- <span data-ttu-id="50f2e-137">**Grupo:** arquivo</span><span class="sxs-lookup"><span data-stu-id="50f2e-137">**Group:** File</span></span>

![Página Tipos de documento](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> <span data-ttu-id="50f2e-139">O tipo de documento selecionado deve estar disponível em todas as empresas da instância atual, porque os anexos do DM são específicos da empresa.</span><span class="sxs-lookup"><span data-stu-id="50f2e-139">The selected document type must be available in every company of the current instance, because DM attachments are company-specific.</span></span>

### <a name="configure-rcs-parameters"></a><span data-ttu-id="50f2e-140">Configurar parâmetros do RCS</span><span class="sxs-lookup"><span data-stu-id="50f2e-140">Configure RCS parameters</span></span>

<span data-ttu-id="50f2e-141">Os rastreamentos de desempenho do ER gerados serão importados para o RCS para análise usando o designer de formato do ER e o designer de mapeamento do ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-141">ER performance traces that are generated will be imported into RCS for analysis by using the ER format designer and the ER mapping designer.</span></span> <span data-ttu-id="50f2e-142">Como os rastreamentos de desempenho do ER são armazenados como anexos do registro de log de execução relacionado ao formato ER, você deve configurar os parâmetros do RCS antecipadamente, para especificar o tipo de documento DM que deve ser usado para anexar rastreamentos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-142">Because ER performance traces are stored as attachments of the execution log record that is related to the ER format, you must configure RCS parameters in advance, to specify the DM document type that should be used to attach performance traces.</span></span> <span data-ttu-id="50f2e-143">Na instância do RCS que foi provisionada para sua empresa, no espaço de trabalho **Relatório eletrônico**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-143">In the instance of RCS that has been provisioned for your company, in the **Electronic reporting** workspace, select **Electronic reporting parameters**.</span></span> <span data-ttu-id="50f2e-144">Depois, na página **Parâmetros de relatório eletrônico**, na guia **Anexos**, no campo **Outros**, selecione o tipo de documento DM a ser usado para rastreamentos de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-144">Then, on the **Electronic reporting parameters** page, on the **Attachments** tab, in the **Others** field, select the DM document type to use for performance traces.</span></span>

![Página Parâmetros de relatório eletrônico no RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

<span data-ttu-id="50f2e-146">Para estar disponível no campo de pesquisa **Outros**, um tipo de documento DM deve ser configurado da seguinte maneira na página **Tipos de documento** (**Administração da organização \> Gerenciamento de documentos \> Tipos de documento**):</span><span class="sxs-lookup"><span data-stu-id="50f2e-146">To be available in the **Others** lookup field, a DM document type must be configured in the following manner on the **Document types** page (**Organization administration \> Document management \> Document types**):</span></span>

- <span data-ttu-id="50f2e-147">**Classe:** anexar arquivo</span><span class="sxs-lookup"><span data-stu-id="50f2e-147">**Class:** Attach file</span></span>
- <span data-ttu-id="50f2e-148">**Grupo:** arquivo</span><span class="sxs-lookup"><span data-stu-id="50f2e-148">**Group:** File</span></span>

## <a name="design-an-er-solution"></a><span data-ttu-id="50f2e-149">Criar uma solução de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-149">Design an ER solution</span></span>

<span data-ttu-id="50f2e-150">Suponha que você tenha começado a criar uma solução de ER para gerar um novo relatório que apresente transações de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="50f2e-150">Assume that you've started to design a new ER solution to generate a new report that presents vendor transactions.</span></span> <span data-ttu-id="50f2e-151">Atualmente, você pode encontrar as transações de um fornecedor selecionado na página **Transações do fornecedor** (vá para **Conta a pagar \> Fornecedores \> Todos os fornecedores**, selecione um fornecedor e, no Painel de Ação, na guia **Fornecedor**, no grupo **Transações**, selecione **Transações**).</span><span class="sxs-lookup"><span data-stu-id="50f2e-151">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable \> Vendors \> All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="50f2e-152">Contudo, você deseja ter todas as transações do fornecedor ao mesmo tempo em um documento eletrônico no formato XML.</span><span class="sxs-lookup"><span data-stu-id="50f2e-152">However, you want to have all vendor transaction at the same time in one electronic document in XML format.</span></span> <span data-ttu-id="50f2e-153">Essa solução consistirá em várias configurações de ER que contêm os modelos de dados, metadados, mapeamento de modelo e componentes de formato necessários.</span><span class="sxs-lookup"><span data-stu-id="50f2e-153">This solution will consist of several ER configurations that contain the required data model, metadata, model mapping, and format components.</span></span>

1. <span data-ttu-id="50f2e-154">Entre na instância do RCS que foi provisionada para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="50f2e-154">Sign in to the instance of RCS that has been provisioned for your company.</span></span>
2. <span data-ttu-id="50f2e-155">Neste tutorial, você criará e modificará configurações para a empresa exemplo **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-155">In this tutorial, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="50f2e-156">Portanto, verifique se esse provedor de configuração foi adicionado ao RCS e selecionado como ativo.</span><span class="sxs-lookup"><span data-stu-id="50f2e-156">Therefore, make sure that this configuration provider has been added to RCS and selected as active.</span></span> <span data-ttu-id="50f2e-157">Para obter instruções, consulte o procedimento [Criar provedores de configuração e marcá-los como ativos](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="50f2e-157">For instructions, see the [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11) procedure.</span></span>
3. <span data-ttu-id="50f2e-158">No espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-158">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="50f2e-159">Na página **Configurações**, importe as configurações de ER que você baixou como um pré-requisito para o RCS, na seguinte ordem: modelo de dados, metadados, mapeamento de modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="50f2e-159">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into RCS, in the following order: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="50f2e-160">Para cada configuração, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="50f2e-160">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="50f2e-161">No Painel de Ação, selecione **Troca \> Carregar de um arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-161">On the Action Pane, select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="50f2e-162">Selecione **Procurar** para selecionar o arquivo apropriado para a configuração de ER necessária no formato XML.</span><span class="sxs-lookup"><span data-stu-id="50f2e-162">Select **Browse** to select the appropriate file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="50f2e-163">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-163">Select **OK**.</span></span>

    ![Página Configurações no RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a><span data-ttu-id="50f2e-165">Executar a solução de ER para rastrear a execução</span><span class="sxs-lookup"><span data-stu-id="50f2e-165">Run the ER solution to trace execution</span></span>

<span data-ttu-id="50f2e-166">Suponha que você tenha terminado de criar a primeira versão da solução de ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-166">Assume that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="50f2e-167">Agora você deseja testá-la em sua instância e analisar o desempenho da execução.</span><span class="sxs-lookup"><span data-stu-id="50f2e-167">You now want to test it in your instance and analyze execution performance.</span></span>

### <a id='import-configuration'></a><span data-ttu-id="50f2e-168">Importar uma configuração de ER do RCS para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="50f2e-168">Import an ER configuration from RCS into Finance and Operations</span></span>

1. <span data-ttu-id="50f2e-169">Entre na sua instância do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="50f2e-169">Sign in to your application instance.</span></span>
2. <span data-ttu-id="50f2e-170">Para este tutorial, você importará configurações de sua instância do RCS (onde você projeta seus componentes de ER) em sua instância (onde você testa e finalmente as utiliza).</span><span class="sxs-lookup"><span data-stu-id="50f2e-170">For this tutorial, you will import configurations from your RCS instance (where you design your ER components) into your instance (where you test and finally use them).</span></span> <span data-ttu-id="50f2e-171">Portanto, você deve se certificar de que todos os artefatos necessários foram preparados.</span><span class="sxs-lookup"><span data-stu-id="50f2e-171">Therefore, you must make sure that all the required artifacts have been prepared.</span></span> <span data-ttu-id="50f2e-172">Para obter instruções, consulte o procedimento [Importar configurações do ER (Relatório eletrônico) dos RCS (Serviços de configuração regulatória)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations).</span><span class="sxs-lookup"><span data-stu-id="50f2e-172">For instructions, see the [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/rcs-download-configurations) procedure.</span></span>
3. <span data-ttu-id="50f2e-173">Siga estas etapas para importar as configurações do RCS para o aplicativo:</span><span class="sxs-lookup"><span data-stu-id="50f2e-173">Follow these steps to import the configurations from RCS into the application:</span></span>

    1. <span data-ttu-id="50f2e-174">No espaço de trabalho **Relatório eletrônico**, no bloco do provedor de configuração **Litware, Inc.**, selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-174">In the **Electronic reporting** workspace, on the tile for the **Litware, Inc.** configuration provider, select **Repositories**.</span></span>
    2. <span data-ttu-id="50f2e-175">Na página **Repositório de configuração**, selecione o repositório do tipo **RCS** e depois selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-175">On the **Configuration repository** page, select the repository of the **RCS** type, and then select **Open**.</span></span>
    3. <span data-ttu-id="50f2e-176">Na Guia Rápida **Configurações**, selecione a configuração **Formato de rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-176">On the **Configurations** FastTab, select the **Performance trace format** configuration.</span></span>
    4. <span data-ttu-id="50f2e-177">Na Guia Rápida **Versões**, selecione a versão **1.1** da configuração selecionada e depois selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-177">On the **Versions** FastTab, select version **1.1** of the selected configuration, and then select **Import**.</span></span>

    ![Página do repositório de configuração](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

<span data-ttu-id="50f2e-179">As versões correspondentes do modelo de dados e as configurações de mapeamento de modelo são importadas automaticamente como pré-requisitos para a configuração importada do formato ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-179">The corresponding versions of the data model and model mapping configurations are automatically imported as prerequisites for the imported ER format configuration.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="50f2e-180">Ativar o rastreamento de desempenho de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-180">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="50f2e-181">Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-181">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="50f2e-182">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-182">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="50f2e-183">Na caixa de diálogo **Parâmetros de usuário**, na seção **Rastreamento de execução**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="50f2e-183">In the **User parameters** dialog box, in the **Execution tracing** section, follow these steps:</span></span>

    1. <span data-ttu-id="50f2e-184">No campo **Formato de rastreamento de execução**, selecione **Depurar formato de rastreamento** para começar a coletar os detalhes da execução do formato ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-184">In the **Execution trace format** field, select **Debug trace format** to start to collect the details of ER format execution.</span></span> <span data-ttu-id="50f2e-185">Quando esse valor é selecionado, o rastreamento de desempenho coletará informações sobre o tempo gasto nas seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="50f2e-185">When this value is selected, the performance trace will collect information about the time that is spent on the following actions:</span></span>

        - <span data-ttu-id="50f2e-186">Execução de cada fonte de dados no mapeamento de modelo que é chamado para obter dados</span><span class="sxs-lookup"><span data-stu-id="50f2e-186">Running each data source in the model mapping that is called to get data</span></span>
        - <span data-ttu-id="50f2e-187">Processamento de cada item de formato para inserir dados na saída gerada</span><span class="sxs-lookup"><span data-stu-id="50f2e-187">Processing each format item to enter data in the output that is generated</span></span>

        <span data-ttu-id="50f2e-188">Você usa o campo **Formato de rastreamento de execução** para especificar o formato do rastreamento de desempenho gerado em que os detalhes de execução são armazenados em formato ER e elementos de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="50f2e-188">You use the **Execution trace format** field to specify the format of the generated performance trace that the execution details are stored in for ER format and mapping elements.</span></span> <span data-ttu-id="50f2e-189">Selecionando **Depurar formato de rastreamento** como o valor, você poderá analisar o conteúdo do rastreamento no designer de operação do ER e ver o formato ER ou os elementos de mapeamento mencionados no rastreamento.</span><span class="sxs-lookup"><span data-stu-id="50f2e-189">By selecting **Debug trace format** as the value, you will be able to analyze the content of the trace in ER Operation designer, and see the ER format or mapping elements that are mentioned in the trace.</span></span>

    2. <span data-ttu-id="50f2e-190">Defina as seguintes opções como **Sim** para coletar detalhes específicos da execução dos componentes de mapeamento do modelo de ER e formato ER:</span><span class="sxs-lookup"><span data-stu-id="50f2e-190">Set the following options to **Yes** to collect specific details of the execution of the ER model mapping and ER format components:</span></span>

        - <span data-ttu-id="50f2e-191">**Coletar estatísticas da consulta** – Quando esta opção está ativada, o rastreamento de desempenho coletará as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="50f2e-191">**Collect query statistics** – When this option is turned on, the performance trace will collect the following information:</span></span>

            - <span data-ttu-id="50f2e-192">O número de chamadas de banco de dados feitas por fontes de dados</span><span class="sxs-lookup"><span data-stu-id="50f2e-192">The number of database calls that were made by data sources</span></span>
            - <span data-ttu-id="50f2e-193">O número de chamadas duplicadas para o banco de dados</span><span class="sxs-lookup"><span data-stu-id="50f2e-193">The number of duplicate calls to the database</span></span>
            - <span data-ttu-id="50f2e-194">Detalhes das instruções SQL que foram usadas para fazer chamadas de banco de dados</span><span class="sxs-lookup"><span data-stu-id="50f2e-194">Details of the SQL statements that were used to make database calls</span></span>

        - <span data-ttu-id="50f2e-195">**Acesso de rastreamento de cache** – Quando esta opção está ativada, o rastreamento de desempenho coletará informações sobre o uso de cache do mapeamento do modelo de ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-195">**Trace access of caching** – When this option is turned on, the performance trace will collect information about the ER model mapping's cache usage.</span></span>
        - <span data-ttu-id="50f2e-196">**Acesso de dados de rastreamento** – Quando esta opção está ativada, o rastreamento de desempenho coletará informações sobre o número de chamadas para o banco de dados para origens de dados executadas do tipo de lista de registros.</span><span class="sxs-lookup"><span data-stu-id="50f2e-196">**Trace data access** – When this option is turned on, the performance trace will collect information about the number of calls to the database for executed data sources of the record list type.</span></span>
        - <span data-ttu-id="50f2e-197">**Enumeração da lista de rastreamento** – Quando esta opção está ativada, o rastreamento de desempenho coletará informações sobre o número de registros que são solicitados de fontes de dados do tipo de lista de registros.</span><span class="sxs-lookup"><span data-stu-id="50f2e-197">**Trace list enumeration** – When this option is turned on, the performance trace will collect information about the number of records that are requested from data sources of the record list type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50f2e-198">Os parâmetros na caixa de diálogo **Parâmetros de usuário** são específicos do usuário e da empresa atual.</span><span class="sxs-lookup"><span data-stu-id="50f2e-198">The parameters in the **User parameters** dialog box are specific to the user and the current company.</span></span>

    ![Caixa de diálogo de parâmetros do usuário](./media/GER-PerfTrace-GER-UserParameters.png)

### <a id='run-format'></a><span data-ttu-id="50f2e-200">Executar o formato de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-200">Run the ER format</span></span>

1. <span data-ttu-id="50f2e-201">Selecione a empresa **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-201">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="50f2e-202">Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-202">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3. <span data-ttu-id="50f2e-203">Na página **Configurações**, na árvore de configuração, selecione o item **Formato de rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-203">On the **Configurations** page, in the configuration tree, select the **Performance trace format** item.</span></span>
4. <span data-ttu-id="50f2e-204">No Painel de Ação, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-204">On the Action Pane, select **Run**.</span></span>

<span data-ttu-id="50f2e-205">Observe que o arquivo gerado apresenta informações sobre 265 transações de seis fornecedores.</span><span class="sxs-lookup"><span data-stu-id="50f2e-205">Notice that the file that is generated presents information about 265 transactions for six vendors.</span></span>

## <a name="review-the-execution-trace"></a><span data-ttu-id="50f2e-206">Revisar o rastreamento de execução</span><span class="sxs-lookup"><span data-stu-id="50f2e-206">Review the execution trace</span></span>

### <a id='export-trace'></a><span data-ttu-id="50f2e-207">Exporte o rastreamento gerado do aplicativo</span><span class="sxs-lookup"><span data-stu-id="50f2e-207">Export the generated trace from the application</span></span>

<span data-ttu-id="50f2e-208">Os rastreamentos de desempenho são desacoplados do formato ER de origem e podem ser serializados em um arquivo zip externo.</span><span class="sxs-lookup"><span data-stu-id="50f2e-208">Performance traces are decoupled from the source ER format and can be serialized to an external zip file.</span></span>

1. <span data-ttu-id="50f2e-209">Vá para **Administração da organização \> Relatório eletrônico \> Logs de depuração de configuração**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-209">Go to **Organization administration \> Electronic reporting \> Configuration debug logs**.</span></span>
2. <span data-ttu-id="50f2e-210">Na página **Logs de execução de relatórios eletrônicos**, no painel esquerdo, no campo **Nome da configuração**, selecione **Formato de rastreamento de desempenho** para encontrar os registros de log que foram gerados pela execução da configuração **Formato de rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-210">On the **Electronic reporting run logs** page, in the left pane, in the **Configuration name** field, select **Performance trace format** to find the log records that have been generated by the execution of the **Performance trace format** configuration.</span></span>
3. <span data-ttu-id="50f2e-211">Selecione o botão **Anexos** (o símbolo de clipe de papel) no canto superior direito da página ou pressione **Ctrl+Shift+A**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-211">Select the **Attachments** button (the paper clip symbol) in the upper-right corner of the page, or press **Ctrl+Shift+A**.</span></span>

    ![Botão Anexos na página Logs de execução de relatórios eletrônicos](./media/GER-PerfTrace-GER-DebugLog.png)

4. <span data-ttu-id="50f2e-213">Na página **Anexos para Logs de execução de relatórios eletrônicos**, no Painel de Ação, selecione **Abrir** para obter o rastreamento de desempenho como um arquivo zip e armazená-lo localmente.</span><span class="sxs-lookup"><span data-stu-id="50f2e-213">On the **Attachments for Electronic reporting run logs** page, on the Action Pane, select **Open** to get the performance trace as a zip file and store it locally.</span></span>

    ![Anexos para Logs de execução de relatórios eletrônicos](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> <span data-ttu-id="50f2e-215">O rastreamento gerado tem uma referência ao relatório ER de origem por meio de um identificador de relatório exclusivo no formato **GUID** apenas.</span><span class="sxs-lookup"><span data-stu-id="50f2e-215">The trace that is generated has a reference to the source ER report via a unique report identifier in **GUID** format only.</span></span> <span data-ttu-id="50f2e-216">A numeração de versão do formato não é considerada.</span><span class="sxs-lookup"><span data-stu-id="50f2e-216">The version numbering of the format isn't considered.</span></span>

<span data-ttu-id="50f2e-217">Observe que a associação entre o rastreamento de desempenho que foi gerado para o formato ER executado e o mapeamento do modelo de ER é baseada no descritor raiz que foi usado e no modelo de dados comum.</span><span class="sxs-lookup"><span data-stu-id="50f2e-217">Notice that the association between the performance trace that has been generated for the executed ER format and the ER model mapping is based on the root descriptor that was used and the common data model.</span></span> <span data-ttu-id="50f2e-218">A numeração da versão do formato e do mapeamento do modelo não é considerada.</span><span class="sxs-lookup"><span data-stu-id="50f2e-218">The version numbering of the format and model mapping isn't considered.</span></span> <span data-ttu-id="50f2e-219">A configuração do sinalizador **Padrão do mapeamento de modelo** para o mapeamento do modelo também não é considerada.</span><span class="sxs-lookup"><span data-stu-id="50f2e-219">The setting of the **Default for model mapping** flag for the model mapping also isn't considered.</span></span>

### <a id='import-trace'></a><span data-ttu-id="50f2e-220">Importar o rastreamento gerado para o RCS</span><span class="sxs-lookup"><span data-stu-id="50f2e-220">Import the generated trace into RCS</span></span>

1. <span data-ttu-id="50f2e-221">No RCS, no espaço de trabalho **Relatório eletrônico**, selecione o bloco **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-221">In RCS, in the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
2. <span data-ttu-id="50f2e-222">Na página **Configurações**, na árvore de configuração, expanda o item **Modelo de rastreamento de desempenho** e selecione o item **Formato de rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-222">On the **Configurations** page, in the configuration tree, expand the **Performance trace model** item, and select the **Performance trace format** item.</span></span>
3. <span data-ttu-id="50f2e-223">No Painel de Ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-223">On the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="50f2e-224">Na página **Designer de formato**, no Painel de Ação, selecione **Rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-224">On the **Format designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="50f2e-225">Na caixa de diálogo **Configurações de resultado de rastreamento de desempenho**, selecione **Importar rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-225">In the **Performance trace result settings** dialog box, select **Import performance trace**.</span></span>
6. <span data-ttu-id="50f2e-226">Selecione **Procurar** para selecionar o arquivo zip que você exportou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="50f2e-226">Select **Browse** to select the zip file that you exported earlier.</span></span>
7. <span data-ttu-id="50f2e-227">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-227">Select **OK**.</span></span>

    ![Caixa de diálogo Configurações de resultado de rastreamento de desempenho no RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a><span data-ttu-id="50f2e-229">Use o rastreamento de desempenho para análise no RCS - Execução de formato</span><span class="sxs-lookup"><span data-stu-id="50f2e-229">Use the performance trace for analysis in RCS – Format execution</span></span>

1. <span data-ttu-id="50f2e-230">No RCS, na página **Designer de formato**, selecione **Expandir/recolher** para expandir o conteúdo de todos os itens de formato.</span><span class="sxs-lookup"><span data-stu-id="50f2e-230">In RCS, on the **Format designer** page, select **Expand/collapse** to expand the content of all format items.</span></span>

    <span data-ttu-id="50f2e-231">Observe que informações adicionais são mostradas para alguns itens do formato atual:</span><span class="sxs-lookup"><span data-stu-id="50f2e-231">Notice that additional information is shown for some items of the current format:</span></span>

    - <span data-ttu-id="50f2e-232">O tempo real gasto ao inserir dados na saída gerada usando o item de formato</span><span class="sxs-lookup"><span data-stu-id="50f2e-232">The actual time that was spent entering data in the generated output by using the format item</span></span>
    - <span data-ttu-id="50f2e-233">O mesmo tempo expresso como uma porcentagem do tempo total gasto gerando toda a saída</span><span class="sxs-lookup"><span data-stu-id="50f2e-233">The same time expressed as a percentage of the total time that was spent generating the whole output</span></span>

    ![Página Designer de formatos no RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. <span data-ttu-id="50f2e-235">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-235">Close **Format designer** page.</span></span>

### <a id='use-trace'></a><span data-ttu-id="50f2e-236">Use o rastreamento de desempenho para análise no RCS – Mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="50f2e-236">Use the performance trace for analysis in RCS – Model mapping</span></span>

1. <span data-ttu-id="50f2e-237">No RCS, na página **Configurações**, na árvore de configuração, selecione o item **Mapeamento de rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-237">In RCS, on the **Configurations** page, in the configuration tree, select the **Performance trace mapping** item.</span></span>
2. <span data-ttu-id="50f2e-238">No Painel de Ação, selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-238">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="50f2e-239">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-239">Select **Designer**.</span></span>
4. <span data-ttu-id="50f2e-240">Na página **Designer de mapeamento de modelo**, no Painel de Ação, selecione **Rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-240">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="50f2e-241">Selecione o rastreamento que você importou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="50f2e-241">Select the trace that you imported earlier.</span></span>
6. <span data-ttu-id="50f2e-242">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-242">Select **OK**.</span></span>

<span data-ttu-id="50f2e-243">Observe que novas informações ficam disponíveis para alguns itens da fonte de dados do mapeamento atual do modelo:</span><span class="sxs-lookup"><span data-stu-id="50f2e-243">Notice that new information becomes available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="50f2e-244">O tempo real gasto ao obter dados usando a fonte de dados</span><span class="sxs-lookup"><span data-stu-id="50f2e-244">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="50f2e-245">O mesmo tempo expresso como uma porcentagem do tempo total gasto na execução do mapeamento do modelo inteiro</span><span class="sxs-lookup"><span data-stu-id="50f2e-245">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

<span data-ttu-id="50f2e-246">Observe que o ER informa que o mapeamento do modelo atual duplica as solicitações do banco de dados enquanto a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum é executada.</span><span class="sxs-lookup"><span data-stu-id="50f2e-246">Notice that ER informs you that the current model mapping duplicates database requests while the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source is run.</span></span> <span data-ttu-id="50f2e-247">Essa duplicação ocorre porque a lista de transações do fornecedor é chamada duas vezes para cada registro de fornecedor repetido:</span><span class="sxs-lookup"><span data-stu-id="50f2e-247">This duplication occurs because the list of vendor transactions is called two times for each iterated vendor record:</span></span>

- <span data-ttu-id="50f2e-248">Uma chamada é feita para inserir detalhes de cada transação no modelo de dados, com base nas ligações configuradas.</span><span class="sxs-lookup"><span data-stu-id="50f2e-248">One call is made to enter details of each transaction in the data model, based on configured bindings.</span></span>
- <span data-ttu-id="50f2e-249">Uma chamada é feita para inserir o número calculado de transações por fornecedor no modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="50f2e-249">One call is made to enter the calculated number of transactions per vendor in the data model.</span></span>

![Mensagem sobre solicitações de banco de dados duplicadas na página Designer de mapeamento de modelo no RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

<span data-ttu-id="50f2e-251">O valor **\[Q:530\]** indica que a tabela VendTrans foi chamada 530 vezes para retornar um registro dessa tabela para a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum.</span><span class="sxs-lookup"><span data-stu-id="50f2e-251">The value **\[Q:530\]** indicates that the VendTrans table was called 530 times to return a record from that table to the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source.</span></span> <span data-ttu-id="50f2e-252">O valor **\[530\]** indica que a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum foi chamada 530 vezes para retornar um registro dessa fonte de dados e inserir os detalhes dela no modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="50f2e-252">The value **\[530\]** indicates that the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source was called 530 times to return a record from that data source and enter the details from it in the data model.</span></span>

<span data-ttu-id="50f2e-253">Recomendamos que você use o armazenamento em cache para a fonte de dados VendTable/\<Relations/VendTrans.VendTable\_AccountNum, para reduzir o número de chamadas feitas para obter os detalhes de 265 transações e ajudar a melhorar o desempenho do mapeamento do modelo.</span><span class="sxs-lookup"><span data-stu-id="50f2e-253">We recommend that you use caching for the VendTable/\<Relations/VendTrans.VendTable\_AccountNum data source, to reduce the number of calls that are made to get the details for 265 transactions and help improve the performance of the model mapping.</span></span>

<span data-ttu-id="50f2e-254">Também pode ser útil reduzir o número de chamadas feitas à fonte de dados LedgerTransTypeList.</span><span class="sxs-lookup"><span data-stu-id="50f2e-254">It can also be useful to reduce the number of calls that are made to the LedgerTransTypeList data source.</span></span> <span data-ttu-id="50f2e-255">Essa fonte de dados é usada para associar cada valor da enumeração **LedgerTransType** a seu rótulo.</span><span class="sxs-lookup"><span data-stu-id="50f2e-255">This data source is used to associate each value of the **LedgerTransType** enumeration with its label.</span></span> <span data-ttu-id="50f2e-256">Usando essa fonte de dados, você pode encontrar um rótulo apropriado e inseri-lo no modelo de dados para cada transação do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="50f2e-256">By using this data source, you can find an appropriate label and enter it in the data model for each vendor transaction.</span></span> <span data-ttu-id="50f2e-257">O número atual de chamadas para essa fonte de dados (9.027) é bastante alto para 265 transações.</span><span class="sxs-lookup"><span data-stu-id="50f2e-257">The current number of calls to this data source (9,027) is quite high for 265 transactions.</span></span>

![Página Designer de mapeamento de modelo no RCS, mostrando 9.027 chamadas para a fonte de dados](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="50f2e-259">Melhorar o mapeamento do modelo com base nas informações do rastreamento de execução</span><span class="sxs-lookup"><span data-stu-id="50f2e-259">Improve the model mapping based on information from the execution trace</span></span>

### <a name="modify-the-logic-of-the-model-mapping"></a><span data-ttu-id="50f2e-260">Modificar a lógica do mapeamento do modelo</span><span class="sxs-lookup"><span data-stu-id="50f2e-260">Modify the logic of the model mapping</span></span>

1. <span data-ttu-id="50f2e-261">Siga estas etapas para usar o armazenamento em cache, para ajudar a evitar chamadas duplicadas para o banco de dados:</span><span class="sxs-lookup"><span data-stu-id="50f2e-261">Follow these steps to use caching, to help prevent duplicate calls to the database:</span></span>

    1. <span data-ttu-id="50f2e-262">No RCS, na página **Designer de mapeamento de modelo**, no painel **Fontes de dados**, selecione o item **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-262">In RCS, on the **Model mapping designer** page, in the **Data sources** pane, select the **VendTable** item.</span></span>
    2. <span data-ttu-id="50f2e-263">Selecione **Cache**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-263">Select **Cache**.</span></span>
    3. <span data-ttu-id="50f2e-264">Expanda o item **VendTable**, expanda a lista de relações um para muitos para a fonte de dados VendTable (o item **\<Relações**) e selecione o item **VendTrans.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-264">Expand the **VendTable** item, expand the list of one-to-many relations for the VendTable data source (the **\<Relations** item), and select the **VendTrans.VendTable\_AccountNum** item.</span></span>
    4. <span data-ttu-id="50f2e-265">Selecione **Cache**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-265">Select **Cache**.</span></span>

    ![Configuração de cache para ajudar a impedir chamadas duplicadas](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. <span data-ttu-id="50f2e-267">Siga estas etapas para trazer a fonte de dados LedgerTransTypeList para o escopo da fonte de dados VendTable:</span><span class="sxs-lookup"><span data-stu-id="50f2e-267">Follow these steps to bring the LedgerTransTypeList data source into the scope of the VendTable data source:</span></span>

    1. <span data-ttu-id="50f2e-268">No painel **Tipos de fontes de dados**, expanda o item **Funções** e selecione o item **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-268">In the **Data source types** pane, expand the **Functions** item, and select the **Calculated field** item.</span></span>
    2. <span data-ttu-id="50f2e-269">No painel **Fontes de dados**, selecione o item **VendTable**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-269">In the **Data sources** pane, select the **VendTable** item.</span></span>
    3. <span data-ttu-id="50f2e-270">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-270">Select **Add**.</span></span>
    4. <span data-ttu-id="50f2e-271">No campo **Nome**, insira **\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-271">In the **Name** field, enter **\$TransType**.</span></span>
    5. <span data-ttu-id="50f2e-272">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-272">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="50f2e-273">No campo **Fórmula**, insira **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-273">In the **Formula** field, enter **LedgerTransTypeList**.</span></span>
    7. <span data-ttu-id="50f2e-274">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-274">Select **Save**.</span></span>
    8. <span data-ttu-id="50f2e-275">Feche a página **Editor de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-275">Close the **Formula editor** page.</span></span>
    9. <span data-ttu-id="50f2e-276">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-276">Click **OK**.</span></span>

3. <span data-ttu-id="50f2e-277">Siga estas etapas para fazer o armazenamento em cache do campo **\$TransType**:</span><span class="sxs-lookup"><span data-stu-id="50f2e-277">Follow these steps to do caching of the **\$TransType** field:</span></span>

    1. <span data-ttu-id="50f2e-278">Selecione o item **LedgerTransTypeList**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-278">Select the **LedgerTransTypeList** item.</span></span>
    2. <span data-ttu-id="50f2e-279">Selecione **Cache**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-279">Select **Cache**.</span></span>
    3. <span data-ttu-id="50f2e-280">Selecione o item **VendTable.\$TransType**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-280">Select the **VendTable.\$TransType** item.</span></span>
    4. <span data-ttu-id="50f2e-281">Selecione **Cache**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-281">Select **Cache**.</span></span>

    ![Configuração de cache para o campo $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. <span data-ttu-id="50f2e-283">Siga estas etapas para alterar o campo **\$TransTypeRecord** para que ele comece a usar o campo **\$TransType** em cache:</span><span class="sxs-lookup"><span data-stu-id="50f2e-283">Follow these steps to change the **\$TransTypeRecord** field so that it starts to use the cached **\$TransType** field:</span></span>

    1. <span data-ttu-id="50f2e-284">No painel **Fontes de dados**, expanda o item **VendTable**, expanda o item **\<Relations**, expanda o item **VendTrans.VendTable\_AccountNum** e selecione o item **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-284">In the **Data sources** pane, expand the **VendTable** item, expand the **\<Relations** item, expand the **VendTrans.VendTable\_AccountNum** item, and select the **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord** item.</span></span>
    2. <span data-ttu-id="50f2e-285">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-285">Select **Edit**.</span></span>
    3. <span data-ttu-id="50f2e-286">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-286">Select **Edit formula**.</span></span>
    4. <span data-ttu-id="50f2e-287">No campo **Fórmula**, encontre a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="50f2e-287">In the **Formula** field, find the following expression:</span></span>

        <span data-ttu-id="50f2e-288">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span><span class="sxs-lookup"><span data-stu-id="50f2e-288">FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))</span></span>

    5. <span data-ttu-id="50f2e-289">No campo **Fórmula**, insira a seguinte expressão:</span><span class="sxs-lookup"><span data-stu-id="50f2e-289">In the **Formula** field, enter the following expression:</span></span>

        <span data-ttu-id="50f2e-290">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span><span class="sxs-lookup"><span data-stu-id="50f2e-290">FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).</span></span>

    6. <span data-ttu-id="50f2e-291">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-291">Select **Save**.</span></span>
    7. <span data-ttu-id="50f2e-292">Feche a página **Editor de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-292">Close the **Formula editor** page.</span></span>
    8. <span data-ttu-id="50f2e-293">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-293">Select **OK**.</span></span>

5. <span data-ttu-id="50f2e-294">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-294">Select **Save**.</span></span>
6. <span data-ttu-id="50f2e-295">Feche a página **Designer de mapeamento de modelo**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-295">Close the **Model mapping designer** page.</span></span>
7. <span data-ttu-id="50f2e-296">Feche a página **Mapeamentos de modelo**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-296">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="50f2e-297">Concluir a versão modificada do mapeamento do modelo de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-297">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="50f2e-298">No RCS, na página **Configurações**, na Guia Rápida **Versões**, selecione a versão **1.2** da configuração **Mapeamento de rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-298">In RCS, on the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance trace mapping** configuration.</span></span>
2. <span data-ttu-id="50f2e-299">Selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-299">Select **Change status**.</span></span>
3. <span data-ttu-id="50f2e-300">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-300">Select **Complete**.</span></span>

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a><span data-ttu-id="50f2e-301">Importar a configuração de mapeamento do modelo de ER modificado do RCS para o aplicativo</span><span class="sxs-lookup"><span data-stu-id="50f2e-301">Import the modified ER model mapping configuration from RCS into the application</span></span>

<span data-ttu-id="50f2e-302">Repita as etapas na seção [Importar uma configuração de ER do RCS para Finance and Operations](#import-configuration) anteriormente neste tópico para importar a versão 1.2 da configuração **Mapeamento de rastreamento de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-302">Repeat the steps in the [Import an ER configuration from RCS into Finance and Operations](#import-configuration) section earlier in this topic to import version 1.2 of the **Performance trace mapping** configuration.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="50f2e-303">Executar a solução de ER modificada para rastrear a execução</span><span class="sxs-lookup"><span data-stu-id="50f2e-303">Run the modified ER solution to trace execution</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="50f2e-304">Executar o formato de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-304">Run the ER format</span></span>

<span data-ttu-id="50f2e-305">Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-305">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="review-the-execution-trace"></a><span data-ttu-id="50f2e-306">Revisar o rastreamento de execução</span><span class="sxs-lookup"><span data-stu-id="50f2e-306">Review the execution trace</span></span>

### <a name="export-the-generated-trace-from-the-application"></a><span data-ttu-id="50f2e-307">Exportar o rastreamento gerado do aplicativo</span><span class="sxs-lookup"><span data-stu-id="50f2e-307">Export the generated trace from the application</span></span>

<span data-ttu-id="50f2e-308">Repita as etapas na seção [Exportar o rastreamento gerado no aplicativo](#export-trace) anteriormente neste tópico para salvar um novo rastreamento de desempenho localmente.</span><span class="sxs-lookup"><span data-stu-id="50f2e-308">Repeat the steps in the [Export the generated trace from the application](#export-trace) section earlier in this topic to save a new performance trace locally.</span></span>

### <a name="import-the-generated-trace-into-rcs"></a><span data-ttu-id="50f2e-309">Importar o rastreamento gerado para o RCS</span><span class="sxs-lookup"><span data-stu-id="50f2e-309">Import the generated trace into RCS</span></span>

<span data-ttu-id="50f2e-310">Repita as etapas na seção [Importar o rastreamento gerado para o RCS](#import-trace) anterior neste tópico para importar o novo rastreamento de desempenho para o RCS.</span><span class="sxs-lookup"><span data-stu-id="50f2e-310">Repeat the steps in the [Import the generated trace into RCS](#import-trace) section earlier in this topic to import the new performance trace into RCS.</span></span>

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><span data-ttu-id="50f2e-311">Use o rastreamento de desempenho para análise no RCS – Mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="50f2e-311">Use the performance trace for analysis in RCS – Model mapping</span></span>

<span data-ttu-id="50f2e-312">Repita as etapas na seção [Use o rastreamento de desempenho para análise no RCS – Mapeamento de modelos](#use-trace) anterior deste tópico para analisar o último rastreio de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-312">Repeat the steps in the [Use the performance trace for analysis in RCS – Model mapping](#use-trace) section earlier in this topic to analyze the latest performance trace.</span></span>

<span data-ttu-id="50f2e-313">Observe que os ajustes feitos no mapeamento do modelo eliminaram consultas duplicadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="50f2e-313">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="50f2e-314">O número de chamadas para tabelas de banco de dados e fontes de dados para esse mapeamento de modelo também foi reduzido.</span><span class="sxs-lookup"><span data-stu-id="50f2e-314">The number of calls to database tables and data sources for this model mapping has been also reduced.</span></span> <span data-ttu-id="50f2e-315">Portanto, o desempenho de toda a solução de ER melhorou.</span><span class="sxs-lookup"><span data-stu-id="50f2e-315">Therefore, the performance of the whole ER solution has improved.</span></span>

![Informações de rastreamento da fonte de dados VendTable na página Designer de mapeamento de modelo no RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

<span data-ttu-id="50f2e-317">Nas informações de rastreamento, o valor **\[12\]** da fonte de dados VendTable indica que essa fonte de dados foi chamada 12 vezes.</span><span class="sxs-lookup"><span data-stu-id="50f2e-317">In the trace information, the value **\[12\]** for the VendTable data source indicates that this data source was called 12 times.</span></span> <span data-ttu-id="50f2e-318">O valor **\[Q:6\]** indica que seis chamadas foram convertidas em chamadas de banco de dados para a tabela VendTable.</span><span class="sxs-lookup"><span data-stu-id="50f2e-318">The value **\[Q:6\]** indicates that six calls were translated to database calls to the VendTable table.</span></span> <span data-ttu-id="50f2e-319">O valor **\[C:6\]** indica que os registros que foram obtidos do banco de dados foram armazenados em cache e seis outras chamadas foram processadas usando o cache.</span><span class="sxs-lookup"><span data-stu-id="50f2e-319">The value **\[C:6\]** indicates that the records that were fetched from the database were cached, and six other calls were processed by using the cache.</span></span>

<span data-ttu-id="50f2e-320">Observe que o número de chamadas para a fonte de dados LedgerTransTypeList foi reduzido de 9.027 para 240.</span><span class="sxs-lookup"><span data-stu-id="50f2e-320">Notice that the number of calls to the LedgerTransTypeList data source has been reduced from 9,027 to 240.</span></span>

![Informações de rastreamento da fonte de dados LedgerTransTypeList na página Designer de mapeamento de modelo no RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a><span data-ttu-id="50f2e-322">Revisar o rastreamento de execução do aplicativo</span><span class="sxs-lookup"><span data-stu-id="50f2e-322">Review the execution trace in the application</span></span>

<span data-ttu-id="50f2e-323">Além do RCS, algumas versões podem oferecer recursos para uma experiência de designer de estrutura de ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-323">In addition to RCS, some versions might offer capabilities for an ER framework designer experience.</span></span> <span data-ttu-id="50f2e-324">Essas versões têm uma opção **Habilitar o modo de design** que pode ser ativada.</span><span class="sxs-lookup"><span data-stu-id="50f2e-324">These versions have an **Enable design mode** option that can be turned on.</span></span> <span data-ttu-id="50f2e-325">Você pode encontrar essa opção na guia **General** da página **Parâmetros de relatório eletrônico**, que pode ser aberta no espaço de trabalho **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-325">You can find this option on the **General** tab of the **Electronic reporting parameters** page, which you can open from the **Electronic reporting** workspace.</span></span>

![Habilitar a opção do modo de design da página de parâmetros de relatórios eletrônicos](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

<span data-ttu-id="50f2e-327">Se usar uma dessas versões, você poderá analisar os detalhes dos rastreamentos de desempenho gerados diretamente no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="50f2e-327">If you use one of these versions, you can analyze the details of generated performance traces directly in the application.</span></span> <span data-ttu-id="50f2e-328">Você não precisa exportá-los do aplicativo e importá-los para o RCS.</span><span class="sxs-lookup"><span data-stu-id="50f2e-328">You don't have to export them from the application and import them into RCS.</span></span>

## <a name="review-the-execution-trace-by-using-external-tools"></a><span data-ttu-id="50f2e-329">Revisar o rastreamento de execução usando ferramentas externas</span><span class="sxs-lookup"><span data-stu-id="50f2e-329">Review the execution trace by using external tools</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="50f2e-330">Configurar parâmetros de usuário</span><span class="sxs-lookup"><span data-stu-id="50f2e-330">Configure user parameters</span></span>

1. <span data-ttu-id="50f2e-331">Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-331">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
2. <span data-ttu-id="50f2e-332">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-332">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="50f2e-333">Na caixa de diálogo **Parâmetros de usuário**, na seção **Rastreamento de execução**, no campo **Formato de rastreamento de execução**, selecione **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-333">In the **User parameters** dialog box, in the **Execution tracing** section, in the **Execution trace format** field, select **PerfView XML**.</span></span>

### <a name="run-the-er-format"></a><span data-ttu-id="50f2e-334">Executar o formato de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-334">Run the ER format</span></span>

<span data-ttu-id="50f2e-335">Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-335">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="50f2e-336">Observe que o navegador da Web oferece um arquivo zip para download.</span><span class="sxs-lookup"><span data-stu-id="50f2e-336">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="50f2e-337">Este arquivo contém o rastreamento de desempenho no formato PerfView.</span><span class="sxs-lookup"><span data-stu-id="50f2e-337">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="50f2e-338">Você pode então usar a ferramenta de análise de desempenho do PerfView para analisar os detalhes da execução do formato ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-338">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span>

![Informações de rastreamento para o formato ER executado em PerfView](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a><span data-ttu-id="50f2e-340">Use ferramentas externas para revisar um rastreamento de execução que inclua consultas a bancos de dados</span><span class="sxs-lookup"><span data-stu-id="50f2e-340">Use external tools to review an execution trace that includes database queries</span></span>

<span data-ttu-id="50f2e-341">Devido as melhorias feitas na estrutura de ER, o rastreamento de desempenho que é gerado no formato PerfView agora oferece mais detalhes sobre a execução do formato ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-341">Because of improvements that have been made to the ER framework, the performance trace that is generated in PerfView format now offers more details about ER format execution.</span></span> <span data-ttu-id="50f2e-342">No Microsoft Dynamics 365 for Finance and Operations versão 10.0.4 (julho de 2019), este rastreamento também pode incluir detalhes de consultas SQL executadas para o banco de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="50f2e-342">In Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019), this trace can also include details of executed SQL queries to the application database.</span></span>

### <a name="configure-user-parameters"></a><span data-ttu-id="50f2e-343">Configurar parâmetros de usuário</span><span class="sxs-lookup"><span data-stu-id="50f2e-343">Configure user parameters</span></span>

1. <span data-ttu-id="50f2e-344">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-344">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="50f2e-345">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-345">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="50f2e-346">Na caixa de diálogo **Parâmetros de usuário**, na seção **Rastreamento de execução**, defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="50f2e-346">In the **User parameters** dialog box, in the **Execution tracing** section, set the following parameters:</span></span>

    - <span data-ttu-id="50f2e-347">No campo **Formato de rastreamento de execução** , selecione **PerfView XML**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-347">In the **Execution trace format** field, select **PerfView XML**.</span></span>
    - <span data-ttu-id="50f2e-348">Defina a opção **Coletar estatísticas da consulta** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-348">Set the **Collect query statistics** option to **Yes**.</span></span>
    - <span data-ttu-id="50f2e-349">Defina a opção **Rastrear consulta** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="50f2e-349">Set the **Trace query** option to **Yes**.</span></span>

    ![Caixa de diálogo de parâmetros do usuário](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a><span data-ttu-id="50f2e-351">Executar o formato de ER</span><span class="sxs-lookup"><span data-stu-id="50f2e-351">Run the ER format</span></span>

<span data-ttu-id="50f2e-352">Repita as etapas na seção [Executar o formato de ER](#run-format) anterior neste tópico para gerar um novo rastreio de desempenho.</span><span class="sxs-lookup"><span data-stu-id="50f2e-352">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

<span data-ttu-id="50f2e-353">Observe que o navegador da Web oferece um arquivo zip para download.</span><span class="sxs-lookup"><span data-stu-id="50f2e-353">Notice that the web browser offers a zip file for download.</span></span> <span data-ttu-id="50f2e-354">Este arquivo contém o rastreamento de desempenho no formato PerfView.</span><span class="sxs-lookup"><span data-stu-id="50f2e-354">This file contains the performance trace in PerfView format.</span></span> <span data-ttu-id="50f2e-355">Você pode então usar a ferramenta de análise de desempenho do PerfView para analisar os detalhes da execução do formato ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-355">You can then use the PerfView performance analysis tool to analyze the details of ER format execution.</span></span> <span data-ttu-id="50f2e-356">Este rastreamento agora inclui os detalhes de acesso do banco de dados SQL durante a execução do formato ER.</span><span class="sxs-lookup"><span data-stu-id="50f2e-356">This trace now includes the details of SQL database access during the execution of the ER format.</span></span>

![Informações de rastreamento para o formato ER executado em PerfView](./media/GER-PerfTrace2-PerfViewTrace2.PNG)