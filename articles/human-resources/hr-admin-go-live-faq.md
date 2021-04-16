---
title: ​Perguntas frequentes sobre ativação​
description: Este tópico lista as perguntas frequentes sobre como ativar um projeto de implementação do Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4a06da220fd90de91fb9091c41f35a1fb95442c3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804008"
---
# <a name="go-live-faq"></a><span data-ttu-id="3f3fb-103">​Perguntas frequentes sobre ativação​</span><span class="sxs-lookup"><span data-stu-id="3f3fb-103">Go-live FAQ</span></span> 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3f3fb-104">Este tópico lista as perguntas frequentes sobre como ativar um projeto de implementação do Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-104">This topic lists frequently asked questions about how to go live with a Dynamics 365 Human Resources implementation project.</span></span> 

## <a name="when-can-i-configure-and-request-my-production-environment"></a><span data-ttu-id="3f3fb-105">Quando posso configurar e solicitar meu ambiente de produção?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-105">When can I configure and request my production environment?</span></span> 

<span data-ttu-id="3f3fb-106">Normalmente, um ambiente de produção é implantado depois de atender aos seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="3f3fb-106">Typically, a production environment is deployed after meeting the following criteria:</span></span>

- <span data-ttu-id="3f3fb-107">Todas as personalizações têm conclusão de código.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-107">All customizations are code-complete.</span></span>
- <span data-ttu-id="3f3fb-108">O teste de aceitação do usuário (UAT) está concluído.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-108">User acceptance testing (UAT) is complete.</span></span>
- <span data-ttu-id="3f3fb-109">O cliente saiu da solução.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-109">The customer has signed off on the solution.</span></span>
- <span data-ttu-id="3f3fb-110">Não há problemas de bloqueio para a ativação.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-110">There are no blocking issues for go-live.</span></span> 

<span data-ttu-id="3f3fb-111">Quando clientes qualificados estão nesse estágio, a equipe do Microsoft FastTrack trabalhará com a equipe do projeto para realizar uma avaliação de ativação.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-111">When qualified customers are at this stage, the Microsoft FastTrack team will work with the project team to do a go-live assessment.</span></span> 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a><span data-ttu-id="3f3fb-112">Quais são os pré-requisitos para a implantação de um ambiente de produção?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-112">What are the prerequisites to deploying a production environment?</span></span> 

<span data-ttu-id="3f3fb-113">Para obter uma lista dos pré-requisitos, consulte  [Preparar-se para a ativação](hr-admin-go-live-prepare.md).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-113">For a list of the prerequisites, see [Prepare for go-live](hr-admin-go-live-prepare.md).</span></span> 

## <a name="what-is-a-go-live-assessment"></a><span data-ttu-id="3f3fb-114">O que é uma avaliação de ativação?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-114">What is a go-live assessment?</span></span>  

<span data-ttu-id="3f3fb-115">A avaliação de ativação é parte do  [programa Microsoft FastTrack ](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-115">The go-live assessment is part of the [Microsoft FastTrack program](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview).</span></span> <span data-ttu-id="3f3fb-116">Durante esta revisão, o arquiteto de soluções avalia se um projeto de implementação está pronto para uma transição e uma ativação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-116">During this review, a solution architect assesses whether an implementation project is ready for a successful cutover and go-live.</span></span> <span data-ttu-id="3f3fb-117">Esta revisão é obrigatória para todos os projetos de implementação antes que você possa solicitar a ativação em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-117">This review is mandatory for every implementation project before you can request to go live in a production environment.</span></span> 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a><span data-ttu-id="3f3fb-118">Nossos ambientes de Área restrita são implantados no data center EUA Central.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-118">Our Sandbox environments are deployed in the Central US datacenter.</span></span> <span data-ttu-id="3f3fb-119">Queremos que nossos Ambientes de produção sejam implantados no datacenter Oeste dos EUA.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-119">We want our Production environments to be deployed in the West US datacenter.</span></span> <span data-ttu-id="3f3fb-120">Posso selecionar Oeste dos EUA como o data center em minha configuração de Produção?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-120">Can I select West US as the datacenter in my Production configuration?</span></span> 

<span data-ttu-id="3f3fb-121">O LCS não impede que você selecione um data center diferente ao implantar um ambiente do Human Resources, mas é altamente recomendável não selecionar um data center diferente.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-121">LCS doesn't restrict you from selecting a different data center when you deploy a Human Resources environment, but we strongly recommend not selecting a different data center.</span></span>  

<span data-ttu-id="3f3fb-122">Se você deseja que seu ambiente de Produção esteja no data center Oeste dos EUA, primeiro implante os ambientes de Área Restrita no data center Oeste dos EUA, teste-os e saia.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-122">If you want your Production environment to be in the West US datacenter, you should first redeploy your Sandbox environments to the West US datacenter, test them, and sign off.</span></span> 

<span data-ttu-id="3f3fb-123">Para obter informações sobre como selecionar o datacenter correto, consulte [Requisitos de rede](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-123">For information about selecting the correct datacenter, see [Network requirements](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements).</span></span> 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a><span data-ttu-id="3f3fb-124">Que nível de acesso tenho para os recursos do Azure para meus ambientes do Human Resources?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-124">What level of access do I have to the Azure resources for my Human Resources environments?</span></span>  

<span data-ttu-id="3f3fb-125">O acesso aos ambientes do Human Resources é limitado.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-125">Access to the Human Resources environments is limited.</span></span> <span data-ttu-id="3f3fb-126">Não é possível acessar a máquina virtual (VM) ou o Serviços de Informações da Internet da Microsoft (IIS).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-126">You can't access the virtual machine (VM) or Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="3f3fb-127">Também não é possível acessar o banco de dados por meio do Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-127">You also can't access the database through Microsoft SQL Server Management Studio.</span></span> 

<span data-ttu-id="3f3fb-128">Embora não seja possível acessar diretamente os recursos do Azure ou o ambiente do Dynamics 365 Human Resources diretamente, há recursos adicionais que você pode usar para acessar seus dados:</span><span class="sxs-lookup"><span data-stu-id="3f3fb-128">Although you can't access your Azure resources or Dynamics 365 Human Resources environment directly, there are additional features you can use to access your data:</span></span>

- <span data-ttu-id="3f3fb-129">Você pode implantar um banco de dados SQL do Azure no seu próprio locatário do Azure e usar o recurso BYOD (Trazer Seu Próprio Banco de Dados) para sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-129">You can deploy an Azure SQL database in your own Azure tenant and use the Bring Your Own Database (BYOD) feature to synchronize data.</span></span> <span data-ttu-id="3f3fb-130">Para obter mais informações, consulte [Trazer seu próprio banco de dados (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-130">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span>

- <span data-ttu-id="3f3fb-131">Você pode usar a integração do Dataverse para sincronizar as entidades selecionadas no banco de dados do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-131">You can use Dataverse integration to synchronize select entities into the Dataverse database.</span></span> <span data-ttu-id="3f3fb-132">Para obter mais informações, consulte [Tabelas do Dataverse](hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-132">For more information, see [Dataverse tables](hr-developer-entities.md).</span></span> 

## <a name="how-often-is-my-production-database-backed-up"></a><span data-ttu-id="3f3fb-133">Com que frequência é feito o backup do meu banco de dados de produção?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-133">How often is my production database backed up?</span></span> 

<span data-ttu-id="3f3fb-134">Os bancos de dados são protegidos por backups automáticos nas seguintes frequências:</span><span class="sxs-lookup"><span data-stu-id="3f3fb-134">Databases are protected by automatic backups at the following frequencies:</span></span>

| <span data-ttu-id="3f3fb-135">Tipo de backup</span><span class="sxs-lookup"><span data-stu-id="3f3fb-135">Type of backup</span></span> | <span data-ttu-id="3f3fb-136">Frequência</span><span class="sxs-lookup"><span data-stu-id="3f3fb-136">Frequency</span></span> |
| --- | --- |
| <span data-ttu-id="3f3fb-137">Backup completo do banco de dados</span><span class="sxs-lookup"><span data-stu-id="3f3fb-137">Full database backup</span></span> | <span data-ttu-id="3f3fb-138">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="3f3fb-138">Weekly</span></span> |
| <span data-ttu-id="3f3fb-139">Backup diferencial do banco de dados</span><span class="sxs-lookup"><span data-stu-id="3f3fb-139">Differential database backup</span></span> | <span data-ttu-id="3f3fb-140">A cada 12-24 horas</span><span class="sxs-lookup"><span data-stu-id="3f3fb-140">Every 12-24 hours</span></span> |
| <span data-ttu-id="3f3fb-141">Backup do log de transações</span><span class="sxs-lookup"><span data-stu-id="3f3fb-141">Transaction log backup</span></span> | <span data-ttu-id="3f3fb-142">A cada 5 a 10 minutos</span><span class="sxs-lookup"><span data-stu-id="3f3fb-142">Every 5 to 10 minutes</span></span> |

<span data-ttu-id="3f3fb-143">A Microsoft mantém backups suficientes para permitir a Recuperação Pontual (PITR) nos últimos 14 dias.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-143">Microsoft retains sufficient backups to allow for Point in Time Restore (PITR) within the last 14 days.</span></span> 

<span data-ttu-id="3f3fb-144">Para obter mais informações sobre os backups, consulte  [Saber mais sobre backups automáticos do Banco de Dados SQL](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-144">For more information, see [Learn about automatic SQL Database backups](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database).</span></span> 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a><span data-ttu-id="3f3fb-145">Posso solicitar uma cópia do backup do meu banco de dados de produção?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-145">Can I request a copy of the backup of my production database?</span></span> 

<span data-ttu-id="3f3fb-146">Nº</span><span class="sxs-lookup"><span data-stu-id="3f3fb-146">No.</span></span> <span data-ttu-id="3f3fb-147">No entanto, você pode enviar uma solicitação de serviço de atualização de banco de dados para copiar seu Ambiente de produção para o Ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-147">You can submit a database refresh service request to copy your Production environment to your Sandbox environment, however.</span></span> <span data-ttu-id="3f3fb-148">Você pode implantar um banco de dados SQL do Azure no seu próprio locatário do Azure e usar o recurso BYOD (Trazer Seu Próprio Banco de Dados) para sincronizar dados do seu Ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-148">You can deploy an Azure SQL database in your own Azure tenant and use the BYOD feature to synchronize data from your Production environment.</span></span> <span data-ttu-id="3f3fb-149">Para obter mais informações, consulte [Trazer seu próprio banco de dados (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-149">For more information, see [Bring your own database (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).</span></span> 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a><span data-ttu-id="3f3fb-150">Como posso mover meu ambiente de Área restrita para Produção para ativação?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-150">How do I move my Sandbox environment to Production for go-live?</span></span> 

<span data-ttu-id="3f3fb-151">Como um recurso de cópia não está disponível para mover seu ambiente de uma Área restrita para um Ambiente de produção, você deverá usar pacotes de dados para mover os dados para o Ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-151">Because a copy feature isn't available to move your environment from a Sandbox to a Production environment, you must use data packages to move data into your Production environment.</span></span>  

<span data-ttu-id="3f3fb-152">É recomendável manter uma lista clara das entidades configuradas em sua Área restrita ao longo do projeto.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-152">We recommend maintaining a clear list of entities configured in your Sandbox throughout the project.</span></span> <span data-ttu-id="3f3fb-153">Em seguida, teste o processo de substituição e migração de quaisquer pacotes de dados necessários para sua ativação.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-153">Then test the process of cutover and migration of any data packages needed for your go-live.</span></span> <span data-ttu-id="3f3fb-154">Você deve mover manualmente todos os pacotes de dados para o Ambiente de produção quando estiver pronto para a ativação.</span><span class="sxs-lookup"><span data-stu-id="3f3fb-154">You must manually move any data packages into the Production environment when you are ready to go live.</span></span> 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a><span data-ttu-id="3f3fb-155">O que devo fazer se meu Ambiente de produção estiver inativo?</span><span class="sxs-lookup"><span data-stu-id="3f3fb-155">What should I do if my Production environment is down?</span></span> 

<span data-ttu-id="3f3fb-156">Para relatar uma interrupção de Produção, siga o processo descrito em  [Informar uma interrupção de produção](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span><span class="sxs-lookup"><span data-stu-id="3f3fb-156">To report a Production outage, follow the process described in [Report a production outage](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage).</span></span> 

 ## <a name="see-also"></a><span data-ttu-id="3f3fb-157">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3f3fb-157">See also</span></span>

 [<span data-ttu-id="3f3fb-158">Preparar para a ativação</span><span class="sxs-lookup"><span data-stu-id="3f3fb-158">Prepare for go-live</span></span>](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]