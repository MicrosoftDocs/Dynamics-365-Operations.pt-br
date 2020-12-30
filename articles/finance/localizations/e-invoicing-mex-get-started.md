---
title: Introdução ao complemento de faturamento eletrônico para o México
description: Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico para o México no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6d15a79a359b3c708b2b33893d700377a57c3eb7
ms.sourcegitcommit: cfd84321fba38e02e270d361df369a536a48efa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "4512225"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-mexico"></a><span data-ttu-id="5ad34-103">Introdução ao complemento de faturamento eletrônico para o México</span><span class="sxs-lookup"><span data-stu-id="5ad34-103">Get started with the Electronic invoicing add-on for Mexico</span></span>

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="5ad34-104">O complemento de faturamento eletrônico para o México no momento talvez não ofereça suporte a todas as funções disponíveis no documento CFDI (Comprovante Fiscal Digital por Internet) e na integração relacionada incorporada ao Microsoft Dynamics 365 Finance ou ao Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5ad34-104">The Electronic invoicing add-on for Mexico might not currently support all the functions that are available in the Comprobante Fiscal Digital por Internet (CFDI) document, and in the related integration that is built into Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="5ad34-105">Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico para o México.</span><span class="sxs-lookup"><span data-stu-id="5ad34-105">This topic provides information that will help you get started with the Electronic invoicing add-on for Mexico.</span></span> <span data-ttu-id="5ad34-106">Ele o orienta você pelas etapas de configuração que dependem do país para os Regulatory Configuration Services (RCS) e no Finance.</span><span class="sxs-lookup"><span data-stu-id="5ad34-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="5ad34-107">Ele também o orienta pelas etapas que devem ser seguidas no Finance para enviar faturas de CFDI pelo serviço e explica como revisar os resultados do processamento e o status de faturas de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-107">It also guides you through the steps that you must follow in Finance to submit CFDI invoices through the service, and it explains how to review the processing results and the status of CFDI invoices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ad34-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5ad34-108">Prerequisites</span></span>

<span data-ttu-id="5ad34-109">Antes de concluir as etapas deste tópico, você deve concluir as etapas em [Introdução ao complemento do faturamento eletrônico](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="5ad34-109">Before you complete the steps in this topic, you must complete the steps in [Get started with the Electronic invoicing add-on](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="5ad34-110">Configuração do RCS</span><span class="sxs-lookup"><span data-stu-id="5ad34-110">RCS setup</span></span>

<span data-ttu-id="5ad34-111">Durante a configuração do RCS, você concluirá estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="5ad34-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="5ad34-112">Importe o recurso de faturamento eletrônico para processar faturas de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-112">Import the e-Invoicing feature for processing CFDI invoices.</span></span>
2. <span data-ttu-id="5ad34-113">Examine as configurações de formato necessárias para gerar, enviar e receber respostas sobre as faturas de CFDI e para enviar e receber respostas sobre o cancelamento.</span><span class="sxs-lookup"><span data-stu-id="5ad34-113">Review the format configurations that are required to generate, submit, and receive responses about CFDI invoices, and to submit and receive responses about cancellation.</span></span>
3. <span data-ttu-id="5ad34-114">Configure os eventos que dão suporte a cenários de envio de fatura de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-114">Configure the events that support the CFDI invoice submission scenarios.</span></span>
4. <span data-ttu-id="5ad34-115">Publique o recurso de faturamento eletrônico para faturas de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-115">Publish the e-Invoicing feature for CFDI invoices.</span></span>

> [!NOTE]
> <span data-ttu-id="5ad34-116">O "recurso de faturamento eletrônico" é o nome genérico do recurso configurado e publicado para consumir o servidor do complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5ad34-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing add-on server.</span></span> <span data-ttu-id="5ad34-117">Neste caso, as faturas de CFDI (MX) são o recurso de faturamento eletrônico que você configurará.</span><span class="sxs-lookup"><span data-stu-id="5ad34-117">In this case, CFDI invoices (MX) are the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="5ad34-118">Importar o recurso de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ad34-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="5ad34-119">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="5ad34-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="5ad34-120">No espaço de trabalho **Recursos de globalização**, na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="5ad34-121">Na página **Recursos de faturamento eletrônico**, selecione **Importar** para importar o recurso **Faturas de CFDI (MX)** do Repositório global.</span><span class="sxs-lookup"><span data-stu-id="5ad34-121">On the **e-Invoicing Features** page, select **Import** to import the **CFDI invoices (MX)** feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ad34-122">Se o recurso não for exibido na lista, selecione **Sincronizar** e repita a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="5ad34-122">If you don't see the feature in the list, select **Synchronize**, and then repeat step 3.</span></span>

![Importar o recurso Faturas de CFDI (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

<span data-ttu-id="5ad34-124">Quando você importa o recurso **Faturas de CFDI (MX)** do Repositório global, todas as definições do recurso, incluindo configurações e ações, também são importadas.</span><span class="sxs-lookup"><span data-stu-id="5ad34-124">When you import the **CFDI invoices (MX)** feature from the Global repository, all the feature settings, including configurations and actions, are also imported.</span></span>

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a><span data-ttu-id="5ad34-125">Criar uma nova versão do recurso Faturas de CFDI (MX)</span><span class="sxs-lookup"><span data-stu-id="5ad34-125">Create a new version of the CFDI invoices (MX) feature</span></span>

<span data-ttu-id="5ad34-126">Você poderá criar uma nova versão se, por exemplo, as URLs precisarem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="5ad34-126">You can create a new version if, for example, URLs must be updated.</span></span> <span data-ttu-id="5ad34-127">Para obter mais informações, consulte [Faturamento eletrônico CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span><span class="sxs-lookup"><span data-stu-id="5ad34-127">For more information, see [E-invoicing CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span></span>

- <span data-ttu-id="5ad34-128">Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-128">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span>

![Adicionar uma nova versão do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a><span data-ttu-id="5ad34-130">Atualizar a versão de configuração</span><span class="sxs-lookup"><span data-stu-id="5ad34-130">Update the configuration version</span></span>

1. <span data-ttu-id="5ad34-131">Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar** ou **Excluir** para gerenciar as versões de configuração (configurações do formato de arquivo ER).</span><span class="sxs-lookup"><span data-stu-id="5ad34-131">On the **e-Invoicing Features** page, on the **Configurations** tab, select **Add** or **Delete** to manage the configuration versions (ER file format configurations).</span></span>

    ![Gerenciar configurações do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    <span data-ttu-id="5ad34-133">Quando você cria uma nova versão, todas as configurações são herdadas da última versão publicada.</span><span class="sxs-lookup"><span data-stu-id="5ad34-133">When you create a new version, all configurations are inherited from the last published version.</span></span> <span data-ttu-id="5ad34-134">Para processar as faturas de CFDI, são necessárias as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5ad34-134">To process CFDI invoices, the following configurations are required:</span></span>

    - <span data-ttu-id="5ad34-135">Fatura de CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="5ad34-135">CFDI invoice (BusinessDocumentService)</span></span>
    - <span data-ttu-id="5ad34-136">Importação da mensagem de resposta de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-136">CFDI response message import</span></span>
    - <span data-ttu-id="5ad34-137">Importação de log de erros de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-137">CFDI error log import</span></span>
    - <span data-ttu-id="5ad34-138">Solicitação de cancelamento de CFDI (MX) (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="5ad34-138">CFDI cancelation request (MX) (BusinessDocumentService)</span></span>
    - <span data-ttu-id="5ad34-139">Fatura de CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="5ad34-139">CFDI invoice (BusinessDocumentService)</span></span>

2. <span data-ttu-id="5ad34-140">Na lista, selecione uma versão de configuração e, em seguida, selecione **Editar** ou **Exibir** para abrir a página **Designer de formato**, na qual você pode editar ou exibir a configuração.</span><span class="sxs-lookup"><span data-stu-id="5ad34-140">In the list, select a configuration version, and then select **Edit** or **View** to open the **Format designer** page, where you can edit or view the configuration.</span></span>

    ![Abrir a página Designer de formato](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. <span data-ttu-id="5ad34-142">Use a página **Designer de formato** para editar e exibir as configurações do arquivo de formato ER.</span><span class="sxs-lookup"><span data-stu-id="5ad34-142">Use the **Format designer** page to edit and view the ER format file configurations.</span></span> <span data-ttu-id="5ad34-143">Para obter mais informações, consulte [Criar configurações do documento eletrônico](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5ad34-143">For more information, see [Create electronic document configurations](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span></span>

    ![Página do designer de formatos](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="5ad34-145">Gerenciar as configurações do recurso de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ad34-145">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="5ad34-146">Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar**, **Excluir** ou **Editar** para gerenciar as configurações do recurso de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5ad34-146">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Gerenciar as configurações do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

<span data-ttu-id="5ad34-148">Para enviar faturas de CFDI para autorização (gerar o arquivo XML, enviar o arquivo XML e processar a resposta), é necessário configurar o recurso **Fatura de venda**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-148">To submit CFDI invoices for authorization (generate the XML file, submit the XML file, and process the response), the **Sales invoice** feature setup is required.</span></span>

<span data-ttu-id="5ad34-149">Para enviar o cancelamento da fatura de CFDI, são necessárias as configurações de recurso **Cancelamento** e **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-149">To submit CFDI invoice cancellation, the **Cancellation** and **Cancel** feature setups are required.</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="5ad34-150">Definir a configuração do recurso de fatura de venda</span><span class="sxs-lookup"><span data-stu-id="5ad34-150">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="5ad34-151">Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, na coluna **Configuração do recurso**, selecione **Fatura de venda**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-151">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="5ad34-152">Selecione **Editar** para configurar as ações, regras de aplicabilidade e variáveis.</span><span class="sxs-lookup"><span data-stu-id="5ad34-152">Select **Edit** to configure the actions, applicability rules, and variables.</span></span>

    ![Editar a configuração do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. <span data-ttu-id="5ad34-154">Na página **Configuração de versão do recurso**, selecione a guia **Ações** para gerenciar a lista de ações.</span><span class="sxs-lookup"><span data-stu-id="5ad34-154">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="5ad34-155">As ações definem uma lista de operações que devem ser executadas na ordem sequencial para realizar a execução total do evento.</span><span class="sxs-lookup"><span data-stu-id="5ad34-155">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Guia Ações](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | <span data-ttu-id="5ad34-157">ID de ação</span><span class="sxs-lookup"><span data-stu-id="5ad34-157">Action ID</span></span> | <span data-ttu-id="5ad34-158">Ação</span><span class="sxs-lookup"><span data-stu-id="5ad34-158">Action</span></span>                   | <span data-ttu-id="5ad34-159">Nome da ação</span><span class="sxs-lookup"><span data-stu-id="5ad34-159">Action name</span></span>                                  | <span data-ttu-id="5ad34-160">Descrição da ação</span><span class="sxs-lookup"><span data-stu-id="5ad34-160">Action description</span></span>                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | <span data-ttu-id="5ad34-161">1</span><span class="sxs-lookup"><span data-stu-id="5ad34-161">1</span></span>         | <span data-ttu-id="5ad34-162">Transformar documento</span><span class="sxs-lookup"><span data-stu-id="5ad34-162">Transform document</span></span>       | <span data-ttu-id="5ad34-163">Gerar fatura eletrônica de CFDI sem assinatura digital</span><span class="sxs-lookup"><span data-stu-id="5ad34-163">Generate CFDI E-Invoice without digital sign</span></span> | <span data-ttu-id="5ad34-164">Gerar fatura eletrônica de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-164">Generate the CFDI e-invoice.</span></span>                                |
    | <span data-ttu-id="5ad34-165">2</span><span class="sxs-lookup"><span data-stu-id="5ad34-165">2</span></span>         | <span data-ttu-id="5ad34-166">Assinar documento</span><span class="sxs-lookup"><span data-stu-id="5ad34-166">Sign document</span></span>            | <span data-ttu-id="5ad34-167">Assinatura digital</span><span class="sxs-lookup"><span data-stu-id="5ad34-167">Digital sign</span></span>                                 | <span data-ttu-id="5ad34-168">Assinar digitalmente a fatura eletrônica para envio.</span><span class="sxs-lookup"><span data-stu-id="5ad34-168">Digitally sign the e-invoice for submission.</span></span>                |
    | <span data-ttu-id="5ad34-169">3</span><span class="sxs-lookup"><span data-stu-id="5ad34-169">3</span></span>         | <span data-ttu-id="5ad34-170">Chamar serviço da PAC mexicana</span><span class="sxs-lookup"><span data-stu-id="5ad34-170">Call Mexican PAC service</span></span> | <span data-ttu-id="5ad34-171">Enviar fatura eletrônica de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-171">Submit CFDI E-Invoice</span></span>                        | <span data-ttu-id="5ad34-172">O cliente Windows Communication Foundation (WCF) envia a fatura eletrônica de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-172">The Windows Communication Foundation (WCF) client submits the CFDI e-invoice.</span></span> |
    | <span data-ttu-id="5ad34-173">4</span><span class="sxs-lookup"><span data-stu-id="5ad34-173">4</span></span>         | <span data-ttu-id="5ad34-174">Processar resposta</span><span class="sxs-lookup"><span data-stu-id="5ad34-174">Process response</span></span>         | <span data-ttu-id="5ad34-175">Analisar resposta do serviço Web</span><span class="sxs-lookup"><span data-stu-id="5ad34-175">Analyze web service response</span></span>                 | <span data-ttu-id="5ad34-176">Analise a resposta do serviço Web e retorne o log de erros.</span><span class="sxs-lookup"><span data-stu-id="5ad34-176">Analyze the web service response, and return the error log.</span></span> |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a><span data-ttu-id="5ad34-177">Configurar a URL para serviços Web da PAC mexicana</span><span class="sxs-lookup"><span data-stu-id="5ad34-177">Set up the URL for Mexican PAC web services</span></span> 

1. <span data-ttu-id="5ad34-178">Na página **Configuração de versão do recurso**, na guia **Ações**, na Guia Rápida **Ações**, selecione **Chamar serviço da PAC mexicana**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-178">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Mexican PAC service**.</span></span>
2. <span data-ttu-id="5ad34-179">Na Guia Rápida **Parâmetros**, no campo **Endereço da URL**, insira a URL do serviço Web para envio da fatura de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-179">On the **Parameters** FastTab, in the **URL address** field, enter the URL of the web service for CFDI invoice submission.</span></span>

> [!NOTE]
> <span data-ttu-id="5ad34-180">Use as mesmas etapas para atualizar a URL para a ação **Chamar serviço da PAC mexicana** para as configurações de recurso **Cancelar** e **Solicitação de cancelamento**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-180">Use the same steps to update the URL for **Call Mexican PAC service** action for the **Cancel** and **Cancelation request** feature setups.</span></span>

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a><span data-ttu-id="5ad34-181">Atribuir a versão de rascunho a um ambiente de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ad34-181">Assign the Draft version to an e-Invoicing environment</span></span>

1. <span data-ttu-id="5ad34-182">Na página **Recursos de faturamento eletrônico**, na guia **Ambientes**, selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-182">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="5ad34-183">No campo **Ambiente**, selecione o ambiente.</span><span class="sxs-lookup"><span data-stu-id="5ad34-183">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="5ad34-184">No campo **Efetivo a partir de**, selecione a data em que o ambiente deve entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="5ad34-184">In the **Effective from** field, select the date when the environment should become effective.</span></span>
3. <span data-ttu-id="5ad34-185">Selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-185">Select **Enable**.</span></span>

![Habilitar um ambiente de faturamento eletrônico](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a><span data-ttu-id="5ad34-187">Alterar o status da versão para Concluído</span><span class="sxs-lookup"><span data-stu-id="5ad34-187">Change the version status to Completed</span></span>

1. <span data-ttu-id="5ad34-188">Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-188">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="5ad34-189">Selecione **Alterar status \> Concluir**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-189">Select **Change status \> Complete**.</span></span>

## <a name="change-the-version-status-to-published"></a><span data-ttu-id="5ad34-190">Alterar o status da versão para Publicado</span><span class="sxs-lookup"><span data-stu-id="5ad34-190">Change the version status to Published</span></span>

- <span data-ttu-id="5ad34-191">Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione **Alterar status \> Publicar**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-191">On the **e-Invoicing Features** page, on the **Versions** tab, select **Change status \> Publish**.</span></span>

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="5ad34-192">Publicar o recurso de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ad34-192">Publish the e-Invoicing feature</span></span>

1. <span data-ttu-id="5ad34-193">Na página **Recursos de faturamento eletrônico**, selecione a guia **Versões** para gerenciar o status do recurso **Faturas de CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-193">On the **e-Invoicing Features** page, select the **Versions** tab to manage the status of the **CFDI invoices (MX)** feature.</span></span>
2. <span data-ttu-id="5ad34-194">Selecione **Alterar status** para alterar o status do recurso.</span><span class="sxs-lookup"><span data-stu-id="5ad34-194">Select **Change status** to change the status of the feature.</span></span>

![Alterar o status do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance"></a><span data-ttu-id="5ad34-196">Configurar integração do complemento de faturamento eletrônico no Finance</span><span class="sxs-lookup"><span data-stu-id="5ad34-196">Set up Electronic invoicing add-on integration in Finance</span></span>

<span data-ttu-id="5ad34-197">Para configurar o complemento de faturamento eletrônico no Finance, você executará estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="5ad34-197">To set up the Electronic invoicing add-on in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="5ad34-198">Importe o modelo de dados ER, o mapeamento do modelo de dados ER e os formatos necessários para faturas de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-198">Import the ER data model, the ER data model mapping, and the formats that are required for CFDI invoices.</span></span>
2. <span data-ttu-id="5ad34-199">Configure tipos de resposta para atualizar as faturas de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-199">Configure response types for updating the CFDI invoices.</span></span> <span data-ttu-id="5ad34-200">Esses tipos de respostas são usados para a resposta do servidor PAC (provedor de certificação autorizado).</span><span class="sxs-lookup"><span data-stu-id="5ad34-200">These response types are used for the response from the authorized certification provider (PAC) server.</span></span>

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a><span data-ttu-id="5ad34-201">Importar o modelo de dados ER, o mapeamento do modelo de dados ER e as configurações de contexto para faturas de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-201">Import the ER data model, ER data model mapping, and context configurations for CFDI invoices</span></span>

1. <span data-ttu-id="5ad34-202">Entre no Finance.</span><span class="sxs-lookup"><span data-stu-id="5ad34-202">Sign in to Finance.</span></span>
2. <span data-ttu-id="5ad34-203">No espaço de trabalho **Relatório eletrônico**, na seção **Provedores de configuração**, selecione o título **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-203">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span> <span data-ttu-id="5ad34-204">Verifique se este provedor de configuração está definido como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-204">Make sure that this configuration provider is set to **Active**.</span></span> <span data-ttu-id="5ad34-205">Para obter informações sobre como definir um provedor como **Ativo**, consulte [Criar provedores de configuração e marcá-los como ativos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="5ad34-205">For information about how to set a provider to **Active**, see [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span></span>
3. <span data-ttu-id="5ad34-206">Selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-206">Select **Repositories**.</span></span>
4. <span data-ttu-id="5ad34-207">Selecione **Recurso global \> Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-207">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="5ad34-208">Importar **Modelo de fatura**, **Mapeamento de modelo de fatura**, **Formato de fatura de CFDI (MX)**, **Formato de solicitação de cancelamento de fatura de CFDI (MX)** e **Formato de cancelamento de fatura de CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-208">Import **Invoice model**, **Invoice model mapping**, **CFDI invoice format (MX)**, **CFDI invoice cancelation request format (MX)**, and **CFDI invoice cancel format (MX)**.</span></span>

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a><span data-ttu-id="5ad34-209">Ativar o recurso de processamento de faturas de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-209">Turn on the feature for processing CFDI invoices</span></span>

1. <span data-ttu-id="5ad34-210">Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="5ad34-211">Na guia **Recursos**, marque a caixa de seleção **Habilitar** nas linhas para referências do recurso **MX-00010** e **MX-00016**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-211">On the **Features** tab, select the **Enable** check box in the rows for feature references **MX-00010** and **MX-00016**.</span></span>

![Ativar os recursos de processamento de faturas de CFDI](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a><span data-ttu-id="5ad34-213">Importar configurações de ER e configurar os tipos de resposta para atualizar faturas de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-213">Import ER configurations and set up the response types for updating CFDI invoices</span></span>

#### <a name="import-er-configurations"></a><span data-ttu-id="5ad34-214">Importar configurações de ER</span><span class="sxs-lookup"><span data-stu-id="5ad34-214">Import ER configurations</span></span>

1. <span data-ttu-id="5ad34-215">No espaço de trabalho **Relatório eletrônico**, na seção **Provedores de configuração**, selecione o título **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-215">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span>
3. <span data-ttu-id="5ad34-216">Selecione **Repositórios**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-216">Select **Repositories**.</span></span>
4. <span data-ttu-id="5ad34-217">Selecione **Recurso global \> Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-217">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="5ad34-218">Importe **Modelo de mensagem de resposta**, **Importação de log de erros de CFDI (MX)**, **Importação de log de erros (MX)**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-218">Import **Response message model**, **CFDI error log import (MX)**, and **CFDI response message import (MX)**.</span></span>

#### <a name="set-up-the-response-types"></a><span data-ttu-id="5ad34-219">Configurar os tipos de resposta</span><span class="sxs-lookup"><span data-stu-id="5ad34-219">Set up the response types</span></span>

1. <span data-ttu-id="5ad34-220">Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-220">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="5ad34-221">Na guia **Documento eletrônico**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-221">On the **Electronic document** tab, select **Add**.</span></span>
3. <span data-ttu-id="5ad34-222">Insira o diário de faturas do cliente e, em seguida, no campo **Nome da tabela**, selecione a fatura do projeto.</span><span class="sxs-lookup"><span data-stu-id="5ad34-222">Enter the customer invoice journal, and then, in the **Table name** field, select the project invoice.</span></span>
4. <span data-ttu-id="5ad34-223">Para cada tabela, defina um contexto de documento relacionado:</span><span class="sxs-lookup"><span data-stu-id="5ad34-223">For each table, define a related document context:</span></span>

    - <span data-ttu-id="5ad34-224">Para **Diário de faturas de clientes**, insira **Contexto de fatura de cliente**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-224">For **Customer invoice journal**, enter **Customer invoice context**.</span></span>
    - <span data-ttu-id="5ad34-225">Para **Fatura de projeto**, insira **Contexto de fatura de projeto**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-225">For **Project invoice**, enter **Project invoice context**.</span></span>

4. <span data-ttu-id="5ad34-226">Selecione **Tipos de resposta** para configurar os tipos de resposta que podem ser retornados do complemento de faturamento eletrônico e incluídos em um diário de faturas de clientes ou em uma fatura de projeto.</span><span class="sxs-lookup"><span data-stu-id="5ad34-226">Select **Response types** to configure the response types that can be returned from the Electronic invoicing add-on and included in a customer invoice journal or project invoice.</span></span>
5. <span data-ttu-id="5ad34-227">Selecione **Novo** e, no campo **Tipo de resposta**, selecione **Resposta**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-227">Select **New**, and then, in the **Response type** field, select **Response**.</span></span>
6. <span data-ttu-id="5ad34-228">No campo **Status de envio**, selecione **Pendente**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-228">In the **Submission status** field, select **Pending**.</span></span>
7. <span data-ttu-id="5ad34-229">No campo **Mapeamento de modelos**, selecione **Formato de importação de mensagem de resposta – mapeamento de modelo da mensagem de resposta**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-229">In the **Model mapping** field, select **Response message import format – Model mapping from response message**.</span></span>
8. <span data-ttu-id="5ad34-230">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-230">Select **Save**.</span></span>
9. <span data-ttu-id="5ad34-231">Selecione **Novo** e, no campo **Tipo de resposta**, selecione **ResponseData**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-231">Select **New**, and then, in the **Response type** field, select **ResponseData**.</span></span>
10. <span data-ttu-id="5ad34-232">No campo **Status de envio**, selecione **Pendente**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-232">In the **Submission status** field, select **Pending**.</span></span>
11. <span data-ttu-id="5ad34-233">No campo **Mapeamento de modelos**, selecione **Formato de importação de dados de resposta de CFDI (detalhes) – importação dos dados de resposta**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-233">In the **Model mapping** field, select **CFDI response data import format (details) – Response data import**.</span></span>
12. <span data-ttu-id="5ad34-234">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-234">Select **Save**.</span></span>

## <a name="process-electronic-invoices-in-finance"></a><span data-ttu-id="5ad34-235">Processar faturas eletrônicas no Finance</span><span class="sxs-lookup"><span data-stu-id="5ad34-235">Process electronic invoices in Finance</span></span> 

<span data-ttu-id="5ad34-236">Durante o processamento de faturas de CFDI no Finance por meio do complemento do faturamento eletrônico, você pode executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="5ad34-236">During the processing of CFDI invoices in Finance through the Electronic invoicing add-on, you can perform the following tasks:</span></span>

- <span data-ttu-id="5ad34-237">Envie faturas de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-237">Submit CFDI invoices.</span></span>
- <span data-ttu-id="5ad34-238">Exiba os logs de execução de envio.</span><span class="sxs-lookup"><span data-stu-id="5ad34-238">View the submission execution logs.</span></span>
- <span data-ttu-id="5ad34-239">Envie o cancelamento de uma fatura de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-239">Submit the cancellation of a CFDI invoice.</span></span>

### <a name="submit-cfdi-invoices"></a><span data-ttu-id="5ad34-240">Enviar faturas de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-240">Submit CFDI invoices</span></span>

<span data-ttu-id="5ad34-241">Depois que você ativar o recurso **Integração do complemento de faturamento eletrônico configurável**, o processo **Exportar/Importar fatura eletrônica** (**Contas a receber \> Faturas \> Faturas eletrônicas**) para enviar faturas de CFDI não poderá mais ser usado.</span><span class="sxs-lookup"><span data-stu-id="5ad34-241">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the **Export/Import electronic invoice** process (**Accounts receivable \> Invoices \> E-invoices**) for submitting CFDI invoices can no longer be used.</span></span> <span data-ttu-id="5ad34-242">Ele é substituído por um novo processo chamado **Enviar documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-242">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

> [!NOTE]
> <span data-ttu-id="5ad34-243">Antes de usar o novo processo **Enviar documentos eletrônicos**, verifique se a configuração necessária para faturas eletrônicas mexicanas foi concluída.</span><span class="sxs-lookup"><span data-stu-id="5ad34-243">Before you use the new **Submit electronic documents** process, verify that the setup that is required for Mexican e-invoices was completed.</span></span> <span data-ttu-id="5ad34-244">Para obter mais informações, consulte [Layout do CFDI versão 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span><span class="sxs-lookup"><span data-stu-id="5ad34-244">For more information, see [CFDI layout version 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span></span>

1. <span data-ttu-id="5ad34-245">Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Enviar documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-245">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="5ad34-246">Para o primeiro envio de qualquer documento, sempre defina a opção **Reenviar documentos** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-246">For the first submission of any document, always set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="5ad34-247">Se você precisar reenviar um documento pelo serviço, defina esta opção como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-247">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="5ad34-248">Na Guia Rápida **Registros a serem incluídos**, selecione **Filtrar** para abrir a caixa de diálogo **Consulta**, na qual você pode criar uma consulta para selecionar documentos para envio.</span><span class="sxs-lookup"><span data-stu-id="5ad34-248">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Enviar um documento de CFDI](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> <span data-ttu-id="5ad34-250">Na primeira tentativa de enviar um documento pelo serviço, você será solicitado a confirmar a conexão com o complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5ad34-250">During your first attempt to submit a document through the service, you will be prompted to confirm the connection with the Electronic invoicing add-on.</span></span> <span data-ttu-id="5ad34-251">Selecione **Clique aqui para se conectar ao serviço de envio de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-251">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

### <a name="view-submission-logs"></a><span data-ttu-id="5ad34-252">Exibir logs de envio</span><span class="sxs-lookup"><span data-stu-id="5ad34-252">View submission logs</span></span>

<span data-ttu-id="5ad34-253">Você pode exibir os logs de envio para todos os documentos enviados ou apenas para um documento enviado.</span><span class="sxs-lookup"><span data-stu-id="5ad34-253">You can view the submission logs for all submitted documents or for just one submitted document.</span></span>

#### <a name="view-all-submission-logs"></a><span data-ttu-id="5ad34-254">Exibir todos os logs de envio</span><span class="sxs-lookup"><span data-stu-id="5ad34-254">View all submission logs</span></span>

<span data-ttu-id="5ad34-255">Depois que ativar o recurso **Integração do complemento de faturamento eletrônico configurável**, uma nova página será disponibilizar que permitirá acompanhar o processo de envio do documento.</span><span class="sxs-lookup"><span data-stu-id="5ad34-255">After you turn on the **Configurable Electronic invoicing add-on integration** feature, a new page is available that lets you follow up on the document submission process.</span></span> <span data-ttu-id="5ad34-256">Você pode usar esta página para exibir os logs de envio para todos os documentos enviados.</span><span class="sxs-lookup"><span data-stu-id="5ad34-256">You can use this page to view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="5ad34-257">Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-257">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="5ad34-258">No campo **Tipo de documento**, selecione **Diário de faturas de clientes** para filtrar os documentos eletrônicos necessários.</span><span class="sxs-lookup"><span data-stu-id="5ad34-258">In the **Document type** field, select **Customer invoice journal** to filter for the required electronic documents.</span></span>

    ![Selecionar um tipo de documento para exibir os logs de envio](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. <span data-ttu-id="5ad34-260">No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.</span><span class="sxs-lookup"><span data-stu-id="5ad34-260">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Exibir os detalhes do log de envio](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

<span data-ttu-id="5ad34-262">As informações nos logs de envio são divididas entre as três FastTabs:</span><span class="sxs-lookup"><span data-stu-id="5ad34-262">The information in the submission logs is divided among three FastTabs:</span></span>

- <span data-ttu-id="5ad34-263">**Ações de processamento** – esta Guia Rápida mostra o log de execução para as ações configuradas na versão do recurso que foi configurada no RCS.</span><span class="sxs-lookup"><span data-stu-id="5ad34-263">**Processing actions** – This FastTab shows the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="5ad34-264">A coluna **Status** mostra se a ação foi executada com êxito.</span><span class="sxs-lookup"><span data-stu-id="5ad34-264">The **Status** column shows whether the action was successfully run.</span></span>
- <span data-ttu-id="5ad34-265">**Arquivos de ação** – esta Guia Rápida mostra os arquivos intermediários que foram gerados durante a execução das ações.</span><span class="sxs-lookup"><span data-stu-id="5ad34-265">**Action files** – This FastTab shows the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="5ad34-266">Você pode selecionar **Exibir** para baixar e exibir o arquivo.</span><span class="sxs-lookup"><span data-stu-id="5ad34-266">You can select **View** to download and view the file.</span></span>
- <span data-ttu-id="5ad34-267">**Log de ação de processamento** – esta Guia Rápida mostra os resultados da comunicação entre o complemento do faturamento eletrônico e o serviço Web de destino.</span><span class="sxs-lookup"><span data-stu-id="5ad34-267">**Processing action log** – This FastTab shows the results of the communication between the Electronic invoicing add-on and the target web service.</span></span> <span data-ttu-id="5ad34-268">Ela também mostra o que foi retornado pelo processamento do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="5ad34-268">It also shows what was returned by the processing from the web service.</span></span> <span data-ttu-id="5ad34-269">A coluna **Código de erro** mostra o código de retorno que foi retornado pelo serviço Web de autorização.</span><span class="sxs-lookup"><span data-stu-id="5ad34-269">The **Error code** column shows the return code that was returned by the authorization web service.</span></span>

<span data-ttu-id="5ad34-270">Quando a fatura de CFDI enviada é autorizada, o status é atualizado para **Aprovado**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-270">When the submitted CFDI invoice is authorized, its status is updated to **Approved**.</span></span>

#### <a name="view-submission-logs-from-cfdi-invoices"></a><span data-ttu-id="5ad34-271">Exibir logs de envio de faturas de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-271">View submission logs from CFDI invoices</span></span>

<span data-ttu-id="5ad34-272">Depois que ativar o recurso **Integração do complemento de faturamento eletrônico configurável**, você também poderá exibir os logs de envio de faturas de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-272">After you turn on the **ConfigurableElectronic invoicing add-on integration** feature, you can also view the submission logs from CFDI invoices.</span></span>

1. <span data-ttu-id="5ad34-273">Vá para **Contas a receber \> Consultas e relatórios \> CFDI (faturas eletrônicas)**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-273">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="5ad34-274">Selecione uma fatura de CFDI que foi enviada após a ativação do recurso **Integração do complemento de faturamento eletrônico configurável**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-274">Select a CFDI invoice that was submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>
3. <span data-ttu-id="5ad34-275">No Painel de Ações, na guia **Histórico**, selecione **Registro de documento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-275">On the Action Pane, on the **History** tab, select **Electronic document log**.</span></span>

![Exibir logs de envio de faturas de CFDI](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> <span data-ttu-id="5ad34-277">Para faturas de CFDI enviadas antes da ativação do recurso **Integração de complemento de faturamento eletrônico configurável**, o botão **Histórico** está disponível.</span><span class="sxs-lookup"><span data-stu-id="5ad34-277">For CFDI invoices that were submitted before the **Configurable Electronic invoicing add-on integration** feature was turned on, the **History** button is available.</span></span> <span data-ttu-id="5ad34-278">O botão **Histórico** não está disponível para faturas de CFDI enviadas após a ativação do recurso **Integração de complemento de faturamento eletrônico configurável**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-278">The **History** button isn't available for CFDI invoices that were submitted after the **Configurable Electronic invoicing add-on integration** feature was turned on.</span></span>

### <a name="submit-cancellation-of-cfdi-invoices"></a><span data-ttu-id="5ad34-279">Enviar cancelamento de faturas de CFDI</span><span class="sxs-lookup"><span data-stu-id="5ad34-279">Submit cancellation of CFDI invoices</span></span>

<span data-ttu-id="5ad34-280">Depois que você ativar o recurso **Integração do complemento de faturamento eletrônico configurável**, o processo antigo de cancelamento de faturas de CFDI não poderá mais ser usado.</span><span class="sxs-lookup"><span data-stu-id="5ad34-280">After you turn on the **Configurable Electronic invoicing add-on integration** feature, the old process for canceling CFDI invoices can no longer be used.</span></span> <span data-ttu-id="5ad34-281">Ele é substituído por um novo processo de cancelamento incorporado na página **Registro de envio de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-281">It's replaced by a new cancellation process that is embedded on the **Electronic document submission log** page.</span></span>

1. <span data-ttu-id="5ad34-282">Vá para **Contas a receber \> Consultas e relatórios \> CFDI (faturas eletrônicas)**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-282">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="5ad34-283">Se a fatura de CFDI tiver um status **Aprovado**, selecione **Funções \> Cancelar CFDI**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-283">If the CFDI invoice has a status of **Approved**, select **Functions \> Cancel CFDI**.</span></span>
3. <span data-ttu-id="5ad34-284">Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-284">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
4. <span data-ttu-id="5ad34-285">Selecione a fatura de CFDI e selecione **Funções \> Enviar envios relacionados**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-285">Select the CFDI invoice, and then select **Functions \> Send related submissions**.</span></span>
5. <span data-ttu-id="5ad34-286">Insira uma descrição do envio relacionado e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-286">Enter a description for the related submission, and then select **OK**.</span></span>

#### <a name="view-cancellation-submission-logs"></a><span data-ttu-id="5ad34-287">Exibir logs de envio de cancelamento</span><span class="sxs-lookup"><span data-stu-id="5ad34-287">View cancellation submission logs</span></span>

1. <span data-ttu-id="5ad34-288">Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-288">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="5ad34-289">No campo **Tipo de documento**, selecione **Diário de faturas de clientes** para filtrar apenas por documentos do diário de faturas do cliente.</span><span class="sxs-lookup"><span data-stu-id="5ad34-289">In the **Document type** field, select **Customer invoice journal** to filter for customer invoice journal documents only.</span></span>
3. <span data-ttu-id="5ad34-290">Selecione a fatura de CFDI e, no Painel de Ações, selecione **Consultas \> Envio relacionado**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-290">Select the CFDI invoice, and then, on the Action Pane, select **Inquiries \> Related submission**.</span></span>

    <span data-ttu-id="5ad34-291">A página **Envios relacionados** mostra todas os envios relacionados e o status do envio de determinada fatura de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-291">The **Related submissions** page shows all related submissions, and their submission status, for a given CFDI invoice.</span></span> <span data-ttu-id="5ad34-292">Na ilustração a seguir, a primeira linha representa o envio que solicitou aprovação da fatura de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-292">In the following illustration, the first line represents the submission that requested approval of the CFDI invoice.</span></span> <span data-ttu-id="5ad34-293">A segunda linha representa o envio que cancelou essa fatura de CFDI.</span><span class="sxs-lookup"><span data-stu-id="5ad34-293">The second line represents the submission that canceled that CFDI invoice.</span></span>

    ![Exibir os logs de envio de cancelamento](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. <span data-ttu-id="5ad34-295">No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.</span><span class="sxs-lookup"><span data-stu-id="5ad34-295">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Exibir os detalhes do log de envio de cancelamento](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a><span data-ttu-id="5ad34-297">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="5ad34-297">Privacy notice</span></span>
<span data-ttu-id="5ad34-298">Habilitar os recursos MX-00010 e MX-00016 (fatura de CFDI e cancelamento de CFDI) pode exigir o envio de dados limitados, que inclui a ID de registro de imposto da organização.</span><span class="sxs-lookup"><span data-stu-id="5ad34-298">Enabling the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features may require sending limited data, which includes the organization tax registration ID.</span></span> <span data-ttu-id="5ad34-299">Isso será transmitido a agências de terceiros autorizadas pela autoridade fiscal com a finalidade de enviar faturas eletrônicas a essa autoridade fiscal no formato predefinido exigido para integração com o serviço Web do governo.</span><span class="sxs-lookup"><span data-stu-id="5ad34-299">This will be transmitted to third-party agencies authorized by the tax authority for purposes of sending electronic invoices to this tax authority in the predefined format required for integration with the government’s web service.</span></span> <span data-ttu-id="5ad34-300">Um administrador pode habilitar e desabilitar os recursos MX-00010 e MX-00016 (fatura de CFDI e cancelamento de CFDI) navegando para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="5ad34-300">An administrator can enable and disable the MX-00010 and MX-00016 (CFDI Invoice and CFDI Cancellation) features by navigating to **Organization administration \> Setup \> Electronic document parameters**.</span></span> <span data-ttu-id="5ad34-301">Selecione a guia **Recursos**, selecione as linhas que contêm os recursos MX-00010 e MX-00016 e, em seguida, faça a seleção apropriada.</span><span class="sxs-lookup"><span data-stu-id="5ad34-301">Select the **Features** tab, select the rows containing the MX-00010 and MX-00016 features, and then make the appropriate selection.</span></span> <span data-ttu-id="5ad34-302">Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132).</span><span class="sxs-lookup"><span data-stu-id="5ad34-302">Data imported from these external systems into this Dynamics 365 online service are subject to our [privacy statement](https://go.microsoft.com/fwlink/?LinkId=512132).</span></span> <span data-ttu-id="5ad34-303">Consulte as seções de aviso de privacidade da documentação de recursos específicos do país para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5ad34-303">Consult the Privacy notice sections in country-specific feature documentation for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ad34-304">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5ad34-304">Additional resources</span></span>

- [<span data-ttu-id="5ad34-305">Visão geral do complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ad34-305">Electronic invoicing add-on overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="5ad34-306">Introdução ao complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ad34-306">Get started with the Electronic invoicing add-on</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="5ad34-307">Configurar o complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="5ad34-307">Set up the Electronic invoicing add-on</span></span>](e-invoicing-setup.md)
