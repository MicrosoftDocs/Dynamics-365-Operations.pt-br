---
title: Confirmação automática com a Otimização de Planejamento
description: Este tópico explica como usar a confirmação automática com a Otimização de Planejamento.
author: ChristianRytt
ms.date: 11/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-30
ms.dyn365.ops.version: AX 10.0.7
ms.openlocfilehash: 3542e343de29c9fd9d19ed99cab4b4eebacd2899
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812994"
---
# <a name="autofirming-with-planning-optimization"></a><span data-ttu-id="53c92-103">Confirmação automática com a Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="53c92-103">Autofirming with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53c92-104">A confirmação automática permite que você confirme (ou seja, libere) as ordens planejadas como parte do processo de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="53c92-104">Automatic firming lets you firm (that is, release) planned orders as part of the master planning process.</span></span> <span data-ttu-id="53c92-105">Quando as ordens planejadas forem confirmadas, serão transformadas em ordens de compra, ordens de transferência ou ordens de produção reais.</span><span class="sxs-lookup"><span data-stu-id="53c92-105">When planned orders are firmed, they are transformed into actual purchase orders, transfer orders, or production orders.</span></span> <span data-ttu-id="53c92-106">Quando a Otimização de Planejamento for usada, as ordens planejadas serão confirmadas durante a execução de um planejamento mestre quando a data da ordem (ou seja, a data inicial) estiver dentro do limite de tempo para a confirmação.</span><span class="sxs-lookup"><span data-stu-id="53c92-106">When Planning Optimization is used, planned orders are firmed during a master planning run when the order date (that is, the start date) is within the time fence for firming.</span></span>

> [!NOTE]
> <span data-ttu-id="53c92-107">A confirmação automática de uma ordem de compra planejada só poderá ocorrer se o item estiver associado a um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="53c92-107">Auto-firming of a planned purchase order can occur only if the item is associated with a vendor.</span></span>
> 
> <span data-ttu-id="53c92-108">As ordens derivadas confirmadas (ordens de compra do subcontratado) apresentarão um status *Em revisão* quando o controle de alterações do caso estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="53c92-108">Firmed derived orders (subcontract purchase orders) will show a status of *In-review* when case change tracking is enabled.</span></span>

## <a name="turn-on-autofirming"></a><span data-ttu-id="53c92-109">Ativar a confirmação automática</span><span class="sxs-lookup"><span data-stu-id="53c92-109">Turn on autofirming</span></span>

<span data-ttu-id="53c92-110">Para ativar a confirmação automática, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="53c92-110">To turn on autofirming, follow these steps.</span></span>

1. <span data-ttu-id="53c92-111">No espaço de trabalho **Gerenciamento de recursos**, na guia **Novo**, selecione **Confirmação automática para Otimização de Planejamento** na lista.</span><span class="sxs-lookup"><span data-stu-id="53c92-111">In the **Feature management** workspace, on the **New** tab, select **Auto-firming for Planning Optimization** in the list.</span></span> <span data-ttu-id="53c92-112">Se o recurso não aparecer na guia **Novo** , examine as guias **Não habilitado** e **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="53c92-112">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="53c92-113">Selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="53c92-113">Select **Enable now**.</span></span> <span data-ttu-id="53c92-114">Como alternativa, selecione **Agenda** e selecione a hora em que você deseja que o recurso seja ativado.</span><span class="sxs-lookup"><span data-stu-id="53c92-114">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

## <a name="set-up-the-firming-time-fence"></a><span data-ttu-id="53c92-115">Configure o limite de tempo de confirmação</span><span class="sxs-lookup"><span data-stu-id="53c92-115">Set up the firming time fence</span></span>

<span data-ttu-id="53c92-116">O limite de tempo de confirmação é calculado a partir da data de execução do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="53c92-116">The firming time fence is calculated forward from the master planning run date.</span></span> <span data-ttu-id="53c92-117">Ele é definido pelo número de dias inserido.</span><span class="sxs-lookup"><span data-stu-id="53c92-117">It's defined by the number of days that you enter.</span></span> <span data-ttu-id="53c92-118">Você pode controlar o limite de tempo de confirmação das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="53c92-118">You can control the firming time fence in the following ways:</span></span>

- <span data-ttu-id="53c92-119">Para definir o limite de tempo de confirmação padrão para um grupo de cobertura, vá para **Planejamento mestre** \> **Configuração** \> **Cobertura** \> **Grupos de cobertura** e selecione um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="53c92-119">To define the default firming time fence for a coverage group, go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**, and select a coverage group.</span></span> <span data-ttu-id="53c92-120">Em seguida, na Guia Rápida **Outro**, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.</span><span class="sxs-lookup"><span data-stu-id="53c92-120">Then, on the **Other** FastTab, in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="53c92-121">Para substituir o limite de tempo de confirmação definido para o grupo de cobertura para um item específico, vá para **Gerenciamento de informações do produto** \> **Produtos liberados** e, no Painel de Ações, selecione **Plano** e **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="53c92-121">To overwrite the firming time fence that is defined for the coverage group for a specific item, go to **Product information management** \> **Released products**, then from the Action Pane select **Plan** and then select **Item coverage**.</span></span> <span data-ttu-id="53c92-122">Em seguida, na guia **Geral**, selecione **Limite de tempo de substituição** e, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.</span><span class="sxs-lookup"><span data-stu-id="53c92-122">Then, on the **General** tab, select **Override time fence** and in the **Automatic firming time fence (days)** field, enter the number of days.</span></span>
- <span data-ttu-id="53c92-123">Para substituir o limite de tempo de confirmação definido para o grupo de cobertura e a cobertura de item para um plano mestre específico, acesse **Planejamento mestre** \> **Configuração** \> **Planos mestres** e selecione um Plano mestre.</span><span class="sxs-lookup"><span data-stu-id="53c92-123">To overwrite the firming time fence that is defined for the coverage group and item coverage for a specific master plan, go to **Master planning** \> **Setup** \> **Master plans**, and select a Master plan.</span></span> <span data-ttu-id="53c92-124">Em seguida, na FastTab **Limite de tempo em dias**, defina **Confirmação** como **Sim** e insira o número de dias.</span><span class="sxs-lookup"><span data-stu-id="53c92-124">Then, on the **Time fence in days** FastTab, set **Firming** to **Yes**, and enter the number of days.</span></span>

<span data-ttu-id="53c92-125">Se a confirmação automática estiver ativada para uma execução de planejamento mestre que use a Otimização de Planejamento, o processo de confirmação automática será concluído de acordo com sua configuração.</span><span class="sxs-lookup"><span data-stu-id="53c92-125">If autofirming is turned on for a master planning run that uses Planning Optimization, the autofirming process is done according to the autofirming setup.</span></span> <span data-ttu-id="53c92-126">Se a confirmação automática não estiver ativada ou se o planejamento tiver sido iniciado na página **Requisitos líquidos**, o processo de confirmação automática será ignorado.</span><span class="sxs-lookup"><span data-stu-id="53c92-126">If autofirming isn't turned on, or if planning is started from the **Net requirements** page, the autofirming process is skipped.</span></span>

## <a name="planning-optimization-vs-the-built-in-supply-chain-management-planning-engine"></a><span data-ttu-id="53c92-127">Otimização de Planejamento versus o mecanismo de planejamento interno do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="53c92-127">Planning Optimization vs. the built-in Supply Chain Management planning engine</span></span>

<span data-ttu-id="53c92-128">A Otimização de Planejamento e o mecanismo de planejamento interno do Microsoft Dynamics 365 Supply Chain Management podem ser usados para confirmar ordens planejadas de forma automática.</span><span class="sxs-lookup"><span data-stu-id="53c92-128">Both Planning Optimization and the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management can be used to autofirm planned orders.</span></span> <span data-ttu-id="53c92-129">No entanto, há alguns diferenças importantes.</span><span class="sxs-lookup"><span data-stu-id="53c92-129">However, there are some important differences.</span></span> <span data-ttu-id="53c92-130">Por exemplo, embora a Otimização de Planejamento use a data da ordem (ou seja, a data inicial) para determinar quais ordens planejadas deverá confirmar, o mecanismo de planejamento interno do Supply Chain Management usa a data de requisição (ou seja, a data de conclusão).</span><span class="sxs-lookup"><span data-stu-id="53c92-130">For example, whereas Planning Optimization uses the order date (that is, the start date) to determine which planned orders to firm, the built-in Supply Chain Management planning engine uses the requirement date (that is, the end date).</span></span> <span data-ttu-id="53c92-131">Aqui está um resumo das diferenças.</span><span class="sxs-lookup"><span data-stu-id="53c92-131">Here is a summary of the differences.</span></span>

<span data-ttu-id="53c92-132">**Otimização do Planejamento**</span><span class="sxs-lookup"><span data-stu-id="53c92-132">**Planning Optimization**</span></span>

- <span data-ttu-id="53c92-133">A confirmação automática se baseia na data da ordem (data de início).</span><span class="sxs-lookup"><span data-stu-id="53c92-133">Autofirming is based on the order date (start date).</span></span>
- <span data-ttu-id="53c92-134">Como a data da ordem (data inicial) dispara a confirmação, você não precisa considerar o prazo de entrega como parte do limite de tempo de confirmação.</span><span class="sxs-lookup"><span data-stu-id="53c92-134">Because the order date (start date) triggers the firming, you don't have to consider the lead time as part of the firming time fence.</span></span>
- <span data-ttu-id="53c92-135">Se você quiser confirmar todas as ordens que devam começar durante a semana atual, o limite de tempo de confirmação deverá ser de uma semana.</span><span class="sxs-lookup"><span data-stu-id="53c92-135">If you want to firm all orders that must start during the current week, the firming time fence must be one week.</span></span>

<span data-ttu-id="53c92-136">**Mecanismo de planejamento interno do Supply Chain Management**</span><span class="sxs-lookup"><span data-stu-id="53c92-136">**Built-in Supply Chain Management planning engine**</span></span>

- <span data-ttu-id="53c92-137">A confirmação automática se baseia na data de requisição (data de término).</span><span class="sxs-lookup"><span data-stu-id="53c92-137">Autofirming is based on the requirement date (end date).</span></span>
- <span data-ttu-id="53c92-138">Para ajudar a garantir que as ordens sejam confirmadas no prazo, o tempo limite de confirmação deverá ser superior ao prazo de entrega.</span><span class="sxs-lookup"><span data-stu-id="53c92-138">To help guarantee that orders are firmed in due time, the firming time fence must be longer than the lead time.</span></span>
- <span data-ttu-id="53c92-139">Se você quiser confirmar todas as ordens que devam começar durante a semana atual, o limite de tempo de confirmação deverá ser o prazo de entrega mais uma semana.</span><span class="sxs-lookup"><span data-stu-id="53c92-139">If you want to firm all orders that must start during the current week, the firming time fence must be the lead time plus one week.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
