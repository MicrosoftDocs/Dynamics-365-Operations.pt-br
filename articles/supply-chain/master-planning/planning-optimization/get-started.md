---
title: Introdução à Otimização de Planejamento
description: Este tópico explica como começar a usar a funcionalidade Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 05/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
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
ms.openlocfilehash: ce1bbb18e9a448e84d001a4195421d2b0e4af5be
ms.sourcegitcommit: c0d37fdd70f3dec4605fdee6f981f84a49be9b9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "3339869"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="83404-103">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="83404-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="83404-104">No momento, a funcionalidade Otimização de Planejamento não dá suporte a todos os recursos disponíveis no mecanismo de planejamento do Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83404-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="83404-105">Portanto, é importante que você avalie se o conjunto de recursos disponível no momento na Otimização de Planejamento atenderá aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="83404-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="83404-106">Por padrão, a funcionalidade Otimização de Planejamento não está ativada no Dynamics Lifecycle Services (LCS) por padrão.</span><span class="sxs-lookup"><span data-stu-id="83404-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="83404-107">Portanto, você tem uma oportunidade de fazer sua avaliação antes de ativá-la.</span><span class="sxs-lookup"><span data-stu-id="83404-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="83404-108">Eventualmente, a Otimização de Planejamento substituirá o mecanismo de planejamento interno do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83404-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="83404-109">Antes de ativar a Otimização de Planejamento, recomendamos enfaticamente que você avalie os resultados da análise de ajuste da Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="83404-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="83404-110">Para obter mais informações, consulte [Introdução à análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="83404-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="83404-111">Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="83404-111">Availability</span></span>
<span data-ttu-id="83404-112">A otimização de planejamento está disponível atualmente nos seguintes ambientes do Azure: Estados Unidos, Canadá, Europa, Reino Unido e Austrália.</span><span class="sxs-lookup"><span data-stu-id="83404-112">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="83404-113">Se você tentar instalar o suplemento de outra região geográfica, o LCS mostrará uma mensagem informando que esse ambiente não é suportado.</span><span class="sxs-lookup"><span data-stu-id="83404-113">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="83404-114">Observe que a otimização de planejamento não oferece suporte a implantações locais do Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83404-114">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="83404-115">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="83404-115">Licensing</span></span>

<span data-ttu-id="83404-116">Se você puder executar o planejamento mestre usando a licença atual, não terá de comprar uma licença adicional para começar a usar a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="83404-116">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="83404-117">Instalar o suplemento</span><span class="sxs-lookup"><span data-stu-id="83404-117">Install the add-in</span></span>

<span data-ttu-id="83404-118">Para usar a Otimização de Planejamento, instale o Suplemento Otimização de Planejamento para o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83404-118">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="83404-119">Você pode acessar o suplemento do seu projeto do LCS e ativar a funcionalidade Otimização de Planejamento da interface do usuário (IU) do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83404-119">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="83404-120">A necessidade de Otimização do Planejamento é um ambiente de alta disponibilidade habilitado para LCS, camada 2 ou superior (não um ambiente OneBox), com o Dynamics 365 Supply Chain Management versão 10.0.7 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="83404-120">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="83404-121">Se você tentar instalar o suplemento em um ambiente do OneBox, a instalação não será concluída e será necessário cancelar a instalação.</span><span class="sxs-lookup"><span data-stu-id="83404-121">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="83404-122">Entre no LCS e abra o ambiente desejado.</span><span class="sxs-lookup"><span data-stu-id="83404-122">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="83404-123">Vá para **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="83404-123">Go to **Full details**.</span></span>
1. <span data-ttu-id="83404-124">Role para baixo até a FastTab **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="83404-124">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="83404-125">Selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="83404-125">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="83404-126">Selecione **Otimização de Planejamento**.</span><span class="sxs-lookup"><span data-stu-id="83404-126">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="83404-127">Acompanhe o guia de instalação e concorde com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="83404-127">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="83404-128">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="83404-128">Select **Install**.</span></span>
1. <span data-ttu-id="83404-129">Na FastTab **Suplementos de ambiente**, você deverá ver que a Otimização do Planejamento está instalando.</span><span class="sxs-lookup"><span data-stu-id="83404-129">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="83404-130">Após alguns minutos, **Instalando** deve mudar para **Instalado** (talvez você precise atualizar a página).</span><span class="sxs-lookup"><span data-stu-id="83404-130">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="83404-131">Quando instalado, você estará pronto para ativar a Otimização do Planejamento no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83404-131">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="83404-132">Integração da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="83404-132">Planning Optimization integration</span></span>

<span data-ttu-id="83404-133">Para configurar se o Suplemento Otimização do Planejamento deve ser usado para o planejamento mestre, vá para **Planejamento mestre** \> **Configuração** \> **Parâmetros de Otimização do Planejamento**.</span><span class="sxs-lookup"><span data-stu-id="83404-133">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="83404-134">Status da conexão</span><span class="sxs-lookup"><span data-stu-id="83404-134">Connection status</span></span>

<span data-ttu-id="83404-135">O status de conexão indica o status atual da conexão entre o Supply Chain Management e o serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="83404-135">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="83404-136">A tabela a seguir mostra os valores possíveis.</span><span class="sxs-lookup"><span data-stu-id="83404-136">The following table shows the possible values.</span></span>

| <span data-ttu-id="83404-137">Status da conexão</span><span class="sxs-lookup"><span data-stu-id="83404-137">Connection status</span></span> | <span data-ttu-id="83404-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="83404-138">Description</span></span> | <span data-ttu-id="83404-139">A Otimização de Planejamento pode ser usada?</span><span class="sxs-lookup"><span data-stu-id="83404-139">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="83404-140">Conectado</span><span class="sxs-lookup"><span data-stu-id="83404-140">Connected</span></span> | <span data-ttu-id="83404-141">Uma conexão foi estabelecida entre o serviço Otimização de Planejamento e o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83404-141">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="83404-142">Sim</span><span class="sxs-lookup"><span data-stu-id="83404-142">Yes</span></span> |
| <span data-ttu-id="83404-143">Habilitando conexão</span><span class="sxs-lookup"><span data-stu-id="83404-143">Enabling connection</span></span> | <span data-ttu-id="83404-144">Uma solicitação para ativar a conexão ao serviço Otimização de Planejamento está em andamento.</span><span class="sxs-lookup"><span data-stu-id="83404-144">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="83404-145">Não</span><span class="sxs-lookup"><span data-stu-id="83404-145">No</span></span> |
| <span data-ttu-id="83404-146">Desconectado</span><span class="sxs-lookup"><span data-stu-id="83404-146">Disconnected</span></span> | <span data-ttu-id="83404-147">Não há nenhuma conexão com o serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="83404-147">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="83404-148">A conexão pode ser ativada do LCS, como descrito anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="83404-148">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="83404-149">Não</span><span class="sxs-lookup"><span data-stu-id="83404-149">No</span></span> |
| <span data-ttu-id="83404-150">Desabilitando a conexão</span><span class="sxs-lookup"><span data-stu-id="83404-150">Disabling connection</span></span> | <span data-ttu-id="83404-151">Uma solicitação para desativar a conexão ao serviço Otimização de Planejamento está em andamento.</span><span class="sxs-lookup"><span data-stu-id="83404-151">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="83404-152">Não</span><span class="sxs-lookup"><span data-stu-id="83404-152">No</span></span> |
| <span data-ttu-id="83404-153">Obtendo status</span><span class="sxs-lookup"><span data-stu-id="83404-153">Getting status</span></span> | <span data-ttu-id="83404-154">O sistema está aguardando informações de status do serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="83404-154">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="83404-155">Não</span><span class="sxs-lookup"><span data-stu-id="83404-155">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="83404-156">A opção Usar Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="83404-156">The Use Planning Optimization option</span></span>

<span data-ttu-id="83404-157">A configuração da opção **Usar Otimização de Planejamento** determina qual mecanismo de planejamento é usado para o planejamento mestre:</span><span class="sxs-lookup"><span data-stu-id="83404-157">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="83404-158">**Sim** – a Otimização de Planejamento é usada para o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="83404-158">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="83404-159">**Não** – o mecanismo de planejamento interno do Supply Chain Management é usado para o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="83404-159">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="83404-160">Se os trabalhos em lotes de planejamento existentes criados para o mecanismo de planejamento interno do Supply Chain Management forem disparados quando a opção **Usar Otimização de Planejamento** estiver definida como **Sim**, esses trabalhos falharão.</span><span class="sxs-lookup"><span data-stu-id="83404-160">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="83404-161">Integração com a configuração</span><span class="sxs-lookup"><span data-stu-id="83404-161">Integration with the setup</span></span>

<span data-ttu-id="83404-162">Se a versão prévia da Otimização de Planejamento estiver ativada, o planejamento mestre será feito usando o Suplemento Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="83404-162">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="83404-163">Neste caso, os resultados do planejamento mestre e os recursos são afetados.</span><span class="sxs-lookup"><span data-stu-id="83404-163">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83404-164">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="83404-164">Additional resources</span></span>

[<span data-ttu-id="83404-165">Termos e condições para a versão prévia</span><span class="sxs-lookup"><span data-stu-id="83404-165">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="83404-166">Visão geral de Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="83404-166">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="83404-167">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="83404-167">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="83404-168">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="83404-168">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="83404-169">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="83404-169">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="83404-170">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="83404-170">Cancel a planning job</span></span>](cancel-planning-job.md)
