---
title: Introdução à administração de serviço do complemento do faturamento eletrônico
description: Este tópico explica como começar a usar o complemento de faturamento eletrônico.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104343"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="9f330-103">Introdução à administração de serviço do complemento do faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="9f330-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="9f330-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9f330-104">Prerequisites</span></span>

<span data-ttu-id="9f330-105">Antes de concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:</span><span class="sxs-lookup"><span data-stu-id="9f330-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="9f330-106">Você deve ter acesso à conta do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="9f330-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="9f330-107">Você deve ter um projeto LCS que inclua a versão 10.0.13 ou posterior do Microsoft Dynamics 365 Finance e o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9f330-107">You must have an LCS project that includes version 10.0.13 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="9f330-108">Além disso, esses aplicativos devem ser implantados em uma das seguintes regiões geográficas do Azure:</span><span class="sxs-lookup"><span data-stu-id="9f330-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="9f330-109">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="9f330-109">East US</span></span>
    - <span data-ttu-id="9f330-110">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="9f330-110">West US</span></span>
    - <span data-ttu-id="9f330-111">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="9f330-111">North EU</span></span>
    - <span data-ttu-id="9f330-112">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="9f330-112">West EU</span></span>

- <span data-ttu-id="9f330-113">Você deve ter acesso à conta do Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="9f330-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="9f330-114">Você deve ativar o recurso Globalização para a conta RCS no Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="9f330-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="9f330-115">Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="9f330-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="9f330-116">Você deve criar um cofre de chaves e uma conta de armazenamento no Azure.</span><span class="sxs-lookup"><span data-stu-id="9f330-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="9f330-117">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="9f330-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="9f330-118">Instalar o complemento para microsserviços no Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="9f330-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="9f330-119">Entre em sua conta do LCS.</span><span class="sxs-lookup"><span data-stu-id="9f330-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="9f330-120">Selecione o bloco **Gerenciamento de versão prévia do recurso**.</span><span class="sxs-lookup"><span data-stu-id="9f330-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="9f330-121">Na seção **Recursos da versão preliminar pública**, selecione **Serviço de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="9f330-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="9f330-122">Verifique se a opção **Versão prévia do recurso habilitada** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9f330-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="9f330-123">Configure os parâmetros da integração do RCS com o complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="9f330-123">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="9f330-124">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="9f330-124">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="9f330-125">No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="9f330-125">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="9f330-126">Na guia **Serviço de faturamento eletrônico**, no campo **URI de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado para sua geografia do Azure, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9f330-126">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="9f330-127">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="9f330-127">Datacenter Azure geography</span></span> | <span data-ttu-id="9f330-128">URI do ponto de extremidade do serviço</span><span class="sxs-lookup"><span data-stu-id="9f330-128">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="9f330-129">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="9f330-129">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9f330-130">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="9f330-130">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9f330-131">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="9f330-131">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9f330-132">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="9f330-132">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="9f330-133">Verifique se o campo **ID do Aplicativo** está definido como **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="9f330-133">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="9f330-134">Esse valor é um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="9f330-134">This value is a fixed value.</span></span>
5. <span data-ttu-id="9f330-135">No campo **ID de Ambiente do LCS**, insira a ID da conta de assinatura do LCS.</span><span class="sxs-lookup"><span data-stu-id="9f330-135">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="9f330-136">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f330-136">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="9f330-137">Criar segredo do Key Vault</span><span class="sxs-lookup"><span data-stu-id="9f330-137">Create Key Vault secret</span></span>

1. <span data-ttu-id="9f330-138">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="9f330-138">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="9f330-139">No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="9f330-139">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="9f330-140">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** e **Parâmetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="9f330-140">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="9f330-141">Selecione **Novo** para criar um segredo de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="9f330-141">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="9f330-142">No campo **Nome**, insira o nome do segredo de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="9f330-142">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="9f330-143">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="9f330-143">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="9f330-144">No campo **URI do Key Vault**, cole o segredo do Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="9f330-144">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="9f330-145">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9f330-145">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="9f330-146">Criar segredo da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="9f330-146">Create Storage account secret</span></span>

1. <span data-ttu-id="9f330-147">Na página **Parâmetros do cofre de chaves**, na seção **Certificados**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9f330-147">On **Key vault parameters** page, in the **Certificates** section, select **Add**.</span></span>
2. <span data-ttu-id="9f330-148">No campo **Nome**, insira o nome do segredo da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9f330-148">In the **Name** field, enter the same of the storage account secret.</span></span> <span data-ttu-id="9f330-149">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="9f330-149">In the **Description** field, enter a description.</span></span>
3. <span data-ttu-id="9f330-150">No campo **Tipo**, selecione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="9f330-150">In the **Type** field, select **Certificate**.</span></span>
4. <span data-ttu-id="9f330-151">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f330-151">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="9f330-152">Criar um ambiente de Complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="9f330-152">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="9f330-153">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="9f330-153">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="9f330-154">No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="9f330-154">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="9f330-155">Criar um ambiente de serviço</span><span class="sxs-lookup"><span data-stu-id="9f330-155">Create a service environment</span></span>

1. <span data-ttu-id="9f330-156">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9f330-156">On the **Environment setups** page, on the action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="9f330-157">Selecione **Novo** para criar um novo ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="9f330-157">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="9f330-158">No campo **Nome**, insira o nome do ambiente de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9f330-158">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="9f330-159">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="9f330-159">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="9f330-160">No campo **Segredo de token SAS de armazenamento**, selecione o nome do certificado que deve ser usado para autenticar o acesso à conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9f330-160">In the **Storage SAS token secret** field, select the name of the certificate that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="9f330-161">Na seção **Usuários**, selecione **Adicionar** para adicionar um usuário que tem permissão para enviar faturas eletrônicas pelo ambiente e também para se conectar à conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9f330-161">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="9f330-162">No campo **ID do Usuário**, insira o alias do usuário.</span><span class="sxs-lookup"><span data-stu-id="9f330-162">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="9f330-163">No campo **Email**, insira o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="9f330-163">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="9f330-164">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9f330-164">Select **Save**.</span></span>
8. <span data-ttu-id="9f330-165">Se as faturas específicas de país/região exigirem uma cadeia de certificados para aplicar assinaturas digitais, no Painel de Ações, selecione **Parâmetros de Key Vault**, selecione **Cadeia de certificados** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9f330-165">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="9f330-166">Selecione **Novo** para criar uma cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="9f330-166">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="9f330-167">No campo **Nome**, insira o nome da cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="9f330-167">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="9f330-168">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="9f330-168">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="9f330-169">Na seção **Certificados**, selecione **Adicionar** para adicionar um certificado à cadeia.</span><span class="sxs-lookup"><span data-stu-id="9f330-169">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="9f330-170">Use o botão **Para cima** ou **Para baixo** para alterar a posição do certificado na cadeia.</span><span class="sxs-lookup"><span data-stu-id="9f330-170">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="9f330-171">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f330-171">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="9f330-172">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f330-172">Close the page.</span></span>
9. <span data-ttu-id="9f330-173">Na página **Ambiente de serviço**, no Painel de Ações, selecione **Publicar** para publicar o ambiente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="9f330-173">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="9f330-174">O valor do campo **Status** é alterado para **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="9f330-174">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="9f330-175">Crie um aplicativo conectado</span><span class="sxs-lookup"><span data-stu-id="9f330-175">Create a connected application</span></span>

1. <span data-ttu-id="9f330-176">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Aplicativos conectados**.</span><span class="sxs-lookup"><span data-stu-id="9f330-176">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="9f330-177">Selecione **Novo** para criar um aplicativo conectado.</span><span class="sxs-lookup"><span data-stu-id="9f330-177">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="9f330-178">No campo **Nome**, insira o nome do aplicativo a ser conectado.</span><span class="sxs-lookup"><span data-stu-id="9f330-178">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="9f330-179">No campo **Aplicativo**, insira a URL do ambiente Finance e Supply Chain Management para conexão.</span><span class="sxs-lookup"><span data-stu-id="9f330-179">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="9f330-180">No campo **Locatário**, insira o locatário do ambiente Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9f330-180">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="9f330-181">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9f330-181">Select **Save**.</span></span>
6. <span data-ttu-id="9f330-182">No Painel de Ações, selecione **Verificar conexão** para testar a conexão com o ambiente.</span><span class="sxs-lookup"><span data-stu-id="9f330-182">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="9f330-183">Depois feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f330-183">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="9f330-184">Vincular aplicativos conectados a ambientes</span><span class="sxs-lookup"><span data-stu-id="9f330-184">Link connected applications to environments</span></span>

1. <span data-ttu-id="9f330-185">Na página **Configurações de ambiente**, selecione **Novo** para atribuir um aplicativo conectado a um ambiente.</span><span class="sxs-lookup"><span data-stu-id="9f330-185">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="9f330-186">No campo **Aplicativo conectado**, selecione um aplicativo conectado.</span><span class="sxs-lookup"><span data-stu-id="9f330-186">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="9f330-187">No campo **Ambiente de serviço**, selecione um ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="9f330-187">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="9f330-188">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f330-188">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="9f330-189">Configurar a integração do Complemento de faturamento eletrônico no Finance e no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9f330-189">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="9f330-190">Ativar o recurso Integração do complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="9f330-190">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="9f330-191">Entre na instância do Finance ou do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9f330-191">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="9f330-192">No espaço de trabalho **Gerenciamento de recursos**, procure o recurso **Integração do complemento de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="9f330-192">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="9f330-193">Se esse recurso não aparecer na página, selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="9f330-193">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="9f330-194">Selecione o recurso e **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="9f330-194">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="9f330-195">Configurar a URL do ponto de extremidade de serviço</span><span class="sxs-lookup"><span data-stu-id="9f330-195">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="9f330-196">Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="9f330-196">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="9f330-197">Na guia **Serviço de envio**, no campo **URL de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado da geografia do Azure, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9f330-197">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="9f330-198">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="9f330-198">Datacenter Azure geography</span></span> | <span data-ttu-id="9f330-199">URL do ponto de extremidade do serviço</span><span class="sxs-lookup"><span data-stu-id="9f330-199">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="9f330-200">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="9f330-200">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9f330-201">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="9f330-201">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9f330-202">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="9f330-202">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="9f330-203">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="9f330-203">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="9f330-204">No campo **Ambiente**, insira o nome do ambiente de complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9f330-204">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="9f330-205">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f330-205">Select **Save**, and then close the page.</span></span>
