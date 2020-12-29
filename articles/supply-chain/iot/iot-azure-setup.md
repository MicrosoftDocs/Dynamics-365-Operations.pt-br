---
title: Configurar recursos do Azure para Inteligência de IoT
description: Este tópico explica como criar e configurar os recursos do Microsoft Azure necessários para a Inteligência de IOT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1277d2ab8bb1f2925874f7469250e164f6bde62d
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422497"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="4fabe-103">Configurar recursos do Azure para Inteligência de IoT</span><span class="sxs-lookup"><span data-stu-id="4fabe-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4fabe-104">Este tópico explica como criar e configurar os recursos do Microsoft Azure necessários para a Inteligência de IOT.</span><span class="sxs-lookup"><span data-stu-id="4fabe-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="4fabe-105">Criar recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="4fabe-105">Create Azure resources</span></span>

<span data-ttu-id="4fabe-106">Siga estas etapas para criar um Hub IoT, um cache de Redis e um cofre de chaves que podem ser acessados pelo Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4fabe-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="4fabe-107">Verifique se a ID do aplicativo interno de microsserviços do Microsoft Dynamics ERP está em seu locatário</span><span class="sxs-lookup"><span data-stu-id="4fabe-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="4fabe-108">Para verificar se a ID do aplicativo para o aplicativo interno de microsserviços do Microsoft Dynamics ERP está em seu locatário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-109">Entre no portal do Azure em <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="4fabe-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="4fabe-110">Acesse **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="4fabe-111">Vá para **Aplicativos corporativos**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="4fabe-112">No campo **Tipo de aplicativo**, selecione **Aplicativos da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="4fabe-113">No campo de pesquisa, insira os **microsserviços do Microsoft Dynamics ERP**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="4fabe-114">Verifique se **microsserviços do Microsoft Dynamics ERP** estão na lista.</span><span class="sxs-lookup"><span data-stu-id="4fabe-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="4fabe-115">Outros aplicativos têm nomes semelhantes.</span><span class="sxs-lookup"><span data-stu-id="4fabe-115">Other applications have similar names.</span></span> <span data-ttu-id="4fabe-116">Portanto, certifique se você encontrou a aplicação correta.</span><span class="sxs-lookup"><span data-stu-id="4fabe-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="4fabe-117">A ID do aplicativo é **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="4fabe-118">Se o aplicativo não estiver na lista, você deve adicioná-lo ao seu locatário:</span><span class="sxs-lookup"><span data-stu-id="4fabe-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="4fabe-119">No portal do Azure, na barra de ferramentas, selecione o botão para abrir o Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="4fabe-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="4fabe-120">Execute o comando **Install-Module AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="4fabe-121">Insira **S** para instalar o módulo.</span><span class="sxs-lookup"><span data-stu-id="4fabe-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="4fabe-122">Execute o comando **Get-InstalledModule -Name "AzureAD"** para verificar se o módulo está instalado.</span><span class="sxs-lookup"><span data-stu-id="4fabe-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="4fabe-123">Execute o comando **Connect-AzureAD -Confirm** para executar a autenticação.</span><span class="sxs-lookup"><span data-stu-id="4fabe-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="4fabe-124">Execute o comando **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="4fabe-125">Agora você pode repetir as etapas 1 a 6 para verificar se a ID do aplicativo está no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="4fabe-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="4fabe-126">Criar um recurso de cofre de chaves</span><span class="sxs-lookup"><span data-stu-id="4fabe-126">Create a key vault resource</span></span>

<span data-ttu-id="4fabe-127">Para criar um recurso de cofre de chaves, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-128">No portal do Azure, crie ou acesse um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4fabe-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="4fabe-129">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-129">Select **Add**.</span></span>
3. <span data-ttu-id="4fabe-130">Na página **Novo**, no campo de pesquisa, insira o **Cofre de chaves**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="4fabe-131">Depois, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-131">Then select **Create**.</span></span>
4. <span data-ttu-id="4fabe-132">Na página **Criar cofre de chaves**, no campo **Nome do cofre de chaves**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="4fabe-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="4fabe-133">Revise os valores padrão e selecione **Revisar + Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="4fabe-134">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-134">Select **Create**.</span></span>

<span data-ttu-id="4fabe-135">O cofre de chaves é criado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4fabe-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="4fabe-136">Criar um recurso de Hub IoT</span><span class="sxs-lookup"><span data-stu-id="4fabe-136">Create an IoT hub resource</span></span>

<span data-ttu-id="4fabe-137">Para criar um recurso de Hub IoT, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-138">Crie ou vá para um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4fabe-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="4fabe-139">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-139">Select **Add**.</span></span>
3. <span data-ttu-id="4fabe-140">Na página **Novo**, no campo de pesquisa, insira o **Hub Iot**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="4fabe-141">Depois, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-141">Then select **Create**.</span></span>
4. <span data-ttu-id="4fabe-142">No campo **Nome de Hub IoT**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="4fabe-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="4fabe-143">Revise os valores padrão e selecione **Revisar + Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="4fabe-144">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-144">Select **Create**.</span></span>

<span data-ttu-id="4fabe-145">O Hub IoT é criado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4fabe-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="4fabe-146">Recomendamos que você crie apenas um recurso de Hub IoT por ambiente.</span><span class="sxs-lookup"><span data-stu-id="4fabe-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="4fabe-147">Criar um recurso de cache Redis</span><span class="sxs-lookup"><span data-stu-id="4fabe-147">Create a Redis cache resource</span></span>

<span data-ttu-id="4fabe-148">Para criar um recurso de cache Redis, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-149">Crie ou vá para um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4fabe-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="4fabe-150">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-150">Select **Add**.</span></span>
3. <span data-ttu-id="4fabe-151">Na página **Novo**, no campo de pesquisa, insira **Cache do Azure para Redis**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="4fabe-152">Depois, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-152">Then select **Create**.</span></span>
4. <span data-ttu-id="4fabe-153">No campo **Nome do DNS**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="4fabe-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="4fabe-154">Revise os valores padrão e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="4fabe-155">O cache Redis é criado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4fabe-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="4fabe-156">Recomendamos que você crie apenas um cache Redis por ambiente.</span><span class="sxs-lookup"><span data-stu-id="4fabe-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="4fabe-157">Todos os recursos foram criados agora.</span><span class="sxs-lookup"><span data-stu-id="4fabe-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="4fabe-158">Configurar os recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="4fabe-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="4fabe-159">Configurar o Hub IoT</span><span class="sxs-lookup"><span data-stu-id="4fabe-159">Configure the IoT hub</span></span>

<span data-ttu-id="4fabe-160">Para configurar o Hub IoT, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-161">Em seus recursos, selecione o recurso de Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="4fabe-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="4fabe-162">No painel de navegação esquerdo, selecione **Empresas internas**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="4fabe-163">Em **Grupos de consumidores**, cole os seguintes grupos de consumidores.</span><span class="sxs-lookup"><span data-stu-id="4fabe-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="4fabe-164">Esses grupos de consumidores correspondem aos cenários de retirada da caixa.</span><span class="sxs-lookup"><span data-stu-id="4fabe-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="4fabe-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="4fabe-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="4fabe-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="4fabe-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="4fabe-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="4fabe-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="4fabe-168">Configurar o cofre de chaves</span><span class="sxs-lookup"><span data-stu-id="4fabe-168">Configure the key vault</span></span>

<span data-ttu-id="4fabe-169">Para configurar o cofre de chaves, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-170">Em seus recursos, selecione o recurso de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="4fabe-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="4fabe-171">No painel de navegação esquerdo, selecione **Políticas de acesso**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="4fabe-172">Selecione **Adicionar uma política de acesso**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="4fabe-173">Na página **Adicionar política de acesso**, no campo **Permissões secretas**, selecione **Obter** e **Lista**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="4fabe-174">Clique em **Selecionar principal**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="4fabe-175">Na caixa de diálogo **Principal**, busque por e selecione **Microsserviços do Microsoft Dynamics ERP**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="4fabe-176">Depois selecione **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-176">Then select **Select**.</span></span>
7. <span data-ttu-id="4fabe-177">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-177">Select **Add**.</span></span>
8. <span data-ttu-id="4fabe-178">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-178">Select **Save**.</span></span>

<span data-ttu-id="4fabe-179">O aplicativo agora tem acesso aos segredos no cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="4fabe-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="4fabe-180">Salvar o segredo da cadeia de conexão do Hub IoT</span><span class="sxs-lookup"><span data-stu-id="4fabe-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="4fabe-181">Para salvar o segredo da cadeia de conexão do Hub IoT, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-182">Em seus recursos, selecione o recurso de Hub IoT.</span><span class="sxs-lookup"><span data-stu-id="4fabe-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="4fabe-183">No painel de navegação esquerdo, selecione **Empresas internas**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="4fabe-184">Copie o valor no campo **Ponto de extremidade compatível com Hub de eventos**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="4fabe-185">Vá para o recurso de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="4fabe-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="4fabe-186">No painel de navegação à esquerda, selecione **Segredos**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="4fabe-187">Selecione **Gerar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="4fabe-188">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="4fabe-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="4fabe-189">No campo **Valor**, cole o valor da empresa que você copiou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4fabe-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="4fabe-190">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="4fabe-191">Salvar o segredo da cadeia de conexão do cache Redis</span><span class="sxs-lookup"><span data-stu-id="4fabe-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="4fabe-192">Para salvar o segredo da cadeia de conexão do cache Redis, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4fabe-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="4fabe-193">Em seus recursos, selecione o recurso de cache Redis.</span><span class="sxs-lookup"><span data-stu-id="4fabe-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="4fabe-194">Selecione **Chaves de acesso**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="4fabe-195">Copie o valor no campo **Sequência de conexão primária**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="4fabe-196">Vá para o recurso de cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="4fabe-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="4fabe-197">No painel de navegação à esquerda, selecione **Segredos**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="4fabe-198">Selecione **Gerar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="4fabe-199">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="4fabe-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="4fabe-200">No campo **Valor**, cole a cadeia de conexão que você copiou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4fabe-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="4fabe-201">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4fabe-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="4fabe-202">Sempre que você atualizar uma das cadeias de conexão, deverá atualizar também os valores secretos.</span><span class="sxs-lookup"><span data-stu-id="4fabe-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="4fabe-203">Você concluiu o provisionamento dos recursos necessários do Azure.</span><span class="sxs-lookup"><span data-stu-id="4fabe-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="4fabe-204">A próxima etapa é [instalar o suplemento de Inteligência de IOT Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="4fabe-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>
