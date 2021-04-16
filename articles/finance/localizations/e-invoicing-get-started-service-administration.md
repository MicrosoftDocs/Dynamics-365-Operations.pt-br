---
title: Introdução à administração de serviço do Faturamento eletrônico
description: Este tópico explica como começar a usar o Faturamento eletrônico.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ec431cb4a3620459d905f64a80fd820a2113290f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840139"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a><span data-ttu-id="c3fa2-103">Introdução à administração de serviço do Faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="c3fa2-103">Get started with Electronic invoicing service administration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="c3fa2-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="c3fa2-104">Prerequisites</span></span>

<span data-ttu-id="c3fa2-105">Antes de concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:</span><span class="sxs-lookup"><span data-stu-id="c3fa2-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="c3fa2-106">Você deve ter acesso à conta do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c3fa2-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="c3fa2-107">Você deve ter um projeto LCS que inclua a versão 10.0.17 ou posterior do Microsoft Dynamics 365 Finance e o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c3fa2-108">Além disso, esses aplicativos devem ser implantados em uma das seguintes regiões geográficas do Azure:</span><span class="sxs-lookup"><span data-stu-id="c3fa2-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="c3fa2-109">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3fa2-109">East US</span></span>
    - <span data-ttu-id="c3fa2-110">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3fa2-110">West US</span></span>
    - <span data-ttu-id="c3fa2-111">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="c3fa2-111">North EU</span></span>
    - <span data-ttu-id="c3fa2-112">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="c3fa2-112">West EU</span></span>

- <span data-ttu-id="c3fa2-113">Você deve ter acesso à conta do Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="c3fa2-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="c3fa2-114">Você deve ativar o recurso Globalização para a conta RCS no Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="c3fa2-115">Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="c3fa2-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="c3fa2-116">Você deve criar um cofre de chaves e uma conta de armazenamento no Azure.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="c3fa2-117">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="c3fa2-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a><span data-ttu-id="c3fa2-118">Instalar o suplemento para microsserviços no Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="c3fa2-118">Install the add-in for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="c3fa2-119">Entre em sua conta do LCS.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="c3fa2-120">Selecione o bloco **Gerenciamento de versão prévia do recurso**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="c3fa2-121">Na seção **Recursos da versão preliminar pública**, selecione **Serviço de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="c3fa2-122">Verifique se a opção **Versão prévia do recurso habilitada** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="c3fa2-123">No painel LCS, selecione o projeto de implantação do LCS.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="c3fa2-124">O projeto LCS deve estar em execução.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="c3fa2-125">Na guia **Suplementos do ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="c3fa2-126">Selecione **Serviços de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-126">Select **e-invoicing Services**.</span></span>
9. <span data-ttu-id="c3fa2-127">No campo **ID do aplicativo do AAD**, insira **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-127">In the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="c3fa2-128">Esse é um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-128">This is a fixed value.</span></span>
10. <span data-ttu-id="c3fa2-129">No campo **ID de locatário AAD**, insira a ID do locatário da sua conta de assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-129">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="c3fa2-130">Analise os termos e condições e depois marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-130">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="c3fa2-131">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-131">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a><span data-ttu-id="c3fa2-132">Configure os parâmetros da integração do RCS com o Faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="c3fa2-132">Set up the parameters for RCS integration with Electronic invoicing</span></span>

1. <span data-ttu-id="c3fa2-133">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-133">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="c3fa2-134">No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-134">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="c3fa2-135">Na guia **Serviço de faturamento eletrônico**, no campo **URI de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado para sua geografia do Azure, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-135">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="c3fa2-136">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="c3fa2-136">Datacenter Azure geography</span></span> | <span data-ttu-id="c3fa2-137">URI do ponto de extremidade do serviço</span><span class="sxs-lookup"><span data-stu-id="c3fa2-137">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="c3fa2-138">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3fa2-138">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="c3fa2-139">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3fa2-139">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="c3fa2-140">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="c3fa2-140">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="c3fa2-141">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="c3fa2-141">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="c3fa2-142">Verifique se o campo **ID do Aplicativo** está definido como **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-142">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="c3fa2-143">Esse valor é um valor fixo.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-143">This value is a fixed value.</span></span>
5. <span data-ttu-id="c3fa2-144">No campo **ID de Ambiente do LCS**, insira a ID do ambiente do LCS.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-144">In the **LCS Environment Id** field, enter the ID of your LCS environment.</span></span>
6. <span data-ttu-id="c3fa2-145">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-145">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-references"></a><span data-ttu-id="c3fa2-146">Criar referências do Key Vault</span><span class="sxs-lookup"><span data-stu-id="c3fa2-146">Create Key Vault references</span></span>

1. <span data-ttu-id="c3fa2-147">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-147">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="c3fa2-148">No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-148">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="c3fa2-149">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** e **Parâmetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-149">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="c3fa2-150">Selecione **Novo** para criar uma referência de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-150">Select **New** to create a key vault reference.</span></span>
5. <span data-ttu-id="c3fa2-151">No campo **Nome**, insira o nome da referência de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-151">In the **Name** field, enter the name of the key vault reference.</span></span> <span data-ttu-id="c3fa2-152">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-152">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="c3fa2-153">No campo **URI do Key Vault**, cole o segredo de cofre de chaves do Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-153">In the **Key Vault URI** field, paste the key vault secret from Azure Key Vault.</span></span> <span data-ttu-id="c3fa2-154">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="c3fa2-154">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
7. <span data-ttu-id="c3fa2-155">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-155">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="c3fa2-156">Criar segredo da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="c3fa2-156">Create Storage account secret</span></span>

1. <span data-ttu-id="c3fa2-157">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** > **Parâmetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-157">On the **Environment setups** page, on the Action Pane, select **Service environment** > **Key Vault parameters**.</span></span>
2. <span data-ttu-id="c3fa2-158">Selecione uma **referência do Key Vault** e, na seção **Certificados**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-158">Select a **Key Vault reference** and in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="c3fa2-159">No campo **Nome**, insira o nome do segredo da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-159">In the **Name** field, enter the name of the storage account secret.</span></span> <span data-ttu-id="c3fa2-160">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="c3fa2-160">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="c3fa2-161">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-161">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="c3fa2-162">No campo **Tipo**, selecione **Segredo**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-162">In the **Type** field, select **Secret**.</span></span>
6. <span data-ttu-id="c3fa2-163">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-163">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="c3fa2-164">Criar um segredo de certificado digital</span><span class="sxs-lookup"><span data-stu-id="c3fa2-164">Create a digital certificate secret</span></span>

1. <span data-ttu-id="c3fa2-165">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** e **Parâmetros de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-165">On the **Environment setups** page, on the action Pane, select **Service environment** and then select **Key Vault parameters**.</span></span>
2. <span data-ttu-id="c3fa2-166">Selecione uma **referência do Key Vault** e, na seção **Certificados**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-166">Select a **Key Vault reference** and then in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="c3fa2-167">No campo **Nome**, insira o nome do segredo do certificado digital.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-167">In the **Name** field, enter the name of the digital certificate secret.</span></span> <span data-ttu-id="c3fa2-168">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="c3fa2-168">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="c3fa2-169">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-169">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="c3fa2-170">No campo **Tipo**, selecione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-170">In the **Type** field, select **Certificate**.</span></span>
6. <span data-ttu-id="c3fa2-171">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-171">Select **Save**, and then close the page.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="c3fa2-172">Criar um ambiente de serviço</span><span class="sxs-lookup"><span data-stu-id="c3fa2-172">Create a service environment</span></span>

1. <span data-ttu-id="c3fa2-173">Entre em sua conta do RCS.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-173">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="c3fa2-174">No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-174">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="c3fa2-175">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-175">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
4. <span data-ttu-id="c3fa2-176">Selecione **Novo** para criar um novo ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-176">Select **New** to create a new service environment.</span></span>
5. <span data-ttu-id="c3fa2-177">No campo **Nome**, insira o nome do ambiente de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-177">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="c3fa2-178">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-178">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="c3fa2-179">No campo **Segredo de token SAS de armazenamento**, selecione o nome do segredo da conta de armazenamento que deve ser usado para autenticar o acesso à conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-179">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
7. <span data-ttu-id="c3fa2-180">Na seção **Usuários**, selecione **Adicionar** para adicionar um usuário que tem permissão para enviar faturas eletrônicas pelo ambiente e também para se conectar à conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-180">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
8. <span data-ttu-id="c3fa2-181">No campo **ID do Usuário**, insira o alias do usuário.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-181">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="c3fa2-182">No campo **Email**, insira o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-182">In the **Email** field, enter the user's email address.</span></span>
9. <span data-ttu-id="c3fa2-183">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-183">Select **Save**.</span></span>
10. <span data-ttu-id="c3fa2-184">Se as faturas específicas de país/região exigirem uma cadeia de certificados para aplicar assinaturas digitais, no Painel de Ações, selecione **Parâmetros de Key Vault**, selecione **Cadeia de certificados** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c3fa2-184">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>
    1. <span data-ttu-id="c3fa2-185">Selecione **Novo** para criar uma cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-185">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="c3fa2-186">No campo **Nome**, insira o nome da cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-186">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="c3fa2-187">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-187">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="c3fa2-188">Na seção **Certificados**, selecione **Adicionar** para adicionar um certificado à cadeia.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-188">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="c3fa2-189">Use o botão **Para cima** ou **Para baixo** para alterar a posição do certificado na cadeia.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-189">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="c3fa2-190">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-190">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="c3fa2-191">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-191">Close the page.</span></span>
11. <span data-ttu-id="c3fa2-192">Na página **Ambiente de serviço**, no Painel de Ações, selecione **Publicar** para publicar o ambiente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-192">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="c3fa2-193">O valor do campo **Status** é alterado para **Publicado**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-193">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="c3fa2-194">Crie um aplicativo conectado</span><span class="sxs-lookup"><span data-stu-id="c3fa2-194">Create a connected application</span></span>

1. <span data-ttu-id="c3fa2-195">Na página **Configurações de ambiente**, no Painel de Ações, selecione **Aplicativos conectados**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-195">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="c3fa2-196">Selecione **Novo** para criar um aplicativo conectado.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-196">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="c3fa2-197">No campo **Nome**, insira o nome do aplicativo a ser conectado.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-197">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="c3fa2-198">No campo **Aplicativo**, insira a URL do ambiente Finance e Supply Chain Management para conexão.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-198">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="c3fa2-199">No campo **Locatário**, insira o locatário do ambiente Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-199">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="c3fa2-200">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-200">Select **Save**.</span></span>
6. <span data-ttu-id="c3fa2-201">No Painel de Ações, selecione **Verificar conexão** para testar a conexão com o ambiente.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-201">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="c3fa2-202">Depois feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-202">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="c3fa2-203">Vincular aplicativos conectados a ambientes</span><span class="sxs-lookup"><span data-stu-id="c3fa2-203">Link connected applications to environments</span></span>

1. <span data-ttu-id="c3fa2-204">Na página **Configurações de ambiente**, selecione **Novo** para atribuir um aplicativo conectado a um ambiente.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-204">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="c3fa2-205">No campo **Aplicativo conectado**, selecione um aplicativo conectado.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-205">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="c3fa2-206">No campo **Ambiente de serviço**, selecione um ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-206">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="c3fa2-207">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-207">Select **Save**, and then close the page.</span></span>

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="c3fa2-208">Configurar a integração do Faturamento eletrônico no Finance e no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c3fa2-208">Set up Electronic invoicing integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a><span data-ttu-id="c3fa2-209">Ativar o recurso Integração do Faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="c3fa2-209">Turn on the Electronic invoicing integration feature</span></span>

1. <span data-ttu-id="c3fa2-210">Entre na instância do Finance ou do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-210">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="c3fa2-211">No espaço de trabalho **Gerenciamento de recursos**, procure o recurso **Integração do Faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-211">In the **Feature management** workspace, search for the **Electronic invoicing integration** feature.</span></span> <span data-ttu-id="c3fa2-212">Se esse recurso não aparecer na página, selecione **Verificar se há atualizações**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-212">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="c3fa2-213">Selecione o recurso e **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-213">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="c3fa2-214">Configurar a URL do ponto de extremidade de serviço</span><span class="sxs-lookup"><span data-stu-id="c3fa2-214">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="c3fa2-215">Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-215">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="c3fa2-216">Na guia **Serviço de envio**, no campo **URL de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado da geografia do Azure, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-216">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="c3fa2-217">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="c3fa2-217">Datacenter Azure geography</span></span> | <span data-ttu-id="c3fa2-218">URL do ponto de extremidade do serviço</span><span class="sxs-lookup"><span data-stu-id="c3fa2-218">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="c3fa2-219">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3fa2-219">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="c3fa2-220">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="c3fa2-220">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="c3fa2-221">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="c3fa2-221">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="c3fa2-222">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="c3fa2-222">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="c3fa2-223">No campo **Ambiente**, insira o nome do ambiente de serviço publicado no Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-223">In the **Environment** field, enter the name of the service environment published in Electronic invoicing.</span></span>
4. <span data-ttu-id="c3fa2-224">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-224">Select **Save**, and then close the page.</span></span>

### <a name="enable-flighting-keys"></a><span data-ttu-id="c3fa2-225">Habilitar chaves da liberação de versões de pré-lançamento</span><span class="sxs-lookup"><span data-stu-id="c3fa2-225">Enable Flighting keys</span></span>

<span data-ttu-id="c3fa2-226">Habilite as chaves da Versão de pré-lançamento do Microsoft Dynamics 365 Finance ou Microsoft Dynamics 365 Supply Chain Management 10.0.17 ou anteriores.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-226">Enable Flight keys for  Microsoft Dynamics 365 Finance or  Microsoft Dynamics 365 Supply Chain Management versions 10.0.17 or earlier.</span></span> 
1. <span data-ttu-id="c3fa2-227">Execute o seguinte comando SQL:</span><span class="sxs-lookup"><span data-stu-id="c3fa2-227">Execute the following SQL command:</span></span>

    <span data-ttu-id="c3fa2-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span><span class="sxs-lookup"><span data-stu-id="c3fa2-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span></span>
    
    <span data-ttu-id="c3fa2-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span><span class="sxs-lookup"><span data-stu-id="c3fa2-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span></span>

2. <span data-ttu-id="c3fa2-230">Executa um comando IISreset para todos os AOS.</span><span class="sxs-lookup"><span data-stu-id="c3fa2-230">Perform an IISreset command for all AOS's.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
