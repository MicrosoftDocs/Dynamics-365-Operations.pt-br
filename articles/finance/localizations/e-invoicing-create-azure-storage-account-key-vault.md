---
title: Criar uma conta de armazenamento do Azure e um cofre de chaves
description: Este tópico explica como criar uma conta de armazenamento do Azure e um cofre de chaves.
author: gionoder
ms.date: 02/12/2021
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
ms.openlocfilehash: 2786d350fde2399aadb35dc653bc15123e0e6d91
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893793"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="6c541-103">Criar uma conta de armazenamento do Azure e um cofre de chaves</span><span class="sxs-lookup"><span data-stu-id="6c541-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="6c541-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6c541-104">Prerequisites</span></span>

<span data-ttu-id="6c541-105">Antes de concluir as etapas neste tópico, verifique se as seguintes tarefas foram concluídas:</span><span class="sxs-lookup"><span data-stu-id="6c541-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="6c541-106">Criar um recurso de cofre de chaves no Azure.</span><span class="sxs-lookup"><span data-stu-id="6c541-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="6c541-107">Para obter mais informações, consulte [Sobre o Azure Key Vault](/azure/key-vault/general/overview).</span><span class="sxs-lookup"><span data-stu-id="6c541-107">For more information, see [About Azure Key Vault](/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="6c541-108">Crie uma conta de armazenamento do Azure (armazenamento de Blob).</span><span class="sxs-lookup"><span data-stu-id="6c541-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="6c541-109">Para obter mais informações, consulte [Manter a conta de armazenamento do Azure](/azure/storage/blobs/).</span><span class="sxs-lookup"><span data-stu-id="6c541-109">For more information, see [Maintaining Azure Storage Account](/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="6c541-110">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="6c541-110">Overview</span></span>

<span data-ttu-id="6c541-111">Neste tópico, você executará duas etapas principais:</span><span class="sxs-lookup"><span data-stu-id="6c541-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="6c541-112">Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="6c541-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="6c541-113">Configure o cofre de chaves para armazenar o URI da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="6c541-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="6c541-114">Configure a conta de armazenamento do Azure para obter o URI da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="6c541-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="6c541-115">Abra a conta de armazenamento que você planeja usar com o Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6c541-115">Open the storage account that you plan to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="6c541-116">Vá para **Serviço Blob** \> **Contêineres** e crie um novo contêiner.</span><span class="sxs-lookup"><span data-stu-id="6c541-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="6c541-117">Digite um nome para o contêiner e defina o campo **Nível de acesso público** como **Privado (sem acesso anônimo)**.</span><span class="sxs-lookup"><span data-stu-id="6c541-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="6c541-118">Abra o contêiner e vá para **Configurações \> Política de acesso**.</span><span class="sxs-lookup"><span data-stu-id="6c541-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="6c541-119">Selecione **Adicionar política** para adicionar uma política de acesso armazenada.</span><span class="sxs-lookup"><span data-stu-id="6c541-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="6c541-120">Defina os campos **Identificador** e **Permissões**, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="6c541-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="6c541-121">No campo **Permissões**, você deve selecionar todas as permissões.</span><span class="sxs-lookup"><span data-stu-id="6c541-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Conceder permissão de armazenamento de Blobs](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="6c541-123">Insira as datas de início e de vencimento.</span><span class="sxs-lookup"><span data-stu-id="6c541-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="6c541-124">A data de vencimento deve estar no futuro.</span><span class="sxs-lookup"><span data-stu-id="6c541-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="6c541-125">Selecione **OK** para salvar a política e salve as alterações no contêiner.</span><span class="sxs-lookup"><span data-stu-id="6c541-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="6c541-126">Retorne à conta de armazenamento e abra o **Gerenciador de Armazenamento (versão prévia)**.</span><span class="sxs-lookup"><span data-stu-id="6c541-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="6c541-127">Clique com o botão direito do mouse no contêiner e selecione **Obter assinatura de acesso compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="6c541-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="6c541-128">Na caixa de diálogo **Assinatura de acesso compartilhado**, copie e armazene o valor no campo **URI**.</span><span class="sxs-lookup"><span data-stu-id="6c541-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="6c541-129">Esse valor será usado no procedimento seguinte e será referenciado como *URI de assinatura de acesso compartilhado*.</span><span class="sxs-lookup"><span data-stu-id="6c541-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Selecionar e copiar o valor do URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="6c541-131">Configure o cofre de chaves para armazenar o URI da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="6c541-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="6c541-132">Abra o cofre de chaves que você pretende usar com o Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6c541-132">Open the key vault that you intend to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="6c541-133">Vá para **Configurações** \> **Segredos** e selecione **Gerar/Importar** para criar um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="6c541-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="6c541-134">Na página **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="6c541-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="6c541-135">Insira o nome do segredo.</span><span class="sxs-lookup"><span data-stu-id="6c541-135">Enter the name of the secret.</span></span> <span data-ttu-id="6c541-136">Esse nome será usado durante a configuração do serviço no RCS (Regulatory Configuration Service) e será referenciado como *Nome secreto do cofre de chaves*.</span><span class="sxs-lookup"><span data-stu-id="6c541-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="6c541-137">No campo **Valor**, selecione **URI de Assinatura de Acesso Compartilhado** e, em seguida, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="6c541-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="6c541-138">Configure a política de acesso para conceder ao Faturamento eletrônico o nível correto de acesso seguro ao segredo criado.</span><span class="sxs-lookup"><span data-stu-id="6c541-138">Set up the access policy to grant Electronic invoicing the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="6c541-139">Vá para **Configurações \> Política de acesso** e selecione **Adicionar Política de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="6c541-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="6c541-140">Defina as permissões secretas para as operações **Obter** e **Lista**.</span><span class="sxs-lookup"><span data-stu-id="6c541-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Conceder acesso ao serviço](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="6c541-142">Defina as permissões de certificado para operações **Obter** e **Lista**.</span><span class="sxs-lookup"><span data-stu-id="6c541-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Conceder permissão de certificado](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="6c541-144">No campo **Selecionar principal**, selecione **Nenhum selecionado**.</span><span class="sxs-lookup"><span data-stu-id="6c541-144">In the **Select principal** field, select **None selected**.</span></span>
10. <span data-ttu-id="6c541-145">Na caixa de diálogo **Entidade de segurança**, selecione a entidade de segurança, adicionando o **Serviço de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="6c541-145">In the **Principal** dialog box, select the principal by adding **e-Invoicing Service**.</span></span>
11. <span data-ttu-id="6c541-146">Selecione **Adicionar** e, em seguida, **Salvar alterações do Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="6c541-146">Select **Add**, and then select **Save Key Vault changes**.</span></span>
12. <span data-ttu-id="6c541-147">Na página **Visão geral**, copie o valor **Nome do DNS** para o cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="6c541-147">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="6c541-148">Esse valor será usado durante a configuração do serviço no RCS e será referenciado como o *URI do cofre de chaves*.</span><span class="sxs-lookup"><span data-stu-id="6c541-148">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]