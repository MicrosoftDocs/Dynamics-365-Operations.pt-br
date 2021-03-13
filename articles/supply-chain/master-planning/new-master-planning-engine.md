---
title: Migração para a Otimização de Planejamento para o planejamento mestre
description: Este tópico fornece informações sobre o novo mecanismo de planejamento mestre, a Otimização de Planejamento, e a migração do mecanismo existente.
author: ChristianRytt
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: crytt
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8a55958a4b9573a7c3527d3d97cbcb818457b995
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007958"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a><span data-ttu-id="94e65-103">Migração para a Otimização de Planejamento para o planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="94e65-103">Migration to Planning Optimization for master planning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94e65-104">O mecanismo de planejamento mestre interno está programado para se tornar obsoleto (preterido).</span><span class="sxs-lookup"><span data-stu-id="94e65-104">The built-in master planning engine is scheduled to be made obsolete (deprecated).</span></span> <span data-ttu-id="94e65-105">Ele está sendo substituído pelo Suplemento Otimização de Planejamento para Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="94e65-105">It's being replaced by the Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="94e65-106">Este tópico fornece informações sobre o impacto em implantações novas e existentes.</span><span class="sxs-lookup"><span data-stu-id="94e65-106">This topic provides information about the impact on new and existing deployments.</span></span> <span data-ttu-id="94e65-107">Ele inclui informações sobre as ações necessárias.</span><span class="sxs-lookup"><span data-stu-id="94e65-107">It includes information about required actions.</span></span>

<span data-ttu-id="94e65-108">A Otimização de Planejamento permite que os cálculos do planejamento mestre ocorram fora do Supply Chain Management e de seu banco de dados SQL do Azure.</span><span class="sxs-lookup"><span data-stu-id="94e65-108">Planning Optimization enables master planning calculations to occur outside Supply Chain Management and its Azure SQL database.</span></span> <span data-ttu-id="94e65-109">Os benefícios associados à Otimização de Planejamento incluem desempenho aprimorado e impacto minimizado no banco de dados SQL durante as execuções do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="94e65-109">The benefits that are associated with Planning Optimization include improved performance and minimized impact on the SQL database during master planning runs.</span></span> <span data-ttu-id="94e65-110">Como execuções de planejamento rápido podem ser feitas mesmo durante o horário de expediente, os planejadores podem reagir imediatamente à demanda ou às alterações de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="94e65-110">Because quick planning runs can be done even during office hours, planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="94e65-111">Para obter mais informações sobre a Otimização de Planejamento, consulte [Visão geral da Otimização de Planejamento](planning-optimization/planning-optimization-overview.md).</span><span class="sxs-lookup"><span data-stu-id="94e65-111">For more information about Planning Optimization, see [Planning Optimization overview](planning-optimization/planning-optimization-overview.md).</span></span>

## <a name="obsolescence-of-the-existing-master-planning-engine"></a><span data-ttu-id="94e65-112">Obsolescência do mecanismo de planejamento mestre existente</span><span class="sxs-lookup"><span data-stu-id="94e65-112">Obsolescence of the existing master planning engine</span></span>

<span data-ttu-id="94e65-113">A Microsoft está no processo de tornar o mecanismo de planejamento interno obsoleto em favor da Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="94e65-113">Microsoft is in the process of making the built-in planning engine obsolete in favor of Planning Optimization.</span></span> <span data-ttu-id="94e65-114">Essa alteração afeta todos os ambientes de nuvem.</span><span class="sxs-lookup"><span data-stu-id="94e65-114">This change affects all cloud environments.</span></span> <span data-ttu-id="94e65-115">As instalações locais não são afetadas.</span><span class="sxs-lookup"><span data-stu-id="94e65-115">On-premises installations aren't affected.</span></span> <span data-ttu-id="94e65-116">Na versão 10.0.16 e posteriores, você receberá uma mensagem de erro se executar o planejamento mestre interno sem gerar ordens de produção planejadas.</span><span class="sxs-lookup"><span data-stu-id="94e65-116">In version 10.0.16 and later, you will receive an error message if you run the built-in master planning without generating planned production orders.</span></span> <span data-ttu-id="94e65-117">No entanto, a execução do planejamento mestre será concluída com êxito apesar da mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="94e65-117">However, the master planning run will be successfully completed despite the error message.</span></span>

<span data-ttu-id="94e65-118">Para obter mais informações sobre a obsolescência do mecanismo de planejamento interno, consulte os comunicados em [Recursos removidos ou preteridos no Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).</span><span class="sxs-lookup"><span data-stu-id="94e65-118">For more information about the obsolescence of the built-in planning engine, see the announcements in [Removed or deprecated features in Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).</span></span>

## <a name="migration-messages-and-exceptions"></a><span data-ttu-id="94e65-119">Migração, mensagens e exceções</span><span class="sxs-lookup"><span data-stu-id="94e65-119">Migration, messages, and exceptions</span></span>

<span data-ttu-id="94e65-120">Os proprietários de ambientes existentes que executam o mecanismo de planejamento mestre interno sem gerar ordens de produção planejadas receberão um email com detalhes sobre o processo de exceção.</span><span class="sxs-lookup"><span data-stu-id="94e65-120">Owners of existing environments who run the built-in master planning engine without generating planned production orders will receive an email that provides details about the exception process.</span></span> <span data-ttu-id="94e65-121">Recomendamos que você trabalhe com um parceiro para avaliar e planejar a migração para a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="94e65-121">We recommend that you work with a partner to evaluate and plan the migration to Planning Optimization.</span></span>

<span data-ttu-id="94e65-122">Como foi mencionado, você receberá uma mensagem de erro na versão 10.0.16 e posteriores se executar o planejamento mestre interno sem gerar ordens de produção planejadas.</span><span class="sxs-lookup"><span data-stu-id="94e65-122">As has been mentioned, you will receive an error message in version 10.0.16 and later if you run the built-in master planning without generating planned production orders.</span></span> <span data-ttu-id="94e65-123">Essa mensagem de erro inclui orientações sobre migração e instruções para solicitação de uma exceção.</span><span class="sxs-lookup"><span data-stu-id="94e65-123">This error message includes guidance about migration and instructions for requesting an exception.</span></span>

### <a name="new-deployments"></a><span data-ttu-id="94e65-124">Implantações novas</span><span class="sxs-lookup"><span data-stu-id="94e65-124">New deployments</span></span>

<span data-ttu-id="94e65-125">A Otimização de Planejamento deve ser considerada o mecanismo de planejamento mestre padrão para todas as novas implantações na nuvem.</span><span class="sxs-lookup"><span data-stu-id="94e65-125">Planning Optimization should be considered the default master planning engine for all new deployments in the cloud.</span></span> <span data-ttu-id="94e65-126">Em geral, a Otimização de Planejamento deve ser usada para todas as novas implantações que não geram ordens de produção planejadas durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="94e65-126">In general, Planning Optimization should be used for all new deployments that don't generate planned production orders during master planning.</span></span> <span data-ttu-id="94e65-127">Se uma nova implantação depender de funcionalidades às quais a Otimização de Planejamento não oferece suporte no momento, você poderá solicitar uma exceção para continuar a usar o mecanismo de planejamento mestre interno.</span><span class="sxs-lookup"><span data-stu-id="94e65-127">If a new deployment depends on functionality that Planning Optimization doesn't currently support, you can request an exception so that you can continue to use the built-in master planning engine.</span></span>

### <a name="existing-deployments"></a><span data-ttu-id="94e65-128">Implantações existentes</span><span class="sxs-lookup"><span data-stu-id="94e65-128">Existing deployments</span></span>

<span data-ttu-id="94e65-129">Os proprietários de implantações existentes baseadas na nuvem que dependem do planejamento mestre devem planejar a migração para a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="94e65-129">Owners of existing cloud-based deployments that depend on master planning should plan to migrate to Planning Optimization.</span></span> <span data-ttu-id="94e65-130">Se a sua implementação depender de funcionalidades às quais a Otimização de Planejamento não oferece suporte no momento, você poderá solicitar uma exceção para continuar a usar o mecanismo de planejamento mestre interno.</span><span class="sxs-lookup"><span data-stu-id="94e65-130">If your implementation depends on functionality that Planning Optimization doesn't currently support, you can request an exception so that you can continue to use the built-in master planning engine.</span></span>

<span data-ttu-id="94e65-131">Para ambientes que atualmente usam processos do planejamento mestre que estão se tornando obsoletos, a Microsoft enviará um email ao administrador do ambiente. Esse email fornecerá informações sobre as ações necessárias para a migração ou a solicitação de uma exceção.</span><span class="sxs-lookup"><span data-stu-id="94e65-131">For environments that currently use master planning processes that are being made obsolete, Microsoft will send an email to the environment admin. This email will provide information about the actions that are required to migrate or to request an exception.</span></span>

## <a name="the-exception-process"></a><span data-ttu-id="94e65-132">O processo de exceção</span><span class="sxs-lookup"><span data-stu-id="94e65-132">The exception process</span></span>

<span data-ttu-id="94e65-133">Você pode solicitar uma exceção se precisar continuar a usar o mecanismo de planejamento mestre interno, pois seus processos empresariais dependem muito de, pelo menos, um recurso que não está implementado na Otimização de Planejamento no momento.</span><span class="sxs-lookup"><span data-stu-id="94e65-133">You can request an exception if you must continue to use the built-in master planning engine because your business processes depends heavily on at least one feature that isn't currently implemented in Planning Optimization.</span></span> <span data-ttu-id="94e65-134">Para obter uma lista de recursos disponíveis, consulte [Análise de ajuste da Otimização de Planejamento](planning-optimization/planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="94e65-134">For a list of available features, see [Planning Optimization fit analysis](planning-optimization/planning-optimization-fit-analysis.md).</span></span>

<span data-ttu-id="94e65-135">No momento, as exceções da migração para a Otimização de Planejamento só são relevantes se o seu processo de planejamento mestre não incluir a produção (ou seja, ordens de produção planejadas geradas pelo planejamento mestre) e se você precisar do mecanismo de planejamento mestre interno além da versão 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="94e65-135">Currently, exceptions for Planning Optimization migration are only relevant if your master planning process doesn't include production (that is, planned production orders that are generated by master planning), and you require the built-in master planning engine beyond version 10.0.15.</span></span>

<span data-ttu-id="94e65-136">Depois que os recursos necessários forem disponibilizados, a Microsoft fornecerá um período de carência até a expiração da exceção.</span><span class="sxs-lookup"><span data-stu-id="94e65-136">After the required features become available, Microsoft will provide a grace period until the exception expires.</span></span> <span data-ttu-id="94e65-137">O administrador do ambiente será informado quando os recursos necessários estiverem disponíveis e o período de carência tiver começado.</span><span class="sxs-lookup"><span data-stu-id="94e65-137">The environment admin will be informed when the required features have become available and the grace period has started.</span></span>

> [!NOTE]
> <span data-ttu-id="94e65-138">Você só pode solicitar uma exceção para ambientes de produção, não para ambientes de área restrita.</span><span class="sxs-lookup"><span data-stu-id="94e65-138">You can only request an exception for production environments, not for sandbox environments.</span></span> <span data-ttu-id="94e65-139">Se você precisar desabilitar o erro de exceção da Otimização de Planejamento em um ambiente de área restrita IaaS (infraestrutura como serviço), execute a consulta SQL fornecida em [Ambientes de área restrita](#faq-sandbox).</span><span class="sxs-lookup"><span data-stu-id="94e65-139">If you need to disable the Planning Optimization exception error on an infrastructure as a service (IaaS) sandbox environment, run the SQL query provided in [Sandbox environments](#faq-sandbox).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="94e65-140">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="94e65-140">Frequently asked questions</span></span>

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a><span data-ttu-id="94e65-141">​Ambientes de área restrita​</span><span class="sxs-lookup"><span data-stu-id="94e65-141">Sandbox environments</span></span>

<span data-ttu-id="94e65-142">Posso usar o planejamento mestre interno no meu ambiente de área restrita?</span><span class="sxs-lookup"><span data-stu-id="94e65-142">Can I use built-in master planning on my sandbox environment?</span></span> <span data-ttu-id="94e65-143">Preciso de uma exceção?</span><span class="sxs-lookup"><span data-stu-id="94e65-143">Do I need an exception?</span></span>

<span data-ttu-id="94e65-144">**Resposta:** Normalmente, as exceções não são relevantes para ambientes de área restrita porque o erro de exceção da Otimização de Planejamento não impede que o mecanismo de planejamento mestre interno seja executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="94e65-144">**Answer:** Exceptions aren't normally relevant for sandbox environments because the Planning Optimization exception error doesn't prevent the built-in master planning engine from running successfully.</span></span> <span data-ttu-id="94e65-145">No entanto, se a mensagem de erro incomoda você, é possível desabilitá-la em um ambiente de área restrita IaaS (não Service Fabric) executando a seguinte consulta no seu banco de dados:</span><span class="sxs-lookup"><span data-stu-id="94e65-145">However, if the error message disturbs you, you can disable it on an IaaS (not Service Fabric) sandbox environment by running the following query on your database:</span></span>

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a><span data-ttu-id="94e65-146">Ambientes locais</span><span class="sxs-lookup"><span data-stu-id="94e65-146">On-premises environments</span></span>

<span data-ttu-id="94e65-147">Meu ambiente é local.</span><span class="sxs-lookup"><span data-stu-id="94e65-147">My environment is on-premises.</span></span> <span data-ttu-id="94e65-148">Preciso de uma exceção?</span><span class="sxs-lookup"><span data-stu-id="94e65-148">Do I need an exception?</span></span>

<span data-ttu-id="94e65-149">**Resposta:** Não.</span><span class="sxs-lookup"><span data-stu-id="94e65-149">**Answer:** No.</span></span> <span data-ttu-id="94e65-150">Uma exceção não é necessária para ambientes locais.</span><span class="sxs-lookup"><span data-stu-id="94e65-150">An exception isn't required for on-premises environments.</span></span> <span data-ttu-id="94e65-151">Você pode continuar a usar o planejamento mestre interno.</span><span class="sxs-lookup"><span data-stu-id="94e65-151">You can continue to use the built-in master planning.</span></span> <span data-ttu-id="94e65-152">O administrador do ambiente será informado se qualquer ação for necessária.</span><span class="sxs-lookup"><span data-stu-id="94e65-152">Your environment admin will be informed if any action is required.</span></span>

### <a name="production-scenarios"></a><span data-ttu-id="94e65-153">Cenários de produção</span><span class="sxs-lookup"><span data-stu-id="94e65-153">Production scenarios</span></span>

<span data-ttu-id="94e65-154">Usamos ordens de produção planejadas, mas estou preocupado com o que acontecerá quando atualizarmos para a versão 10.0.16.</span><span class="sxs-lookup"><span data-stu-id="94e65-154">We use planned production orders, but I'm concerned about what will happen when we upgrade to version 10.0.16.</span></span> <span data-ttu-id="94e65-155">Devo executar alguma ação?</span><span class="sxs-lookup"><span data-stu-id="94e65-155">Should I take any action?</span></span>

<span data-ttu-id="94e65-156">**Resposta:** Você não deve se preocupar.</span><span class="sxs-lookup"><span data-stu-id="94e65-156">**Answer:** You should not be concerned.</span></span> <span data-ttu-id="94e65-157">Você pode continuar a usar o planejamento mestre interno na versão 10.0.16.</span><span class="sxs-lookup"><span data-stu-id="94e65-157">You can continue to use the built-in master planning in version 10.0.16.</span></span> <span data-ttu-id="94e65-158">No entanto, recomendamos que você avalie se a migração para a Otimização de Planejamento pode começar com a funcionalidade atual.</span><span class="sxs-lookup"><span data-stu-id="94e65-158">However, we recommend that you evaluate whether migration to Planning Optimization can start with the current functionality.</span></span> <span data-ttu-id="94e65-159">Também recomendamos que você se mantenha informado sobre novas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="94e65-159">We also recommend that you remain informed about new functionality.</span></span>

### <a name="email-from-microsoft"></a><span data-ttu-id="94e65-160">Email da Microsoft</span><span class="sxs-lookup"><span data-stu-id="94e65-160">Email from Microsoft</span></span>

<span data-ttu-id="94e65-161">Nosso administrador de ambiente recebeu um email da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94e65-161">Our environment admin received an email from Microsoft.</span></span> <span data-ttu-id="94e65-162">Esse email informa que devemos migrar para a Otimização de Planejamento ou solicitar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="94e65-162">This email states that we should migrate to Planning Optimization or request an exception.</span></span> <span data-ttu-id="94e65-163">Preciso executar alguma ação?</span><span class="sxs-lookup"><span data-stu-id="94e65-163">Do I need to take any action?</span></span>

<span data-ttu-id="94e65-164">**Resposta:** Sim.</span><span class="sxs-lookup"><span data-stu-id="94e65-164">**Answer:** Yes.</span></span> <span data-ttu-id="94e65-165">Seu ambiente será afetado a menos que você siga as instruções do email.</span><span class="sxs-lookup"><span data-stu-id="94e65-165">Your environment will be affected unless you follow the instructions in the email.</span></span> <span data-ttu-id="94e65-166">Você pode migrar para a Otimização de Planejamento até a data especificada ou solicitar uma exceção usando o link no email.</span><span class="sxs-lookup"><span data-stu-id="94e65-166">You can either migrate to Planning Optimization by the date specified or request an exception by using the link in the email.</span></span> <span data-ttu-id="94e65-167">Esse link abre um questionário.</span><span class="sxs-lookup"><span data-stu-id="94e65-167">This link opens a questionnaire.</span></span> <span data-ttu-id="94e65-168">Depois de concluir e enviar o questionário, você receberá uma resposta por email.</span><span class="sxs-lookup"><span data-stu-id="94e65-168">After you've completed and submitted this questionnaire, you will receive a reply via email.</span></span> <span data-ttu-id="94e65-169">Embora esse processo seja manual, a Microsoft tenta responder dentro de uma semana após o envio do questionário.</span><span class="sxs-lookup"><span data-stu-id="94e65-169">Although this process is manual, Microsoft tries to reply within a week after the questionnaire is submitted.</span></span>

### <a name="error-messages"></a><span data-ttu-id="94e65-170">Mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="94e65-170">Error messages</span></span>

<span data-ttu-id="94e65-171">Estou usando a versão 10.0.16 ou posteriores e recebi a seguinte mensagem de erro ao executar o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="94e65-171">I'm using version 10.0.16 or later, and I receive the following error message when I run master planning.</span></span> <span data-ttu-id="94e65-172">O planejamento mestre está bloqueado?</span><span class="sxs-lookup"><span data-stu-id="94e65-172">Is master planning blocked?</span></span>

> <span data-ttu-id="94e65-173">Você recebeu essa mensagem de erro porque o mecanismo de planejamento mestre interno foi usado para cenários com suporte da Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="94e65-173">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="94e65-174">Você deve migrar para a Otimização de Planejamento agora, pois o planejamento mestre interno atual será preterido.</span><span class="sxs-lookup"><span data-stu-id="94e65-174">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="94e65-175">Observe que essa execução do planejamento mestre foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="94e65-175">Note that this master planning run did complete successfully.</span></span>
>
> <span data-ttu-id="94e65-176">Caso sua migração tenha fortes dependências de recursos pendentes, uma exceção para continuar o uso do mecanismo de planejamento mestre interno poderá ser solicitada.</span><span class="sxs-lookup"><span data-stu-id="94e65-176">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span>
>
> <span data-ttu-id="94e65-177">Preencha o seguinte questionário para começar e, se for o caso, solicitar uma exceção da migração para a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="94e65-177">Please complete the following questionnaire to get started and if relevant request exception from migration to Planning Optimization.</span></span>

<span data-ttu-id="94e65-178">**Resposta:** Não, o planejamento mestre não está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="94e65-178">**Answer:** No, master planning isn't blocked.</span></span> <span data-ttu-id="94e65-179">A execução do planejamento mestre foi concluída com êxito e você pode usar o resultado como de costume.</span><span class="sxs-lookup"><span data-stu-id="94e65-179">Your master planning run was successfully completed, and you can use the result in the usual way.</span></span> <span data-ttu-id="94e65-180">No entanto, para evitar o recebimento dessa mensagem de erro durante futuras execuções do planejamento mestre, você deve migrar para a Otimização de Planejamento imediatamente ou solicitar uma exceção usando o link na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="94e65-180">However, to avoid receiving this error message during future master planning runs, you must either migrate to Planning Optimization immediately or request an exception by using the link in the error message.</span></span>