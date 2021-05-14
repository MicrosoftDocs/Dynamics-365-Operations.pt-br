---
title: Criar uma conta de armazenamento do Azure e um cofre de chaves
description: Este tópico explica como criar uma conta de armazenamento do Azure e um cofre de chaves.
author: gionoder
ms.date: 04/29/2021
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
ms.openlocfilehash: 5c2ddad10f9cbedd77a04fe0f42bdc217fd43344
ms.sourcegitcommit: 54d3ec0c006bfa9d2b849590205be08551c4e0f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "5963230"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="433a4-103">Criar uma conta de armazenamento do Azure e um cofre de chaves</span><span class="sxs-lookup"><span data-stu-id="433a4-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="433a4-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="433a4-104">Prerequisites</span></span>

<span data-ttu-id="433a4-105">Antes de concluir as etapas neste tópico, verifique se as seguintes tarefas foram concluídas:</span><span class="sxs-lookup"><span data-stu-id="433a4-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="433a4-106">Criar um recurso de cofre de chaves no Azure.</span><span class="sxs-lookup"><span data-stu-id="433a4-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="433a4-107">Para obter mais informações, consulte [Sobre o Azure Key Vault](/azure/key-vault/general/overview).</span><span class="sxs-lookup"><span data-stu-id="433a4-107">For more information, see [About Azure Key Vault](/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="433a4-108">Crie uma conta de armazenamento do Azure (armazenamento de Blob).</span><span class="sxs-lookup"><span data-stu-id="433a4-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="433a4-109">Para obter mais informações, consulte [Manter a conta de armazenamento do Azure](/azure/storage/blobs/).</span><span class="sxs-lookup"><span data-stu-id="433a4-109">For more information, see [Maintaining Azure Storage Account](/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="433a4-110">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="433a4-110">Overview</span></span>

<span data-ttu-id="433a4-111">Neste tópico, você executará duas etapas principais:</span><span class="sxs-lookup"><span data-stu-id="433a4-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="433a4-112">Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="433a4-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="433a4-113">Configure o cofre de chaves para armazenar o URI da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="433a4-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="433a4-114">Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="433a4-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="433a4-115">Abra a conta de armazenamento que você planeja usar com o Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="433a4-115">Open the storage account that you plan to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="433a4-116">Vá para **Serviço Blob** \> **Contêineres** e crie um novo contêiner.</span><span class="sxs-lookup"><span data-stu-id="433a4-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="433a4-117">Digite um nome para o contêiner e defina o campo **Nível de acesso público** como **Privado (sem acesso anônimo)**.</span><span class="sxs-lookup"><span data-stu-id="433a4-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="433a4-118">Abra o contêiner e vá para **Configurações \> Política de acesso**.</span><span class="sxs-lookup"><span data-stu-id="433a4-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="433a4-119">Selecione **Adicionar política** para adicionar uma política de acesso armazenada.</span><span class="sxs-lookup"><span data-stu-id="433a4-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="433a4-120">Defina os campos **Identificador** e **Permissões**, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="433a4-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="433a4-121">No campo **Permissões**, você deve selecionar todas as permissões.</span><span class="sxs-lookup"><span data-stu-id="433a4-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Conceder permissão de armazenamento de Blobs](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="433a4-123">Insira as datas de início e de vencimento.</span><span class="sxs-lookup"><span data-stu-id="433a4-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="433a4-124">A data de vencimento deve estar no futuro.</span><span class="sxs-lookup"><span data-stu-id="433a4-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="433a4-125">Selecione **OK** para salvar a política e salve as alterações no contêiner.</span><span class="sxs-lookup"><span data-stu-id="433a4-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="433a4-126">Retorne à conta de armazenamento e abra o **Gerenciador de Armazenamento (versão prévia)**.</span><span class="sxs-lookup"><span data-stu-id="433a4-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="433a4-127">Clique com o botão direito do mouse no contêiner e selecione **Obter assinatura de acesso compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="433a4-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="433a4-128">Na caixa de diálogo **Assinatura de acesso compartilhado**, copie e armazene o valor no campo **URI**.</span><span class="sxs-lookup"><span data-stu-id="433a4-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="433a4-129">Esse valor será usado no procedimento seguinte e será referenciado como *URI de assinatura de acesso compartilhado*.</span><span class="sxs-lookup"><span data-stu-id="433a4-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Selecionar e copiar o valor do URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="433a4-131">Configure o cofre de chaves para armazenar o URI da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="433a4-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="433a4-132">Abra o cofre de chaves que você pretende usar com o Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="433a4-132">Open the key vault that you intend to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="433a4-133">Vá para **Configurações** \> **Segredos** e selecione **Gerar/Importar** para criar um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="433a4-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="433a4-134">Na página **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="433a4-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="433a4-135">Insira o nome do segredo.</span><span class="sxs-lookup"><span data-stu-id="433a4-135">Enter the name of the secret.</span></span> <span data-ttu-id="433a4-136">Esse nome será usado durante a configuração do serviço no RCS (Regulatory Configuration Service) e será referenciado como *Nome secreto do cofre de chaves*.</span><span class="sxs-lookup"><span data-stu-id="433a4-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="433a4-137">No campo **Valor**, selecione **URI de Assinatura de Acesso Compartilhado** e, em seguida, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="433a4-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="433a4-138">Configure a política de acesso para conceder ao Faturamento eletrônico o nível correto de acesso seguro ao segredo criado.</span><span class="sxs-lookup"><span data-stu-id="433a4-138">Set up the access policy to grant Electronic invoicing the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="433a4-139">Vá para **Configurações \> Política de acesso** e selecione **Adicionar Política de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="433a4-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="433a4-140">Defina as permissões secretas para as operações **Obter** e **Lista**.</span><span class="sxs-lookup"><span data-stu-id="433a4-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Conceder acesso ao serviço](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="433a4-142">Defina as permissões de certificado para operações **Obter** e **Lista**.</span><span class="sxs-lookup"><span data-stu-id="433a4-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Conceder permissão de certificado](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="433a4-144">No campo **Selecionar principal**, selecione **Nenhum selecionado**.</span><span class="sxs-lookup"><span data-stu-id="433a4-144">In the **Select principal** field, select **None selected**.</span></span>
10. <span data-ttu-id="433a4-145">Na caixa de diálogo **Entidade de segurança**, selecione a entidade de segurança, adicionando o **Serviço de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="433a4-145">In the **Principal** dialog box, select the principal by adding **e-Invoicing Service**.</span></span>
11. <span data-ttu-id="433a4-146">Selecione **Adicionar** e, em seguida, **Salvar alterações do Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="433a4-146">Select **Add**, and then select **Save Key Vault changes**.</span></span>
12. <span data-ttu-id="433a4-147">Na página **Visão geral**, copie o valor **Nome do DNS** para o cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="433a4-147">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="433a4-148">Esse valor será usado durante a configuração do serviço no RCS e será referenciado como o *URI do cofre de chaves*.</span><span class="sxs-lookup"><span data-stu-id="433a4-148">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>

> [!NOTE]
> <span data-ttu-id="433a4-149">Para obter segurança adicional na conta de armazenamento, configure o Azure Defender para armazenamento.</span><span class="sxs-lookup"><span data-stu-id="433a4-149">For additional security on the storage account, configure the Azure Defender for Storage.</span></span>
> 
> <span data-ttu-id="433a4-150">Para obter mais informações, consulte [Introdução ao Azure Defender para armazenamento](/azure/security-center/defender-for-storage-introduction).</span><span class="sxs-lookup"><span data-stu-id="433a4-150">For more information, see [Introduction to Azure Defender for Storage](/azure/security-center/defender-for-storage-introduction).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
