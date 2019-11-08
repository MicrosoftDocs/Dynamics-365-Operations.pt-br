---
title: Atualização manual de contadores de ativo
description: Este tópico descreve atualização manual de contadores de ativo no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3072ab204b53b16988d2973b28a697041cb84c27
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626123"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="56a29-103">Atualização manual de contadores de ativo</span><span class="sxs-lookup"><span data-stu-id="56a29-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="56a29-104">Os contadores são usados para criar registros em um ativo, como registros sobre o número de horas que o ativo esteve em operação ou a quantidade que foi produzida.</span><span class="sxs-lookup"><span data-stu-id="56a29-104">Counters are used to create registrations on an asset, such as registrations about the number of hours that the asset has been in operation or the quantity that has been produced.</span></span>

<span data-ttu-id="56a29-105">O tipo selecionado para um contador deve ser definido para herdar valores do contador.</span><span class="sxs-lookup"><span data-stu-id="56a29-105">The counter type that is selected for a counter might be set to inherit counter values.</span></span> <span data-ttu-id="56a29-106">Ou seja, a opção **Herdar valores do contador de ativos** é definida como **Sim** na Guia Rápida **Geral** da página **Contadores** (**Gerenciamento de ativos** > **Configurar** > **Tipos de ativo** > **Contadores**).</span><span class="sxs-lookup"><span data-stu-id="56a29-106">In other words, the **Inherit asset counter values** option is set to **Yes** on the **General** FastTab of the **Counters** page (**Asset management** > **Setup** > **Asset types** > **Counters**).</span></span> <span data-ttu-id="56a29-107">Nesse caso, ao criar uma nova linha de contador desse tipo, cada ativo filho que usar o mesmo tipo de contador será atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="56a29-107">In this case, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="56a29-108">Na página **Todos os ativos**, você pode criar os registros de contador de horas ou quantidade em um ativo com base nas leituras do ativo.</span><span class="sxs-lookup"><span data-stu-id="56a29-108">On the **All assets** page, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="56a29-109">Selecione **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="56a29-109">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="56a29-110">Selecione o ativo e, depois, no Painel de Ação, na guia **Ativo** , no grupo **Preventivo** , selecione **Contadores**.</span><span class="sxs-lookup"><span data-stu-id="56a29-110">Select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span> <span data-ttu-id="56a29-111">A página **Contadores de ativos** exibe uma lista de todos os registros do contador anteriores que foram feitos no ativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="56a29-111">The **Asset counters** page shows a list of all previous counter registrations that have been made on the selected asset.</span></span>

3. <span data-ttu-id="56a29-112">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="56a29-112">Select **New** to create a registration.</span></span> <span data-ttu-id="56a29-113">A ID de ativo é inserida automaticamente no campo **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="56a29-113">The asset ID is automatically entered in the **Asset** field.</span></span>

4. <span data-ttu-id="56a29-114">No campo **Contador**, selecione o contador relevante.</span><span class="sxs-lookup"><span data-stu-id="56a29-114">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="56a29-115">Somente os contadores relacionados ao tipo de ativo selecionado no ativo estão disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="56a29-115">Only counters that are related to the asset type selected on the asset are available for selection.</span></span> <span data-ttu-id="56a29-116">A unidade relacionada é inserida automaticamente no campo **Unidade**.</span><span class="sxs-lookup"><span data-stu-id="56a29-116">The related unit is automatically entered in the **Unit** field.</span></span>

5. <span data-ttu-id="56a29-117">No campo **Registrado**, selecione a data e a hora para o registro do contador.</span><span class="sxs-lookup"><span data-stu-id="56a29-117">In the **Registered** field, select the date and time for the counter registration.</span></span>

6. <span data-ttu-id="56a29-118">No campo **Valor**, insira o número desde o último registro do contador.</span><span class="sxs-lookup"><span data-stu-id="56a29-118">In the **Value** field, enter the number since the last counter registration.</span></span> <span data-ttu-id="56a29-119">Alternativamente, no campo **Valor agregado**, insira o número de contagem total.</span><span class="sxs-lookup"><span data-stu-id="56a29-119">Alternatively, in the **Aggregated value** field, enter the total count number.</span></span>

<span data-ttu-id="56a29-120">Observe os seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="56a29-120">Note the following points:</span></span>

- <span data-ttu-id="56a29-121">Se instalar fisicamente um novo contador em um ativo, você deverá registrar a alteração no ativo na página **Contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="56a29-121">If you physically install a new counter on an asset, you must register the change on the asset on the **Asset counters** page.</span></span> <span data-ttu-id="56a29-122">Em seguida, você deve criar duas linhas de registro com carimbos de data/hora idênticos.</span><span class="sxs-lookup"><span data-stu-id="56a29-122">Next, you must create two registration lines that have identical timestamps.</span></span> <span data-ttu-id="56a29-123">A primeira linha deve ser para o contador que está sendo substituído.</span><span class="sxs-lookup"><span data-stu-id="56a29-123">The first line must be for the counter that you're replacing.</span></span> <span data-ttu-id="56a29-124">Na linha relacionada ao novo contador, marque a caixa de seleção **Redefinir contador**.</span><span class="sxs-lookup"><span data-stu-id="56a29-124">On the line that is related to the new counter, select the **Counter reset** check box.</span></span> <span data-ttu-id="56a29-125">No campo **Totais**, o número de contagem total é a soma dos totais do contador de todos os valores registrados nesse tipo de contador.</span><span class="sxs-lookup"><span data-stu-id="56a29-125">In the **Totals** field, the total count number is the sum of the counter totals of all registered values on that counter type.</span></span>

- <span data-ttu-id="56a29-126">Se a caixa de seleção **Redefinir contador** for marcada em um ativo que usa um plano de manutenção com um tipo de intervalo "Uma vez de..." ou "Uma vez atingido...", o contador ainda ficará ativo na nova linha do contador, pois você cria uma linha de contador separada e inicia com um novo contador.</span><span class="sxs-lookup"><span data-stu-id="56a29-126">If the **Counter reset** check box is selected on an asset using a maintenance plan that has a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line, because you create a separate counter line and start over with a new counter.</span></span>

<span data-ttu-id="56a29-127">A ilustração a seguir mostra um exemplo da página **Contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="56a29-127">The illustration below shows an example of the **Asset counters** page.</span></span>

![Figura 1](media/11-work-orders.png)

<span data-ttu-id="56a29-129">Na página **Contadores de ativos** (**Gerenciamento de ativos** > **Consultas** > **Ativos** > **Contadores de ativos**), você pode criar registros de contador em vários ativos ao mesmo tempo, conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="56a29-129">On the **Asset counters** page (**Asset management** > **Inquiries** > **Assets** > **Asset counters**), you can make counter registrations on several assets at the same time, as you require.</span></span>

>[!NOTE]
><span data-ttu-id="56a29-130">Você pode configurar um intervalo para definir os desvios em registros de contador manuais.</span><span class="sxs-lookup"><span data-stu-id="56a29-130">You can set up a range to define deviations in manual counter registrations.</span></span> <span data-ttu-id="56a29-131">Também é possível especificar o tipo de mensagem exibida se os registros estiverem fora do intervalo definido.</span><span class="sxs-lookup"><span data-stu-id="56a29-131">You can also specify the type of message that is shown if registrations are outside the defined range.</span></span> <span data-ttu-id="56a29-132">Para obter mais informações sobre como configurar contadores, consulte [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="56a29-132">For more information about how to set up counters, see [Counters](../setup-for-objects/counters.md).</span></span>

