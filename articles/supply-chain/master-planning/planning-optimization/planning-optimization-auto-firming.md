---
title: Confirmação automática com Otimização de Planejamento
description: Este tópico explica como usar a confirmação automática com a Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 11/05/2019
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
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 81c26b8a99f86d663d91ac4f549987262c0541ad
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323522"
---
# <a name="auto-firming-with-planning-optimization"></a><span data-ttu-id="55697-103">Confirmação automática com Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="55697-103">Auto-firming with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="55697-104">A confirmação automática permite que você confirme (ou seja, libere) as ordens planejadas como parte do processo de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="55697-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="55697-105">Quando as ordens planejadas forem confirmadas, serão transformadas em ordens de compra, ordens de transferência ou ordens de produção reais.</span><span class="sxs-lookup"><span data-stu-id="55697-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="55697-106">Quando a Otimização de Planejamento for usada, as ordens planejadas serão confirmadas durante a execução de um planejamento mestre quando a data da ordem (ou seja, a data inicial) estiver dentro do limite de tempo para a confirmação.</span><span class="sxs-lookup"><span data-stu-id="55697-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="55697-107">A confirmação automática de uma ordem de compra planejada só poderá ocorrer se o item estiver associado a um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="55697-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>

## <a name="turn-on-auto-firming"></a><span data-ttu-id="55697-108">Ativar a confirmação automática</span><span class="sxs-lookup"><span data-stu-id="55697-108">Turn on auto-firming</span></span>

<span data-ttu-id="55697-109">Para ativar a confirmação automática, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="55697-109">To turn on auto-firming, follow these steps.</span></span>

1. <span data-ttu-id="55697-110">No espaço de trabalho **Gerenciamento de recursos**, na guia **Novo**, selecione **Confirmação automática para Otimização de Planejamento** na lista.</span><span class="sxs-lookup"><span data-stu-id="55697-110">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="55697-111">Se o recurso não aparecer na guia **Novo** , examine as guias **Não habilitado** e **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="55697-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="55697-112">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="55697-112">Select **Enable now**.</span></span> <span data-ttu-id="55697-113">Como alternativa, selecione **Agenda** e selecione a hora em que você deseja que o recurso seja ativado.</span><span class="sxs-lookup"><span data-stu-id="55697-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="55697-114">Configure o limite de tempo de confirmação</span><span class="sxs-lookup"><span data-stu-id="55697-114">Set up the firming time fence</span></span>

<span data-ttu-id="55697-115">O limite de tempo de confirmação é calculado a partir da data de execução do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="55697-115">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="55697-116">Ele é definido pelo número de dias inserido.</span><span class="sxs-lookup"><span data-stu-id="55697-116">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="55697-117">Você pode controlar o limite de tempo de confirmação das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="55697-117">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="55697-118">Para definir o limite de tempo de confirmação padrão para um grupo de cobertura, vá para **Planejamento mestre** \> **Configuração** \> **Cobertura** \> **Grupos de cobertura** e selecione um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="55697-118">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="55697-119">Em seguida, na Guia Rápida **Outro**, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.</span><span class="sxs-lookup"><span data-stu-id="55697-119">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="55697-120">Para substituir o limite de tempo de confirmação definido para o grupo de cobertura para um item específico, vá para **Gerenciamento de informações do produto** \> **Produtos liberados** e, no painel de ações, selecione **Plano** e **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="55697-120">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the action pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="55697-121">Em seguida, na guia **Geral**, selecione **Limite de tempo de substituição** e, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.</span><span class="sxs-lookup"><span data-stu-id="55697-121">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="55697-122">Para substituir o limite de tempo de confirmação definido para o grupo de cobertura e a cobertura de item para um plano mestre específico, acesse **Planejamento mestre** \> **Configuração** \> **Planos mestres** e selecione um Plano mestre.</span><span class="sxs-lookup"><span data-stu-id="55697-122">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="55697-123">Em seguida, na Guia Rápida **Limite de tempo em dias**, defina **Congelar** como **Sim** e insira o número de dias.</span><span class="sxs-lookup"><span data-stu-id="55697-123">Then, on the **Time fence in days** FastTab, set **Freeze** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="55697-124">Se a confirmação automática estiver ativada para uma execução de planejamento mestre que use a Otimização de Planejamento, o processo de confirmação automática será concluído de acordo com a configuração de confirmação automática.</span><span class="sxs-lookup"><span data-stu-id="55697-124">If auto-firming is turned on for a master planning run that uses Planning Optimization, the auto-firming process is done according to the auto-firming setup.</span></span> <span data-ttu-id="55697-125">Se a confirmação automática não estiver ativada, ou se o planejamento tiver sido iniciado da página **Requisitos líquidos**, o processo de confirmação automática será ignorado.</span><span class="sxs-lookup"><span data-stu-id="55697-125">If auto-firming isn't turned on, or if planning is started from the **Net requirements** page, the auto-firming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="55697-126">Otimização de Planejamento versus o mecanismo de planejamento interno do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="55697-126">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="55697-127">A Otimização de Planejamento e o mecanismo de planejamento criado no Microsoft Dynamics 365 Supply Chain Management podem ser usados para ordens planejadas de confirmação automática.</span><span class="sxs-lookup"><span data-stu-id="55697-127">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to auto-firm planned orders.</span></span> <span data-ttu-id="55697-128">No entanto, há alguns diferenças importantes.</span><span class="sxs-lookup"><span data-stu-id="55697-128">However, there are some important differences.</span></span> <span data-ttu-id="55697-129">Por exemplo, embora a Otimização de Planejamento use a data da ordem (ou seja, a data inicial) para determinar quais ordens planejadas deverá confirmar, o mecanismo de planejamento interno do Supply Chain Management usa a data de requisição (ou seja, a data de conclusão).</span><span class="sxs-lookup"><span data-stu-id="55697-129">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="55697-130">Aqui está um resumo das diferenças.</span><span class="sxs-lookup"><span data-stu-id="55697-130">Here is a summary of the differences.</span></span>

<span data-ttu-id="55697-131">**Otimização do Planejamento**</span><span class="sxs-lookup"><span data-stu-id="55697-131">**Planning Optimization**</span></span>

- <span data-ttu-id="55697-132">A confirmação automática se baseia na data da ordem (data inicial).</span><span class="sxs-lookup"><span data-stu-id="55697-132">Auto-firming is based on the order date (start date).</span></span>
- <span data-ttu-id="55697-133">Como a data da ordem (data inicial) dispara a confirmação, você não precisa considerar o prazo de entrega como parte do limite de tempo de confirmação.</span><span class="sxs-lookup"><span data-stu-id="55697-133">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="55697-134">Se você quiser confirmar todas as ordens que devam começar durante a semana atual, o limite de tempo de confirmação deverá ser de uma semana.</span><span class="sxs-lookup"><span data-stu-id="55697-134">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="55697-135">**Mecanismo de planejamento interno do Supply Chain Management**</span><span class="sxs-lookup"><span data-stu-id="55697-135">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="55697-136">A confirmação automática se baseia na data de requisição (data final).</span><span class="sxs-lookup"><span data-stu-id="55697-136">Auto-firming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="55697-137">Para ajudar a garantir que as ordens sejam confirmadas no prazo, o tempo limite de confirmação deverá ser superior ao prazo de entrega.</span><span class="sxs-lookup"><span data-stu-id="55697-137">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="55697-138">Se você quiser confirmar todas as ordens que devam começar durante a semana atual, o limite de tempo de confirmação deverá ser o prazo de entrega mais uma semana.</span><span class="sxs-lookup"><span data-stu-id="55697-138">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>
