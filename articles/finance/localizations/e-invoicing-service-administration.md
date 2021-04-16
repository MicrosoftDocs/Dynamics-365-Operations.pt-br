---
title: Componentes de administração de Faturamento eletrônico
description: Este tópico fornece informações sobre os componentes relacionados à administração do Faturamento eletrônico.
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
ms.openlocfilehash: 2e859875e124796e49000cd5ea94cfb75ecd768a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840019"
---
# <a name="electronic-invoicing-administration-components"></a><span data-ttu-id="7bb42-103">Componentes de administração de Faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="7bb42-103">Electronic invoicing administration components</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="7bb42-104">Este tópico fornece informações sobre os componentes relacionados à administração do Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-104">This topic provides information about the components that are related to administration of Electronic invoicing.</span></span> <span data-ttu-id="7bb42-105">Ele também fornece informações sobre como configurar o serviço de Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-105">It also provides information about how to configure the Electronic invoicing service.</span></span>

## <a name="azure"></a><span data-ttu-id="7bb42-106">Azure</span><span class="sxs-lookup"><span data-stu-id="7bb42-106">Azure</span></span>

<span data-ttu-id="7bb42-107">Use o Microsoft Azure para criar os segredos para o cofre de chaves e a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="7bb42-107">Use Microsoft Azure to create the secrets for the key vault and storage account.</span></span> <span data-ttu-id="7bb42-108">Em seguida, use os segredos na configuração do Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-108">Then use the secrets in the configuration of Electronic invoicing.</span></span>

## <a name="lifecycle-services"></a><span data-ttu-id="7bb42-109">Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="7bb42-109">Lifecycle Services</span></span>

<span data-ttu-id="7bb42-110">Use o Lifecycle Services (LCS) do Microsoft Dynamics para habilitar os microsserviços do projeto de implantação do LCS.</span><span class="sxs-lookup"><span data-stu-id="7bb42-110">Use Microsoft Dynamics Lifecycle Services (LCS) to enable the microservices for your LCS deployment project.</span></span>

> [!NOTE]
> <span data-ttu-id="7bb42-111">A instalação do microsserviço no LCS requer pelo menos uma máquina virtual de Camada 2.</span><span class="sxs-lookup"><span data-stu-id="7bb42-111">The installation of the microservice in LCS requires at least a Tier 2 virtual machine.</span></span> <span data-ttu-id="7bb42-112">Para obter mais informações sobre o planejamento de ambiente, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="7bb42-112">For more information about environment planning, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
 

## <a name="regulatory-configuration-services"></a><span data-ttu-id="7bb42-113">Regulatory Configuration Services</span><span class="sxs-lookup"><span data-stu-id="7bb42-113">Regulatory Configuration Services</span></span>

<span data-ttu-id="7bb42-114">O Regulatory Configuration Services (RCS) do Dynamics 365 é a interface usada para configurar o Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-114">Dynamics 365 Regulatory Configuration Services (RCS) is the interface that is used to configure Electronic invoicing.</span></span> <span data-ttu-id="7bb42-115">Recursos como ambientes e recursos de faturamento eletrônico são criados, mantidos e hospedados no RCS.</span><span class="sxs-lookup"><span data-stu-id="7bb42-115">Resources such as environments and electronic invoicing features are created, maintained, and hosted in RCS.</span></span> <span data-ttu-id="7bb42-116">Quando os recursos estão prontos, eles são publicados no serviço de Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-116">When the resources are ready, they are published to Electronic invoicing service.</span></span>

<span data-ttu-id="7bb42-117">Para inscrição no RCS, consulte [Regulatory services](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="7bb42-117">For RCS sign-up, see [Regulatory services](https://marketing.configure.global.dynamics.com/).</span></span>

<span data-ttu-id="7bb42-118">Para obter mais informações sobre RCS, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md)</span><span class="sxs-lookup"><span data-stu-id="7bb42-118">For more information about RCS, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md)</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="7bb42-119">Integração ao Faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="7bb42-119">Integration with Electronic invoicing</span></span> 

<span data-ttu-id="7bb42-120">Para poder usar o RCS para configurar faturas eletrônicas, é necessário configurar o RCS para permitir a comunicação com o Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-120">Before you can use RCS to configure electronic invoices, you must configure RCS to allow for communication with Electronic invoicing.</span></span> <span data-ttu-id="7bb42-121">Você preenche essa configuração na guia **Faturamento eletrônico** da página **Parâmetros de relatórios eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="7bb42-121">You complete this configuration on the **Electronic invoicing** tab of the **Electronic reporting parameters** page.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="7bb42-122">Empresa do serviço</span><span class="sxs-lookup"><span data-stu-id="7bb42-122">Service endpoint</span></span>

<span data-ttu-id="7bb42-123">O Faturamento eletrônico está disponível em várias regiões do datacenter do Azure.</span><span class="sxs-lookup"><span data-stu-id="7bb42-123">Electronic invoicing is available in several Azure datacenter geographies.</span></span> <span data-ttu-id="7bb42-124">A seguinte tabela lista a disponibilidade por região.</span><span class="sxs-lookup"><span data-stu-id="7bb42-124">The following table lists the availability per region.</span></span>

| <span data-ttu-id="7bb42-125">Geografia do data center Azure</span><span class="sxs-lookup"><span data-stu-id="7bb42-125">Azure datacenter geography</span></span> |
|----------------------------|
| <span data-ttu-id="7bb42-126">Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="7bb42-126">East US</span></span>                    |
| <span data-ttu-id="7bb42-127">Oeste dos EUA</span><span class="sxs-lookup"><span data-stu-id="7bb42-127">West US</span></span>                    |
| <span data-ttu-id="7bb42-128">Norte da UE</span><span class="sxs-lookup"><span data-stu-id="7bb42-128">North EU</span></span>                   |
| <span data-ttu-id="7bb42-129">Oeste da UE</span><span class="sxs-lookup"><span data-stu-id="7bb42-129">West EU</span></span>                    |

### <a name="service-environments"></a><span data-ttu-id="7bb42-130">Ambientes de serviço</span><span class="sxs-lookup"><span data-stu-id="7bb42-130">Service environments</span></span>

<span data-ttu-id="7bb42-131">Os ambientes de serviço são partições lógicas criadas para oferecer suporte à execução de recursos de faturamento eletrônico no Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-131">Service environments are logical partitions that are created to support execution of the electronic invoicing features in Electronic invoicing.</span></span> <span data-ttu-id="7bb42-132">Os segredos de segurança e os certificados digitais e a governança (ou seja, permissões de acesso) devem ser configurados em nível do ambiente de serviço.</span><span class="sxs-lookup"><span data-stu-id="7bb42-132">The security secrets and digital certificates, and the governance (that is, access permissions), must be configured at the service environment level.</span></span>

<span data-ttu-id="7bb42-133">Os clientes podem criar a quantidade de ambientes de serviço desejada.</span><span class="sxs-lookup"><span data-stu-id="7bb42-133">Customers can create as many service environments as they want.</span></span> <span data-ttu-id="7bb42-134">Todos os ambientes de serviço que um cliente cria são independentes um do outro.</span><span class="sxs-lookup"><span data-stu-id="7bb42-134">All the service environments that a customer creates are independent of each other.</span></span>

<span data-ttu-id="7bb42-135">Os ambientes de serviço devem ser criados e mantidos no RCS.</span><span class="sxs-lookup"><span data-stu-id="7bb42-135">Service environments must be created and maintained in RCS.</span></span> <span data-ttu-id="7bb42-136">Quando os ambientes de serviço estão prontos, eles devem ser publicados no Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-136">When the service environments are ready, they must be published to Electronic invoicing.</span></span>

#### <a name="service-environment-status"></a><span data-ttu-id="7bb42-137">Status do ambiente de serviço</span><span class="sxs-lookup"><span data-stu-id="7bb42-137">Service environment status</span></span>

<span data-ttu-id="7bb42-138">Os ambientes de serviço podem ser gerenciados por meio do status.</span><span class="sxs-lookup"><span data-stu-id="7bb42-138">Service environments can be managed through status.</span></span> <span data-ttu-id="7bb42-139">As opções possíveis são:</span><span class="sxs-lookup"><span data-stu-id="7bb42-139">The possible options are:</span></span>

- <span data-ttu-id="7bb42-140">**Não publicado** – o ambiente foi criado, mas ainda não foi publicado.</span><span class="sxs-lookup"><span data-stu-id="7bb42-140">**Not published** – The environment has been created, but it hasn't yet been published.</span></span>
- <span data-ttu-id="7bb42-141">**Publicado** – o ambiente foi publicado no Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-141">**Published** – The environment has been published to Electronic invoicing .</span></span>
- <span data-ttu-id="7bb42-142">**Alterado** – os atributos de um ambiente publicado foram alterados, mas as alterações ainda não foram publicadas.</span><span class="sxs-lookup"><span data-stu-id="7bb42-142">**Changed** – The attributes of a published environment have been changed, but the changes haven't yet been published.</span></span>

#### <a name="customer-secrets"></a><span data-ttu-id="7bb42-143">Segredos do cliente</span><span class="sxs-lookup"><span data-stu-id="7bb42-143">Customer secrets</span></span>

<span data-ttu-id="7bb42-144">O serviço de Faturamento eletrônico é responsável pelo armazenamento de todos os dados comerciais nos recursos do Azure pertencentes à sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7bb42-144">The Electronic invoicing service is responsible for storing all your business data in the Azure resources that your company owns.</span></span> <span data-ttu-id="7bb42-145">Para garantir que o serviço funcione corretamente e que todos os dados comerciais necessários e gerados pelo Faturamento eletrônico sejam acessados corretamente, crie dois recursos principais do Azure:</span><span class="sxs-lookup"><span data-stu-id="7bb42-145">To ensure that the service works correctly, and that all the business data that is required for and generated by Electronic invoicing is accessed appropriately, you must create two main Azure resources:</span></span>

- <span data-ttu-id="7bb42-146">Uma conta de armazenamento do Azure (armazenamento de Blob) que armazenará faturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="7bb42-146">An Azure storage account (Blob storage) that will store electronic invoices</span></span>
- <span data-ttu-id="7bb42-147">Um Azure Key Vault que armazenará certificados e o URI (Uniform Resource Identifier) da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="7bb42-147">An Azure key vault that will store certificates and the uniform resource identifier (URI) of the storage account</span></span>

> [!NOTE]
> <span data-ttu-id="7bb42-148">Um cofre de chaves dedicado e uma conta de armazenamento de cliente devem ser alocados especificamente para uso com o Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-148">A dedicated key vault and customer storage account must be allocated specifically for use with the Electronic invoicing .</span></span>

<span data-ttu-id="7bb42-149">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="7bb42-149">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

#### <a name="users"></a><span data-ttu-id="7bb42-150">Usuários</span><span class="sxs-lookup"><span data-stu-id="7bb42-150">Users</span></span>

<span data-ttu-id="7bb42-151">Cada ambiente de serviço deve listar os usuários que podem se conectar ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management no Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-151">Each service environment must list the users who can connect from Dynamics 365 Finance and Dynamics 365 Supply Chain Management in Electronic invoicing.</span></span>

#### <a name="publication"></a><span data-ttu-id="7bb42-152">Publicação</span><span class="sxs-lookup"><span data-stu-id="7bb42-152">Publication</span></span>

<span data-ttu-id="7bb42-153">Os ambientes de serviço devem ser publicados no Faturamento eletrônico antes de serem usados.</span><span class="sxs-lookup"><span data-stu-id="7bb42-153">Service environments must be published to Electronic invoicing before they can be used.</span></span> <span data-ttu-id="7bb42-154">Somente ambientes publicados podem ser acessados pelo Finance e pelo Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="7bb42-154">Only published environments can be accessed by Finance and Supply Chain Management.</span></span> <span data-ttu-id="7bb42-155">Além disso, um ambiente de serviço deve ser publicado antes que as atualizações de seus atributos tenham efeito no serviço de faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-155">Additionally, a service environment must be published before any updates to its attributes will take effect on the electronic invoicing service.</span></span>

### <a name="connected-applications"></a><span data-ttu-id="7bb42-156">Aplicativos conectados</span><span class="sxs-lookup"><span data-stu-id="7bb42-156">Connected applications</span></span>

<span data-ttu-id="7bb42-157">Os aplicativos conectados são as instâncias do Finance e do Supply Chain Management que você pode querer alcançar por meio do RCS.</span><span class="sxs-lookup"><span data-stu-id="7bb42-157">Connected applications are the instances of Finance and Supply Chain Management that you might want to reach through RCS.</span></span> <span data-ttu-id="7bb42-158">Além da URL do aplicativo e de seu locatário, um aplicativo conectado contém as credenciais que habilitam RCS a conectar-se ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="7bb42-158">Besides the application URL and its tenant, a connected application contains the credentials that enable RCS to connect to the environment.</span></span>

<span data-ttu-id="7bb42-159">Por meio dos aplicativos conectados, você pode configurar parte do recurso de faturamento eletrônico no Finance e no Supply Chain Management para que todo o recurso de faturamento eletrônico funcione.</span><span class="sxs-lookup"><span data-stu-id="7bb42-159">Through the connected applications, you can configure part of the electronic invoicing feature in Finance and Supply Chain Management to make the whole electronic invoicing feature work.</span></span>

## <a name="finance-and-supply-chain-management"></a><span data-ttu-id="7bb42-160">Finance e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="7bb42-160">Finance and Supply Chain Management</span></span>

### <a name="integration-with-electronic-invoicing"></a><span data-ttu-id="7bb42-161">Integração ao Faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="7bb42-161">Integration with Electronic invoicing</span></span>

<span data-ttu-id="7bb42-162">Antes de usar o Finance e o Supply Chain Management para emitir faturas eletrônicas por meio do Faturamento eletrônico, ele deve ser configurado para permitir a comunicação com o serviço.</span><span class="sxs-lookup"><span data-stu-id="7bb42-162">Before you can use Finance and Supply Chain Management to issue electronic invoices through Electronic invoicing, it must be configured to allow for communication with the service.</span></span>

#### <a name="electronic-invoicing-integration-feature"></a><span data-ttu-id="7bb42-163">Recurso de integração de faturamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="7bb42-163">Electronic invoicing integration feature</span></span>

<span data-ttu-id="7bb42-164">Para habilitar a comunicação entre o Finance e o Supply Chain Management e o Faturamento eletrônico, você deve ativar o recurso **Integração de Faturamento eletrônico** no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="7bb42-164">To enable communication between Finance and Supply Chain Management and Electronic invoicing, you must turn on the **Electronic Invoicing integration** feature in the **Feature management** workspace.</span></span>

#### <a name="service-endpoint"></a><span data-ttu-id="7bb42-165">Empresa do serviço</span><span class="sxs-lookup"><span data-stu-id="7bb42-165">Service endpoint</span></span>

<span data-ttu-id="7bb42-166">A empresa de serviço é a URL na qual o Faturamento eletrônico está localizado.</span><span class="sxs-lookup"><span data-stu-id="7bb42-166">The service endpoint is the URL where Electronic invoicing is located.</span></span> <span data-ttu-id="7bb42-167">Antes da emissão de faturas eletrônicas, o ponto de extremidade de serviço deve ser configurado no Finance e no Supply Chain Management para emitir a comunicação com o serviço.</span><span class="sxs-lookup"><span data-stu-id="7bb42-167">Before electronic invoices can be issued, the service endpoint must be configured in Finance and Supply Chain Management to allow for communication with the service.</span></span>

<span data-ttu-id="7bb42-168">Para configurar o ponto de extremidade de serviço, acesse **Administração da organização \> Configuração \> Parâmetro de documento eletrônico** e, depois, na guia **Serviços de envio**, no campo **URL do Faturamento eletrônico**, insira a URL, conforme descrito na tabela descrita na seção **Ponto de extremidade de serviço**.</span><span class="sxs-lookup"><span data-stu-id="7bb42-168">To configure the service endpoint, go to **Organization administration \> Setup \> Electronic document parameter**, and then, on the **Submission services** tab, in the **Electronic invoicing URL** field, enter the URL as described in the table described in section **Service endpoint**.</span></span>

#### <a name="environments"></a><span data-ttu-id="7bb42-169">Ambientes</span><span class="sxs-lookup"><span data-stu-id="7bb42-169">Environments</span></span>

<span data-ttu-id="7bb42-170">O nome de ambiente que é inserido no Finance e no Supply Chain Management se refere ao nome do ambiente criado no RCS e publicado no Faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7bb42-170">The environment name that is entered in Finance and Supply Chain Management refers to the name of the environment that is created in RCS and published to Electronic invoicing.</span></span>

<span data-ttu-id="7bb42-171">O ambiente deve ser configurado na guia **Serviços de envio** da página **Parâmetro de documento eletrônico**, de forma que cada solicitação para emitir faturas eletrônicas contenha o ambiente no qual o Faturamento eletrônico possa determinar qual recurso de faturamento eletrônico deve processar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="7bb42-171">The environment must be configured on the **Submission services** tab of the **Electronic document parameter** page, so that every request to issue electronic invoices contains the environment where Electronic invoicing can determine which electronic invoicing feature must process the request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7bb42-172">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7bb42-172">Additional resources</span></span>

- [<span data-ttu-id="7bb42-173">Configurar faturas eletrônicas no RCS</span><span class="sxs-lookup"><span data-stu-id="7bb42-173">Configure electronic invoices in RCS</span></span>](e-invoicing-configuration-rcs.md)
- [<span data-ttu-id="7bb42-174">Emitir faturas eletrônicas no Finance e no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="7bb42-174">Issue electronic invoices in Finance and Supply Chain Management</span></span>](e-invoicing-issuing-electronic-invoices-finance-supply-chain-management.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
