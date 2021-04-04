---
title: Introdução à administração de serviço do complemento do faturamento eletrônico
description: Este tópico explica como começar a usar o complemento de faturamento eletrônico.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592517"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="b670d-103">Introdução à administração de serviço do complemento do faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="b670d-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="b670d-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b670d-104">Prerequisites</span></span>

<span data-ttu-id="b670d-105">Antes de concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:</span><span class="sxs-lookup"><span data-stu-id="b670d-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="b670d-106">Você deve ter acesso à conta do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b670d-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="b670d-107">Você deve ter um projeto LCS que inclua a versão 10.0.17 ou posterior do Microsoft Dynamics 365 Finance e o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b670d-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b670d-108">Além disso, esses aplicativos devem ser implantados em uma das seguintes regiões geográficas do Azure:</span><span class="sxs-lookup"><span data-stu-id="b670d-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="b670d-109">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="b670d-109">East US</span></span>
    - <span data-ttu-id="b670d-110">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="b670d-110">West US</span></span>
    - <span data-ttu-id="b670d-111">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="b670d-111">North EU</span></span>
    - <span data-ttu-id="b670d-112">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="b670d-112">West EU</span></span>

- <span data-ttu-id="b670d-113">Você deve ter acesso à conta do Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="b670d-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="b670d-114">Você deve ativar o recurso Globalização para a conta RCS no Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="b670d-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="b670d-115">Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="b670d-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="b670d-116">Você deve criar um cofre de chaves e uma conta de armazenamento no Azure.</span><span class="sxs-lookup"><span data-stu-id="b670d-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="b670d-117">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="b670d-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="b670d-118">Instalar o complemento para microsserviços no Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="b670d-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="b670d-119">Entre em sua conta do LCS.</span><span class="sxs-lookup"><span data-stu-id="b670d-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="b670d-120">Selecione o bloco **Gerenciamento de versão prévia do recurso**.</span><span class="sxs-lookup"><span data-stu-id="b670d-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="b670d-121">Na seção **Recursos da versão preliminar pública**, selecione **Serviço de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b670d-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="b670d-122">Verifique se a opção **Versão prévia do recurso habilitada** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b670d-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="b670d-123">No painel LCS, selecione o projeto de implantação do LCS.</span><span class="sxs-lookup"><span data-stu-id="b670d-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="b670d-124">O projeto LCS deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="b670d-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="b670d-125">Na guia **Suplementos do ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="b670d-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="b670d-126">Selecione **Serviços de faturamento eletrônico** e, no campo **ID do aplicativo AAD**, insira **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="b670d-126">Select **e-invoicing Services** and in the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="b670d-127">Esse é um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="b670d-127">This is a fixed value.</span></span>
10. <span data-ttu-id="b670d-128">No campo **ID de locatário AAD**, insira a ID do locatário da sua conta de assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="b670d-128">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="b670d-129">Analise os termos e condições e depois marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="b670d-129">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="b670d-130">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b670d-130">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="b670d-131">Configure os parâmetros da integração do RCS com o complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="b670d-131">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="b670d-132">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="b670d-132">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="b670d-133">No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b670d-133">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="b670d-134">Na guia **Serviço de faturamento eletrônico**, no campo **URI de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado para sua geografia do Azure, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b670d-134">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="b670d-135">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="b670d-135">Datacenter Azure geography</span></span> | <span data-ttu-id="b670d-136">URI do ponto de extremidade do serviço</span><span class="sxs-lookup"><span data-stu-id="b670d-136">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="b670d-137">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="b670d-137">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="b670d-138">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="b670d-138">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="b670d-139">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="b670d-139">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="b670d-140">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="b670d-140">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="b670d-141">Verifique se o campo **ID do Aplicativo** está definido como **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="b670d-141">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="b670d-142">Esse valor é um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="b670d-142">This value is a fixed value.</span></span>
5. <span data-ttu-id="b670d-143">No campo **ID de Ambiente do LCS**, insira a ID da conta de assinatura do LCS.</span><span class="sxs-lookup"><span data-stu-id="b670d-143">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="b670d-144">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-144">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="b670d-145">Criar segredo do Key Vault</span><span class="sxs-lookup"><span data-stu-id="b670d-145">Create Key Vault secret</span></span>

1. <span data-ttu-id="b670d-146">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="b670d-146">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="b670d-147">No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Complemento de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b670d-147">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>
3. <span data-ttu-id="b670d-148">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** e **Parâmetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="b670d-148">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="b670d-149">Selecione **Novo** para criar um segredo de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="b670d-149">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="b670d-150">No campo **Nome**, insira o nome do segredo de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="b670d-150">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="b670d-151">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b670d-151">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="b670d-152">No campo **URI do Key Vault**, cole o segredo do Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b670d-152">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="b670d-153">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b670d-153">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="b670d-154">Criar segredo da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="b670d-154">Create Storage account secret</span></span>

1. <span data-ttu-id="b670d-155">Acesse **Administração do sistema** > **Configuração** > **Parâmetros do Key Vault** e selecione um Segredo do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="b670d-155">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="b670d-156">Na seção **Certificados**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b670d-156">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="b670d-157">No campo **Nome**, insira o nome do segredo da conta de armazenamento e, no campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b670d-157">In the **Name** field, enter the name of the storage account secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="b670d-158">No campo **Tipo**, selecione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="b670d-158">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="b670d-159">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-159">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="b670d-160">Criar um segredo de certificado digital</span><span class="sxs-lookup"><span data-stu-id="b670d-160">Create a digital certificate secret</span></span>

1. <span data-ttu-id="b670d-161">Acesse **Administração do sistema** > **Configuração** > **Parâmetros do Key Vault** e selecione um Segredo do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="b670d-161">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="b670d-162">Na seção **Certificados**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b670d-162">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="b670d-163">No campo **Nome**, insira o nome do segredo do certificado digital e, no campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b670d-163">In the **Name** field, enter the name of the digital certificate secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="b670d-164">No campo **Tipo**, selecione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="b670d-164">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="b670d-165">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-165">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="b670d-166">Criar um ambiente de Complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="b670d-166">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="b670d-167">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="b670d-167">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="b670d-168">No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Complemento de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b670d-168">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="b670d-169">Criar um ambiente de serviço</span><span class="sxs-lookup"><span data-stu-id="b670d-169">Create a service environment</span></span>

1. <span data-ttu-id="b670d-170">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b670d-170">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="b670d-171">Selecione **Novo** para criar um novo ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="b670d-171">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="b670d-172">No campo **Nome**, insira o nome do ambiente de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b670d-172">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="b670d-173">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b670d-173">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="b670d-174">No campo **Segredo de token SAS de armazenamento**, selecione o nome do segredo da conta de armazenamento que deve ser usado para autenticar o acesso à conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b670d-174">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="b670d-175">Na seção **Usuários**, selecione **Adicionar** para adicionar um usuário que tem permissão para enviar faturas eletrônicas pelo ambiente e também para se conectar à conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b670d-175">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="b670d-176">No campo **ID do Usuário**, insira o alias do usuário.</span><span class="sxs-lookup"><span data-stu-id="b670d-176">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="b670d-177">No campo **Email**, insira o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="b670d-177">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="b670d-178">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b670d-178">Select **Save**.</span></span>
8. <span data-ttu-id="b670d-179">Se as faturas específicas de país/região exigirem uma cadeia de certificados para aplicar assinaturas digitais, no Painel de Ações, selecione **Parâmetros de Key Vault**, selecione **Cadeia de certificados** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b670d-179">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="b670d-180">Selecione **Novo** para criar uma cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="b670d-180">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="b670d-181">No campo **Nome**, insira o nome da cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="b670d-181">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="b670d-182">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b670d-182">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="b670d-183">Na seção **Certificados**, selecione **Adicionar** para adicionar um certificado à cadeia.</span><span class="sxs-lookup"><span data-stu-id="b670d-183">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="b670d-184">Use o botão **Para cima** ou **Para baixo** para alterar a posição do certificado na cadeia.</span><span class="sxs-lookup"><span data-stu-id="b670d-184">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="b670d-185">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-185">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="b670d-186">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-186">Close the page.</span></span>
9. <span data-ttu-id="b670d-187">Na página **Ambiente de serviço**, no Painel de Ações, selecione **Publicar** para publicar o ambiente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b670d-187">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="b670d-188">O valor do campo **Status** é alterado para **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="b670d-188">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="b670d-189">Crie um aplicativo conectado</span><span class="sxs-lookup"><span data-stu-id="b670d-189">Create a connected application</span></span>

1. <span data-ttu-id="b670d-190">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Aplicativos conectados**.</span><span class="sxs-lookup"><span data-stu-id="b670d-190">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="b670d-191">Selecione **Novo** para criar um aplicativo conectado.</span><span class="sxs-lookup"><span data-stu-id="b670d-191">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="b670d-192">No campo **Nome**, insira o nome do aplicativo a ser conectado.</span><span class="sxs-lookup"><span data-stu-id="b670d-192">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="b670d-193">No campo **Aplicativo**, insira a URL do ambiente Finance e Supply Chain Management para conexão.</span><span class="sxs-lookup"><span data-stu-id="b670d-193">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="b670d-194">No campo **Locatário**, insira o locatário do ambiente Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b670d-194">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="b670d-195">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b670d-195">Select **Save**.</span></span>
6. <span data-ttu-id="b670d-196">No Painel de Ações, selecione **Verificar conexão** para testar a conexão com o ambiente.</span><span class="sxs-lookup"><span data-stu-id="b670d-196">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="b670d-197">Depois feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-197">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="b670d-198">Vincular aplicativos conectados a ambientes</span><span class="sxs-lookup"><span data-stu-id="b670d-198">Link connected applications to environments</span></span>

1. <span data-ttu-id="b670d-199">Na página **Configurações de ambiente**, selecione **Novo** para atribuir um aplicativo conectado a um ambiente.</span><span class="sxs-lookup"><span data-stu-id="b670d-199">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="b670d-200">No campo **Aplicativo conectado**, selecione um aplicativo conectado.</span><span class="sxs-lookup"><span data-stu-id="b670d-200">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="b670d-201">No campo **Ambiente de serviço**, selecione um ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="b670d-201">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="b670d-202">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-202">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="b670d-203">Configurar a integração do Complemento de faturamento eletrônico no Finance e no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b670d-203">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="b670d-204">Ativar o recurso Integração do complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="b670d-204">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="b670d-205">Entre na instância do Finance ou do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b670d-205">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="b670d-206">No espaço de trabalho **Gerenciamento de recursos**, procure o recurso **Integração do complemento de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b670d-206">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="b670d-207">Se esse recurso não aparecer na página, selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="b670d-207">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="b670d-208">Selecione o recurso e **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="b670d-208">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="b670d-209">Configurar a URL do ponto de extremidade de serviço</span><span class="sxs-lookup"><span data-stu-id="b670d-209">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="b670d-210">Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="b670d-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="b670d-211">Na guia **Serviço de envio**, no campo **URL de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado da geografia do Azure, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b670d-211">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="b670d-212">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="b670d-212">Datacenter Azure geography</span></span> | <span data-ttu-id="b670d-213">URL do ponto de extremidade do serviço</span><span class="sxs-lookup"><span data-stu-id="b670d-213">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="b670d-214">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="b670d-214">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="b670d-215">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="b670d-215">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="b670d-216">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="b670d-216">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="b670d-217">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="b670d-217">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="b670d-218">No campo **Ambiente**, insira o nome do ambiente de complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b670d-218">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="b670d-219">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="b670d-219">Select **Save**, and then close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
