---
title: Atualização manual de contadores de ativo
description: Este tópico descreve atualização manual de contadores de ativo no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875506"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="7351a-103">Atualização manual de contadores de ativo</span><span class="sxs-lookup"><span data-stu-id="7351a-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="7351a-104">Contadores são usados para criar registros em um ativo relacionado, por exemplo, o número de horas na operação, ou número de quantidades geradas.</span><span class="sxs-lookup"><span data-stu-id="7351a-104">Counters are used to create registrations on an asset regarding, for example, number of hours in operation, or the number of quantities produced.</span></span>

<span data-ttu-id="7351a-105">Se o tipo de contador selecionado para um contador for definido para herdar valores do contador (**Gerenciamento de ativos** > **Configuração** > **Tipos de ativos** > **Contadores** > **Geral** Guia Rápida > **Herdar valores do contador de ativos** botão de alternância definido como "Sim"), então, quando você criar uma nova linha do contador desse tipo, cada ativo filho que usa o mesmo tipo de contador é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7351a-105">If the counter type selected for a counter is set to inherit counter values (**Asset management** > **Setup** > **Asset types** > **Counters** > **General** FastTab > **Inherit asset counter values** toggle button set to "Yes"), then, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="7351a-106">Em **Todos os ativos**, você cria horas ou registros do contador da quantidade em um ativo com base nas leituras do ativo.</span><span class="sxs-lookup"><span data-stu-id="7351a-106">In **All assets**, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="7351a-107">Clique em **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="7351a-107">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="7351a-108">Selecione o ativo da lista e clique em **Contadores**.</span><span class="sxs-lookup"><span data-stu-id="7351a-108">Select the asset in the list, and click **Counters**.</span></span> <span data-ttu-id="7351a-109">No formulário **Contadores de ativo**, você verá uma lista de todos os registros do contador anteriores no ativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="7351a-109">In the **Asset counters** form, you see a list of all previous counter registrations on the selected asset.</span></span>

3. <span data-ttu-id="7351a-110">Clique em **Novo** para criar um novo registro.</span><span class="sxs-lookup"><span data-stu-id="7351a-110">Click **New** to create a new registration.</span></span> <span data-ttu-id="7351a-111">O ID do ativo é inserido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7351a-111">The asset ID is automatically inserted.</span></span>

4. <span data-ttu-id="7351a-112">No campo **Contador**, selecione o contador relevante.</span><span class="sxs-lookup"><span data-stu-id="7351a-112">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="7351a-113">Somente estão disponíveis contadores relacionados ao tipo de ativo selecionado no ativo.</span><span class="sxs-lookup"><span data-stu-id="7351a-113">Only counters related to the asset type selected on the asset are available.</span></span> <span data-ttu-id="7351a-114">A unidade relacionada é inserida automaticamente no campo **Unidade**.</span><span class="sxs-lookup"><span data-stu-id="7351a-114">The related unit is automatically inserted in the **Unit** field.</span></span>

5. <span data-ttu-id="7351a-115">Selecione a data e a hora do registro do contador.</span><span class="sxs-lookup"><span data-stu-id="7351a-115">Select date and time for the counter registration.</span></span>

6. <span data-ttu-id="7351a-116">No campo **Valor**, insira o número desde o último registro do contador ou no campo **Valor agregado**, insira o número total de contagem.</span><span class="sxs-lookup"><span data-stu-id="7351a-116">In the **Value** field, insert the number since the last counter registration, or, in the **Aggregated value** field, insert the total count number.</span></span>

- <span data-ttu-id="7351a-117">Se você instalar fisicamente um novo contador em um ativo, você precisará registrar a alteração no ativo em **Contadores de ativo**.</span><span class="sxs-lookup"><span data-stu-id="7351a-117">If you physically install a new counter on an asset, you need to register the change on the asset in **Asset counters**.</span></span> <span data-ttu-id="7351a-118">Em seguida, crie duas linhas de registro com carimbos de data/hora idênticos, e na linha referente ao novo contador, marque a caixa de seleção **Redefinição do contador**.</span><span class="sxs-lookup"><span data-stu-id="7351a-118">Next, you must create two registration lines with identical timestamps, and on the line regarding the new counter, you select the **Counter reset** check box.</span></span> <span data-ttu-id="7351a-119">Ao criar as duas linhas de registro, a primeira linha deve ser para o contador que você está substituindo.</span><span class="sxs-lookup"><span data-stu-id="7351a-119">When you create the two registration lines, the first line must be for the counter that you are replacing.</span></span> <span data-ttu-id="7351a-120">No campo **Totais**, o número de contagem total é a soma total do contador de todos os valores registrados nesse tipo de contador.</span><span class="sxs-lookup"><span data-stu-id="7351a-120">In the **Totals** field, the total count number is the sum of the counter total of all registered values on that counter type.</span></span>  
- <span data-ttu-id="7351a-121">Se a caixa de seleção **Redefinir contador** for selecionada em um ativo que usa um plano de manutenção com um tipo de intervalo "Uma vez..." ou "Uma vez atingido...", o contador ainda ficará ativo na nova linha do contador porque você cria uma linha do contador separada e inicia um novo contador.</span><span class="sxs-lookup"><span data-stu-id="7351a-121">If the **Counter reset** check box is selected on an asset using a maintenance plan with a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line because you create a separate counter line and start over with a new counter.</span></span>

![Figura 1](media/11-work-orders.png)


<span data-ttu-id="7351a-123">Se precisar efetuar registros do contador em vários ativos, isso poderá ser feito em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="7351a-123">If you need to make counter registrations on several assets, that can be done in **Asset management** > **Inquiries** > **Assets** > **Asset counters**.</span></span>

>[!NOTE]
><span data-ttu-id="7351a-124">Você pode configurar um intervalo para definir desvios em registros de contadores manuais, e o tipo de mensagem a ser exibido se os registros estiverem fora do intervalo definido.</span><span class="sxs-lookup"><span data-stu-id="7351a-124">You can set up a range to define deviations in manual counter registrations, and the type of message that should be displayed if registrations are outside the defined range.</span></span> <span data-ttu-id="7351a-125">Consulte o tópico [Contadores](../setup-for-objects/counters.md) referente à configuração dos contadores.</span><span class="sxs-lookup"><span data-stu-id="7351a-125">Refer to the [Counters](../setup-for-objects/counters.md) topic regarding setup of counters.</span></span>
