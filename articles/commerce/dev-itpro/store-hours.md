---
title: Criar e atualizar os horários das lojas
description: Este tópico descreve como criar e atualizar os horários de funcionamento em Commerce Headquarters.
author: josaw1
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 862b032c75145594be78fb2f4e27ea5616605c4d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792920"
---
# <a name="create-and-update-store-hours"></a><span data-ttu-id="ace08-103">Criar e atualizar os horários das lojas</span><span class="sxs-lookup"><span data-stu-id="ace08-103">Create and update store hours</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="ace08-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="ace08-104">Overview</span></span>

<span data-ttu-id="ace08-105">De um único local, fornecedores podem criar, manter e gerenciar e o horário de funcionamento para diferentes lojas nas regiões.</span><span class="sxs-lookup"><span data-stu-id="ace08-105">From a single place, retailers can create, maintain, and manage the store hours for different stores across geographic regions.</span></span> <span data-ttu-id="ace08-106">O horário de funcionamento pode ser exibido em terminais do ponto de venda (POS).</span><span class="sxs-lookup"><span data-stu-id="ace08-106">The store hours can then be shown on point of sale (POS) terminals.</span></span> <span data-ttu-id="ace08-107">Assim, os caixas podem compartilhar o horário de funcionamento com clientes e ajudar melhor os clientes que estão interessados em estoque em outras lojas.</span><span class="sxs-lookup"><span data-stu-id="ace08-107">In this way, cashiers can share store hours with customers and better help shoppers who are interested in inventory in other stores.</span></span> <span data-ttu-id="ace08-108">O horário de funcionamento também pode ser impresso nos recibos, se os clientes desejarem retornar posteriormente à loja.</span><span class="sxs-lookup"><span data-stu-id="ace08-108">The store hours can also be printed on receipts, in case customers want to return to the store later.</span></span>

<span data-ttu-id="ace08-109">Vários horários de funcionamento podem ser configurados em diferentes canais.</span><span class="sxs-lookup"><span data-stu-id="ace08-109">Multiple store hours can be configured across different channels.</span></span> <span data-ttu-id="ace08-110">Esses canais incluem lojas físicas, call centers, dispositivos móveis e sites e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ace08-110">These channels include brick-and-mortar stores, call centers, mobile devices, and e-Commerce sites.</span></span>

<span data-ttu-id="ace08-111">Se um cliente tiver um ordem de retirada de uma loja diferente, o caixa poderá selecionar datas em que o recolhimento estará disponível naquela loja.</span><span class="sxs-lookup"><span data-stu-id="ace08-111">If a customer has a pickup order for a different store, the cashier can select dates when the pickup will be available in that store.</span></span> <span data-ttu-id="ace08-112">A pesquisa de loja oferecerá uma referência a datas e horário das lojas.</span><span class="sxs-lookup"><span data-stu-id="ace08-112">The store lookup will provide a reference to the dates and store times.</span></span> <span data-ttu-id="ace08-113">O caixa pode selecionar uma data e uma localização e também pode imprimir um recibo de retirada que inclua o horário de funcionamento.</span><span class="sxs-lookup"><span data-stu-id="ace08-113">The cashier can select a date and location, and can also print a pickup receipt that includes the store hours.</span></span>

<span data-ttu-id="ace08-114">Esta funcionalidade ficará disponível em versões 8.1.2 do Microsoft Dynamics 365 Retail e posterior.</span><span class="sxs-lookup"><span data-stu-id="ace08-114">This functionality is available in Microsoft Dynamics 365 Retail versions 8.1.2 and later.</span></span>

## <a name="configure-store-hours"></a><span data-ttu-id="ace08-115">Configurar horários das lojas</span><span class="sxs-lookup"><span data-stu-id="ace08-115">Configure store hours</span></span>

<span data-ttu-id="ace08-116">Siga estas etapas para configurar os horários das lojas.</span><span class="sxs-lookup"><span data-stu-id="ace08-116">Follow these steps to configure store hours.</span></span>

1. <span data-ttu-id="ace08-117">Vá para **Retail e Commerce** \> **Configuração do canal** \> **Horários das lojas**.</span><span class="sxs-lookup"><span data-stu-id="ace08-117">Go to **Retail and Commerce** \> **Channel Setup** \> **Store hours**.</span></span>
2. <span data-ttu-id="ace08-118">Selecionar **Novo** para criar um novo modelo de horários das lojas.</span><span class="sxs-lookup"><span data-stu-id="ace08-118">Select **New** to create a new store hours template.</span></span> <span data-ttu-id="ace08-119">Para usar um modelo existente, selecione o modelo no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ace08-119">To use an existing template, select the template in the left pane.</span></span>
3. <span data-ttu-id="ace08-120">Na caixa de diálogo **Adicionar intervalo**, defina o intervalo de data, o horário de funcionamento e todos os feriados necessários.</span><span class="sxs-lookup"><span data-stu-id="ace08-120">In the **Add range** dialog box, define the date range, the store hours, and any holidays that are required.</span></span>

    - <span data-ttu-id="ace08-121">Se o horário da loja não se altera, selecione **Nunca terminará** no campo **Data final**.</span><span class="sxs-lookup"><span data-stu-id="ace08-121">If store hours don't change, select **Never ends** in the **End date** field.</span></span>
    - <span data-ttu-id="ace08-122">Se o horário de funcionamento para um mês, semana, ou dia específico, defina as datas apropriadas nos campos **Data inicial** e **Data final**.</span><span class="sxs-lookup"><span data-stu-id="ace08-122">If the store hours are for a specific month, week, or day, set the appropriate dates in the **Start Date** and **End date** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ace08-123">Você pode criar vários modelos com as datas inicial e final sobrepostas.</span><span class="sxs-lookup"><span data-stu-id="ace08-123">You can create multiple templates that have overlapping start and end dates.</span></span> <span data-ttu-id="ace08-124">Portanto, você pode, por exemplo, definir o horário de funcionamento para lojas em fusos horários diferentes.</span><span class="sxs-lookup"><span data-stu-id="ace08-124">Therefore, you can, for example, define store hours for stores in different time zones.</span></span>

    <span data-ttu-id="ace08-125">![Adicionar a caixa de diálogo do intervalo](../dev-itpro/media/Storehours1.png "Adicionar a caixa de diálogo do intervalo")</span><span class="sxs-lookup"><span data-stu-id="ace08-125">![Add range dialog box](../dev-itpro/media/Storehours1.png "Add range dialog box")</span></span>

4. <span data-ttu-id="ace08-126">Associe o modelo de horário de funcionamento com os armazenamentos que será usado.</span><span class="sxs-lookup"><span data-stu-id="ace08-126">Associate the store hours template with the stores where it will be used.</span></span> <span data-ttu-id="ace08-127">Na caixa de diálogo **Escolher nós organizacionais**, selecione os armazenamentos, regiões e organizações aos quais o modelo será associado.</span><span class="sxs-lookup"><span data-stu-id="ace08-127">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>

    - <span data-ttu-id="ace08-128">Apenas um modelo de horário de funcionamento pode ser associado com cada loja.</span><span class="sxs-lookup"><span data-stu-id="ace08-128">Only one store hours template can be associated with each store.</span></span>
    - <span data-ttu-id="ace08-129">Use os botões de seta para selecionar lojas, regiões ou organizações.</span><span class="sxs-lookup"><span data-stu-id="ace08-129">Use the arrow buttons to select stores, regions, or organizations.</span></span> <span data-ttu-id="ace08-130">O calendário estará disponível para as lojas ou grupos de loja e estará visível na POS para referência.</span><span class="sxs-lookup"><span data-stu-id="ace08-130">The calendar will be available to the stores or store groups, and it will be visible at the POS for reference.</span></span>

    <span data-ttu-id="ace08-131">![Escolha a caixa de diálogo dos nós da organização](../dev-itpro/media/Storehours2.png "Escolha a caixa de diálogo dos nós da organização")</span><span class="sxs-lookup"><span data-stu-id="ace08-131">![Choose organization nodes dialog box](../dev-itpro/media/Storehours2.png "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="ace08-132">Na página **Agendamento de distribuição**, execute os trabalhos **1070** e **1090** para deixar o horário de funcionamento disponível na POS.</span><span class="sxs-lookup"><span data-stu-id="ace08-132">On the **Distribution schedule** page, run the **1070** and **1090** jobs to make the store hours available to the POS.</span></span>

## <a name="add-store-hours-to-printed-receipts"></a><span data-ttu-id="ace08-133">Adicionar horários de funcionamento a recibos impressos</span><span class="sxs-lookup"><span data-stu-id="ace08-133">Add store hours to printed receipts</span></span>

<span data-ttu-id="ace08-134">Siga essas etapas para adicionar horas de funcionamento aos recibos de POS impressos.</span><span class="sxs-lookup"><span data-stu-id="ace08-134">Follow these steps to add store hours to the printed POS receipts.</span></span>

1. <span data-ttu-id="ace08-135">Abra o designer de recibo.</span><span class="sxs-lookup"><span data-stu-id="ace08-135">Open the receipt designer.</span></span>
2. <span data-ttu-id="ace08-136">Selecione **Rodapé** no canto inferior esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ace08-136">Select **Footer** in the lower-left corner.</span></span>
3. <span data-ttu-id="ace08-137">Arraste o elemento **Horário de funcionamento** no painel esquerdo do rodapé na parte inferior do recibo.</span><span class="sxs-lookup"><span data-stu-id="ace08-137">Drag the **Store hours** element from the left pane to the footer at the bottom of the receipt template.</span></span>
4. <span data-ttu-id="ace08-138">Você pode editar o rótulo padrão no elemento **Horário de funcionamento**.</span><span class="sxs-lookup"><span data-stu-id="ace08-138">You can edit the default label on the **Store hours** element as you require.</span></span>
5. <span data-ttu-id="ace08-139">Salve recibo e feche o designer de recibo.</span><span class="sxs-lookup"><span data-stu-id="ace08-139">Save the receipt, and close the receipt designer.</span></span>
6. <span data-ttu-id="ace08-140">Na página **Agenda de distribuição**, execute os trabalhos **1070** e **1090**.</span><span class="sxs-lookup"><span data-stu-id="ace08-140">On the **Distribution schedule** page, run the **1070** and **1090** jobs.</span></span>
7. <span data-ttu-id="ace08-141">Entrar no PDV.</span><span class="sxs-lookup"><span data-stu-id="ace08-141">Sign in to the POS.</span></span>
8. <span data-ttu-id="ace08-142">Conclua uma venda e selecione para imprimir um recibo.</span><span class="sxs-lookup"><span data-stu-id="ace08-142">Complete a sale, and select to print a receipt.</span></span>

<span data-ttu-id="ace08-143">Recibos de POS agora incluem as horas de funcionamento.</span><span class="sxs-lookup"><span data-stu-id="ace08-143">POS receipts now include the store hours.</span></span> <span data-ttu-id="ace08-144">Se algum feriado foi incluído no modelo, eles são exibidos no recibo.</span><span class="sxs-lookup"><span data-stu-id="ace08-144">If any holidays were included in the template, they are shown on the receipt.</span></span>

<span data-ttu-id="ace08-145">![Exemplo de recibo](../dev-itpro/media/Storehours3.png "Exemplo de recibo")</span><span class="sxs-lookup"><span data-stu-id="ace08-145">![Receipt example](../dev-itpro/media/Storehours3.png "Receipt example")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]