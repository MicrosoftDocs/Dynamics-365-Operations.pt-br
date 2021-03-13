---
title: Componentes de administração de complemento do faturamento eletrônico
description: Este tópico fornece informações sobre os componentes relacionados à administração do complemento do faturamento eletrônico.
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
ms.openlocfilehash: 6f630ebb694217c3bd52378a649933a670c090f2
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104345"
---
# <a name="electronic-invoicing-add-on-administration-components"></a><span data-ttu-id="3c6bf-103">Componentes de administração de complemento do faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="3c6bf-103">Electronic invoicing add-on administration components</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="3c6bf-104">Este tópico fornece informações sobre os componentes relacionados à administração do complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-104">This topic provides information about the components that are related to administration of the Electronic invoicing add-on.</span></span> <span data-ttu-id="3c6bf-105">Ele também fornece informações sobre como configurar o serviço de complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-105">It also provides information about how to configure the Electronic invoicing add-on service.</span></span>

## <a name="azure"></a><span data-ttu-id="3c6bf-106">Azure</span><span class="sxs-lookup"><span data-stu-id="3c6bf-106">Azure</span></span>

<span data-ttu-id="3c6bf-107">Use o Microsoft Azure para criar os segredos para o cofre de chaves e a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="3c6bf-108">Em seguida, use os segredos na configuração do complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-108">Then use the secrets in the configuration of the Electronic invoicing add-on.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="3c6bf-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="3c6bf-109">Lifecycle Services</span></span>

<span data-ttu-id="3c6bf-110">Use o Lifecycle Services (LCS) do Microsoft Dynamics para habilitar o complemento dos microsserviços do projeto de implantação do LCS.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the add-on for the microservices for your LCS deployment project.</span></span>

<span data-ttu-id="3c6bf-111">No LCS, selecione o bloco **Gerenciamento de versão prévia do recurso** e ative o recurso **Serviço de faturamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-111">In LCS, select the **Preview feature management** tile, and then turn on the **e-Invoicing Service** feature.</span></span>

## <a name="regulatory-configuration-services"></a><span data-ttu-id="3c6bf-112">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="3c6bf-112">Regulatory Configuration Services</span></span>

<span data-ttu-id="3c6bf-113">O Regulatory Configuration Services (RCS) do Dynamics 365 é a interface usada para configurar o complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-113">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure the Electronic invoicing add-on.</span></span> <span data-ttu-id="3c6bf-114">Recursos como ambientes e recursos de faturamento eletrônico são criados, mantidos e hospedados no RCS.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-114">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="3c6bf-115">Quando os recursos estão prontos, eles são publicados no serviço de complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-115">When the resources are ready, they are published to the Electronic invoicing add-on service.</span></span>

<span data-ttu-id="3c6bf-116">Para obter mais informações sobre RCS, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="3c6bf-116">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="3c6bf-117">Integração ao complemento do faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="3c6bf-117">Integration with the Electronic invoicing add-on</span></span>

<span data-ttu-id="3c6bf-118">Para poder usar o RCS para configurar faturas eletrônicas, é necessário configurar o RCS para permitir a comunicação com o complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-118">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with the Electronic invoicing add-on.</span></span> <span data-ttu-id="3c6bf-119">Você preenche essa configuração na guia **Complemento do faturamento eletrônico** da página **Parâmetros de relatórios eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-119">You complete this configuration on the **Electronic invoicing add-on** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="3c6bf-120">Empresa do serviço</span><span class="sxs-lookup"><span data-stu-id="3c6bf-120">Service endpoint</span></span>

<span data-ttu-id="3c6bf-121">A URL do ponto de extremidade do complemento de faturamento eletrônico pode variar de acordo com a geografia do data center do Azure.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-121">The URL of the Electronic invoicing add-on endpoint can vary according to the Azure datacenter geography.</span></span> <span data-ttu-id="3c6bf-122">A seguinte tabela lista a disponibilidade por região:</span><span class="sxs-lookup"><span data-stu-id="3c6bf-122">The following table lists the availability per region:</span></span>

| <span data-ttu-id="3c6bf-123">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="3c6bf-123">Azure datacenter geography</span></span> | <span data-ttu-id="3c6bf-124">URL do ponto de extremidade do serviço</span><span class="sxs-lookup"><span data-stu-id="3c6bf-124">Service endpoint URL</span></span>                                                       |
|----------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="3c6bf-125">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="3c6bf-125">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="3c6bf-126">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="3c6bf-126">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="3c6bf-127">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="3c6bf-127">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
| <span data-ttu-id="3c6bf-128">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="3c6bf-128">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

#### <a name="application-id"></a><span data-ttu-id="3c6bf-129">ID do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="3c6bf-129">Application ID</span></span>

<span data-ttu-id="3c6bf-130">A ID do aplicativo é a ID do aplicativo do complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-130">The application ID is the ID of the Electronic invoicing add-on application.</span></span> <span data-ttu-id="3c6bf-131">Nesse caso, o valor é fixo: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-131">In this case, the value is fixed: **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

#### <a name="lcs-environment-id"></a><span data-ttu-id="3c6bf-132">ID do ambiente LCS</span><span class="sxs-lookup"><span data-stu-id="3c6bf-132">LCS environment ID</span></span>

<span data-ttu-id="3c6bf-133">A ID do ambiente LCS é a ID da subscrição de LCS da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-133">The LCS environment ID is the ID of your organization's LCS subscription.</span></span>

### <a name="service-environments"></a><span data-ttu-id="3c6bf-134">Ambientes de serviço</span><span class="sxs-lookup"><span data-stu-id="3c6bf-134">Service environments</span></span>

<span data-ttu-id="3c6bf-135">Os ambientes de serviço são partições lógicas criadas para oferecer suporte à execução de recursos de faturamento eletrônico no complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-135">Service environments are logical partitions that are created to support execution of the electronic invoicing features in the Electronic invoicing add-on.</span></span> <span data-ttu-id="3c6bf-136">Os segredos de segurança e os certificados digitais e a governança (ou seja, permissões de acesso) devem ser configurados em nível do ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-136">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="3c6bf-137">Os clientes podem criar a quantidade de ambientes de serviço desejada.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-137">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="3c6bf-138">Todos os ambientes de serviço que um cliente cria são independentes um do outro.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-138">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="3c6bf-139">Os ambientes de serviço devem ser criados e mantidos no RCS.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-139">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="3c6bf-140">Quando os ambientes de serviço estão prontos, eles devem ser publicados no complemento do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-140">When the service environments are ready, they must be published to the Electronic invoicing add-on.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="3c6bf-141">Status do ambiente de serviço</span><span class="sxs-lookup"><span data-stu-id="3c6bf-141">Service environment status</span></span>

<span data-ttu-id="3c6bf-142">Os ambientes de serviço podem ser gerenciados por meio do status.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-142">Service environments can be managed through status.</span></span> <span data-ttu-id="3c6bf-143">As opções possíveis são:</span><span class="sxs-lookup"><span data-stu-id="3c6bf-143">The possible options are:</span></span>

- <span data-ttu-id="3c6bf-144">**Não publicado** – o ambiente foi criado, mas ainda não foi publicado.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-144">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="3c6bf-145">**Publicado** – o ambiente foi publicado no complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-145">**Published** – The environment has been published to the Electronic invoicing add-on.</span></span>
- <span data-ttu-id="3c6bf-146">**Alterado** – os atributos de um ambiente publicado foram alterados, mas as alterações ainda não foram publicadas.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-146">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="3c6bf-147">Segredos do cliente</span><span class="sxs-lookup"><span data-stu-id="3c6bf-147">Customer secrets</span></span>

<span data-ttu-id="3c6bf-148">O serviço do complemento de faturamento eletrônico é responsável pelo armazenamento de todos os dados comerciais nos recursos do Azure pertencentes à sua empresa.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-148">The Electronic invoicing add-on service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="3c6bf-149">Para garantir que o serviço funcione corretamente e que todos os dados comerciais exigidos e gerados pelo complemento de faturamento eletrônico sejam acessados somente pelo complemento, crie dois recursos principais do Azure:</span><span class="sxs-lookup"><span data-stu-id="3c6bf-149">To ensure that the service works correctly, and that all the business data that is required for and generated by the Electronic invoicing add-on is accessed only by the add-on, you must create two main Azure resources:</span></span>

- <span data-ttu-id="3c6bf-150">Uma conta de armazenamento do Azure (armazenamento de Blob) que armazenará faturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="3c6bf-150">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="3c6bf-151">Um Azure Key Vault que armazenará certificados e o URI (Uniform Resource Identifier) da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="3c6bf-151">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="3c6bf-152">Um cofre de chaves dedicado e uma conta de armazenamento de cliente devem ser alocados especificamente para uso com o complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-152">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing add-on.</span></span>

<span data-ttu-id="3c6bf-153">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="3c6bf-153">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="3c6bf-154">Usuários</span><span class="sxs-lookup"><span data-stu-id="3c6bf-154">Users</span></span>

<span data-ttu-id="3c6bf-155">Cada ambiente de serviço deve listar os usuários que podem se conectar ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management no complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-155">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in the Electronic invoicing add-on.</span></span>

#### <a name="publication"></a><span data-ttu-id="3c6bf-156">Publicação</span><span class="sxs-lookup"><span data-stu-id="3c6bf-156">Publication</span></span>

<span data-ttu-id="3c6bf-157">Os ambientes de serviço devem ser publicados no complemento de faturamento eletrônico antes de serem usados.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-157">Service environments must be published to the Electronic invoicing add-on before they can be used.</span></span> <span data-ttu-id="3c6bf-158">Somente ambientes publicados podem ser acessados pelo Finance e pelo Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-158">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="3c6bf-159">Além disso, um ambiente de serviço deve ser publicado antes que as atualizações de seus atributos tenham efeito no serviço de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-159">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="3c6bf-160">Aplicativos conectados</span><span class="sxs-lookup"><span data-stu-id="3c6bf-160">Connected applications</span></span>

<span data-ttu-id="3c6bf-161">Os aplicativos conectados são as instâncias do Finance e do Supply Chain Management que você pode querer alcançar por meio do RCS.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-161">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="3c6bf-162">Além da URL do aplicativo e de seu locatário, um aplicativo conectado contém as credenciais que habilitam RCS a conectar-se ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-162">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="3c6bf-163">Por meio dos aplicativos conectados, você pode configurar parte do recurso de faturamento eletrônico no Finance e no Supply Chain Management para que todo o recurso de faturamento eletrônico funcione.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-163">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="3c6bf-164">Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3c6bf-164">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing-add-on"></a><span data-ttu-id="3c6bf-165">Integração ao complemento do faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="3c6bf-165">Integration with Electronic invoicing add-on</span></span>

<span data-ttu-id="3c6bf-166">Antes de usar o Finance e o Supply Chain Management para emitir faturas eletrônicas por meio do complemento de faturamento eletrônico, configure o complemento para permitir a comunicação com o serviço.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-166">Before you can use Finance and Supply Chain Management to issue electronic invoices through the Electronic invoicing add-on, the add-on must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="3c6bf-167">Recurso de integração de complemento de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="3c6bf-167">Electronic invoicing add-on integration feature</span></span>

<span data-ttu-id="3c6bf-168">Para habilitar a comunicação entre o Finance e o Supply Chain Management e o complemento de faturamento eletrônico, você deve ativar o recurso **Integração de complemento de faturamento eletrônico** no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-168">To enable communication between Finance and Supply Chain Management and the Electronic invoicing add-on, you must turn on the **Electronic Invoicing add-on integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="3c6bf-169">Empresa do serviço</span><span class="sxs-lookup"><span data-stu-id="3c6bf-169">Service endpoint</span></span>

<span data-ttu-id="3c6bf-170">A empresa de serviço é a URL na qual o complemento do faturamento eletrônico está localizado.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-170">The service endpoint is the URL where the Electronic invoicing add-on is located.</span></span> <span data-ttu-id="3c6bf-171">Antes da emissão de faturas eletrônicas, o ponto de extremidade de serviço deve ser configurado no Finance e no Supply Chain Management para emitir a comunicação com o serviço.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-171">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="3c6bf-172">Para configurar o ponto de extremidade de serviço, acesse **Administração da organização \> Configuração \> Parâmetro de documento eletrônico** e, depois, na guia **Serviços de envio**, no campo **URL do complemento de faturamento eletrônico**, insira a URL, conforme descrito na tabela descrita na seção **Ponto de extremidade de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-172">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing add-on URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="3c6bf-173">Ambientes</span><span class="sxs-lookup"><span data-stu-id="3c6bf-173">Environments</span></span>

<span data-ttu-id="3c6bf-174">O nome de ambiente que é inserido no Finance e no Supply Chain Management se refere ao nome do ambiente criado no RCS e publicado no complemento de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-174">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to the Electronic invoicing add-on.</span></span>

<span data-ttu-id="3c6bf-175">O ambiente deve ser configurado na guia **Serviços de envio** da página **Parâmetro de documento eletrônico**, de forma que cada solicitação para emitir faturas eletrônicas contenha o ambiente no qual o complemento de faturamento eletrônico possa determinar qual recurso de faturamento eletrônico deve processar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-175">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where the Electronic invoicing add-on can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3c6bf-176">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3c6bf-176">Additional resources</span></span>

- [<span data-ttu-id="3c6bf-177">Configurar faturas eletrônicas no RCS</span><span class="sxs-lookup"><span data-stu-id="3c6bf-177">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="3c6bf-178">Emitir faturas eletrônicas no Finance e no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3c6bf-178">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)
