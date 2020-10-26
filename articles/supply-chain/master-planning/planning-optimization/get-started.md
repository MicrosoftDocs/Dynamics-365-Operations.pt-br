---
title: Introdução à Otimização de Planejamento
description: Este tópico explica como começar a usar a funcionalidade Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 49025d0aa0f6a627b816a43dd4260449942b400c
ms.sourcegitcommit: ae04c7cb48f7ecafe71bbe77a0f97715e6290991
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973467"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="4d9c8-103">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4d9c8-104">Como [anunciado anteriormente](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), a Otimização de Planejamento está agendada para substituir o mecanismo de planejamento mestre existente.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-104">As [previously announced](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), Planning Optimization is scheduled to replace the existing built-in master planning engine.</span></span>

<span data-ttu-id="4d9c8-105">Se estiver usando o mecanismo de planejamento mestre interno no momento, você deverá começar a planejar a migração para a Otimização de Planejamento agora.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-105">If you currently use the built-in master planning engine, you should start planning your migration to Planning Optimization now.</span></span> <span data-ttu-id="4d9c8-106">É importante iniciar o processo de migração imediatamente porque suas operações poderão ser afetadas quando a substituição for imposta.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-106">It is important to start the migration process right away because your operations may be impacted when deprecation is enforced.</span></span> <span data-ttu-id="4d9c8-107">Para evitar problemas de última hora quando a substituição for imposta, é altamente recomendável que você conclua a migração antes de 1º de dezembro de 2020.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-107">To avoid last-minutes issues when deprecation is enforced, we strongly encourage you to complete the migration before December 1, 2020.</span></span> 

<span data-ttu-id="4d9c8-108">No momento, a funcionalidade Otimização de Planejamento não dá suporte a todos os recursos disponíveis no mecanismo de planejamento interno do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-108">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Supply Chain Management.</span></span> <span data-ttu-id="4d9c8-109">Portanto, é importante que você avalie se o conjunto de recursos disponível no momento na Otimização de Planejamento atenderá aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-109">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="4d9c8-110">No momento, a funcionalidade Otimização de Planejamento não está ativada por padrão no Dynamics Lifecycle Services (LCS), de modo que você tem a oportunidade de fazer a avaliação antes do recurso ser ativado.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-110">The Planning Optimization functionality isn't currently turned on by default in Dynamics Lifecycle Services (LCS), so you have the opportunity to do your evaluation before the feature is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9c8-111">Você precisará solicitar uma exceção da migração para a Otimização de Planejamento se o processo de planejamento mestre não incluir a produção (ordens de produção planejadas geradas pelo planejamento mestre) e se precisar do mecanismo de planejamento mestre interno além da versão 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-111">You need to request an exception from migration to Planning Optimization if your master planning process does not include production (master planning generated planned production orders) and you require the built-in master planning engine beyond version 10.0.15.</span></span> <span data-ttu-id="4d9c8-112">A partir da versão 10.0.16, um erro será mostrado nos ambientes durante a execução do planejamento mestre interno sem a geração de ordens de produção planejadas.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-112">Starting in version 10.0.16, an error will be shown in environments when running built-in master planning without generation of planned production orders.</span></span> <span data-ttu-id="4d9c8-113">A Otimização de Planejamento deverá ser usada para todas as novas implantações que não gerem ordens de produção planejadas durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-113">Planning Optimization should be used for all new deployments that do not generate planned production orders during master planning.</span></span> <span data-ttu-id="4d9c8-114">Os proprietários de ambientes existentes que executam o mecanismo de planejamento mestre interno sem a geração de ordens de produção planejadas receberão um email com detalhes sobre o processo de exceção.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-114">Owners of existing environments running the built-in master planning engine without generation of Planned production orders, will receive a mail with details about the exception process.</span></span> <span data-ttu-id="4d9c8-115">Recomendamos que você trabalhe com um parceiro para avaliar e planejar a migração para a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-115">We recommend that you work with a partner to evaluate and plan the migration to Planning Optimization.</span></span>

<span data-ttu-id="4d9c8-116">Antes de ativar a Otimização de Planejamento, recomendamos enfaticamente que você avalie os resultados da análise de ajuste da Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-116">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="4d9c8-117">Para obter mais informações, consulte [Introdução à análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c8-117">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="4d9c8-118">Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="4d9c8-118">Availability</span></span>
<span data-ttu-id="4d9c8-119">A otimização de planejamento está disponível atualmente nos seguintes ambientes do Azure: Estados Unidos, Canadá, Europa, Reino Unido e Austrália.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-119">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="4d9c8-120">Se você tentar instalar o suplemento de outra região geográfica, o LCS mostrará uma mensagem informando que esse ambiente não é suportado.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-120">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="4d9c8-121">Observe que a otimização de planejamento não oferece suporte a implantações locais do Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-121">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="4d9c8-122">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-122">Licensing</span></span>

<span data-ttu-id="4d9c8-123">Se você puder executar o planejamento mestre usando a licença atual, não terá de comprar uma licença adicional para começar a usar a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-123">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="4d9c8-124">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-124">Install the add-in</span></span>

<span data-ttu-id="4d9c8-125">Para usar a Otimização de Planejamento, instale o Suplemento Otimização de Planejamento para o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-125">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="4d9c8-126">Você pode acessar o suplemento do seu projeto do LCS e ativar a funcionalidade Otimização de Planejamento da interface do usuário (IU) do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-126">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="4d9c8-127">A necessidade de Otimização do Planejamento é um ambiente de alta disponibilidade habilitado para LCS, camada 2 ou superior (não um ambiente OneBox), com o Dynamics 365 Supply Chain Management versão 10.0.7 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-127">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="4d9c8-128">Se você tentar instalar o suplemento em um ambiente do OneBox, a instalação não será concluída e será necessário cancelar a instalação.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-128">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="4d9c8-129">Entre no LCS e abra o ambiente desejado.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-129">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="4d9c8-130">Vá para **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="4d9c8-131">Role para baixo até a Guia Rápida **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-131">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="4d9c8-132">Selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-132">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="4d9c8-133">Selecione **Otimização de Planejamento**.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-133">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="4d9c8-134">Acompanhe o guia de instalação e concorde com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-134">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="4d9c8-135">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-135">Select **Install**.</span></span>
1. <span data-ttu-id="4d9c8-136">Na Guia Rápida **Suplementos de ambiente**, você deverá ver que a Otimização do Planejamento está instalando.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-136">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="4d9c8-137">Após alguns minutos, **Instalando** deve mudar para **Instalado** (talvez você precise atualizar a página).</span><span class="sxs-lookup"><span data-stu-id="4d9c8-137">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="4d9c8-138">Quando instalado, você estará pronto para ativar a Otimização do Planejamento no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-138">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="4d9c8-139">Integração da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-139">Planning Optimization integration</span></span>

<span data-ttu-id="4d9c8-140">Para configurar se o Suplemento Otimização do Planejamento deve ser usado para o planejamento mestre, vá para **Planejamento mestre** \> **Configuração** \> **Parâmetros de Otimização do Planejamento**.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-140">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="4d9c8-141">Status da conexão</span><span class="sxs-lookup"><span data-stu-id="4d9c8-141">Connection status</span></span>

<span data-ttu-id="4d9c8-142">O status de conexão indica o status atual da conexão entre o Supply Chain Management e o serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-142">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="4d9c8-143">A tabela a seguir mostra os valores possíveis.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-143">The following table shows the possible values.</span></span>

| <span data-ttu-id="4d9c8-144">Status da conexão</span><span class="sxs-lookup"><span data-stu-id="4d9c8-144">Connection status</span></span> | <span data-ttu-id="4d9c8-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d9c8-145">Description</span></span> | <span data-ttu-id="4d9c8-146">A Otimização de Planejamento pode ser usada?</span><span class="sxs-lookup"><span data-stu-id="4d9c8-146">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="4d9c8-147">Conectado</span><span class="sxs-lookup"><span data-stu-id="4d9c8-147">Connected</span></span> | <span data-ttu-id="4d9c8-148">Uma conexão foi estabelecida entre o serviço Otimização de Planejamento e o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-148">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="4d9c8-149">Sim</span><span class="sxs-lookup"><span data-stu-id="4d9c8-149">Yes</span></span> |
| <span data-ttu-id="4d9c8-150">Habilitando conexão</span><span class="sxs-lookup"><span data-stu-id="4d9c8-150">Enabling connection</span></span> | <span data-ttu-id="4d9c8-151">Uma solicitação para ativar a conexão ao serviço Otimização de Planejamento está em andamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-151">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="4d9c8-152">Não</span><span class="sxs-lookup"><span data-stu-id="4d9c8-152">No</span></span> |
| <span data-ttu-id="4d9c8-153">Desconectado</span><span class="sxs-lookup"><span data-stu-id="4d9c8-153">Disconnected</span></span> | <span data-ttu-id="4d9c8-154">Não há nenhuma conexão com o serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-154">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="4d9c8-155">A conexão pode ser ativada do LCS, como descrito anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-155">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="4d9c8-156">Não</span><span class="sxs-lookup"><span data-stu-id="4d9c8-156">No</span></span> |
| <span data-ttu-id="4d9c8-157">Desabilitando a conexão</span><span class="sxs-lookup"><span data-stu-id="4d9c8-157">Disabling connection</span></span> | <span data-ttu-id="4d9c8-158">Uma solicitação para desativar a conexão ao serviço Otimização de Planejamento está em andamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-158">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="4d9c8-159">Não</span><span class="sxs-lookup"><span data-stu-id="4d9c8-159">No</span></span> |
| <span data-ttu-id="4d9c8-160">Obtendo status</span><span class="sxs-lookup"><span data-stu-id="4d9c8-160">Getting status</span></span> | <span data-ttu-id="4d9c8-161">O sistema está aguardando informações de status do serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-161">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="4d9c8-162">Não</span><span class="sxs-lookup"><span data-stu-id="4d9c8-162">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="4d9c8-163">A opção Usar Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-163">The Use Planning Optimization option</span></span>

<span data-ttu-id="4d9c8-164">A configuração da opção **Usar Otimização de Planejamento** determina qual mecanismo de planejamento é usado para o planejamento mestre:</span><span class="sxs-lookup"><span data-stu-id="4d9c8-164">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="4d9c8-165">**Sim** – a Otimização de Planejamento é usada para o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-165">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="4d9c8-166">**Não** – o mecanismo de planejamento interno do Supply Chain Management é usado para o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-166">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="4d9c8-167">Se os trabalhos em lotes de planejamento existentes criados para o mecanismo de planejamento interno do Supply Chain Management forem disparados quando a opção **Usar Otimização de Planejamento** estiver definida como **Sim**, esses trabalhos falharão.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-167">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="4d9c8-168">Integração com a configuração</span><span class="sxs-lookup"><span data-stu-id="4d9c8-168">Integration with the setup</span></span>

<span data-ttu-id="4d9c8-169">Se a versão prévia da Otimização de Planejamento estiver ativada, o planejamento mestre será feito usando o Suplemento Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-169">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="4d9c8-170">Neste caso, os resultados do planejamento mestre e os recursos são afetados.</span><span class="sxs-lookup"><span data-stu-id="4d9c8-170">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4d9c8-171">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4d9c8-171">Additional resources</span></span>

[<span data-ttu-id="4d9c8-172">Termos e condições para a versão prévia</span><span class="sxs-lookup"><span data-stu-id="4d9c8-172">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="4d9c8-173">Visão geral de Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-173">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="4d9c8-174">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-174">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="4d9c8-175">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-175">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="4d9c8-176">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="4d9c8-176">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="4d9c8-177">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="4d9c8-177">Cancel a planning job</span></span>](cancel-planning-job.md)
