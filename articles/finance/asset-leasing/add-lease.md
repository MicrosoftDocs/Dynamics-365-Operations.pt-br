---
title: Adicionar ou copiar arrendamentos (Versão preliminar)
description: Este tópico descreve como criar um novo arrendamento inserindo informações sobre arrendamento de ativos ou copiando informações de um arrendamento existente.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: abbf04d009a4b347792cd8b317e334da2a4cbbee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969594"
---
# <a name="add-or-copy-leases-preview"></a><span data-ttu-id="7aa8a-103">Adicionar ou copiar arrendamentos (Versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="7aa8a-103">Add or copy leases (Preview)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7aa8a-104">Este tópico explica como criar um arrendamento do zero no arrendamento do ativo e também como criar um arrendamento copiando um arrendamento existente.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-104">This topic explains how to create a lease from scratch in Asset leasing, and also how to create a lease by copying an existing lease.</span></span> <span data-ttu-id="7aa8a-105">O processo de criação de um arrendamento a partir do zero envolve a inserção de informações para o novo arrendamento e, em seguida, a criação de um plano de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-105">The process for creating a lease from scratch involves entering information for the new lease and then creating a lease schedule.</span></span> <span data-ttu-id="7aa8a-106">Depois que pelo menos um arrendamento for configurado, talvez seja mais fácil copiar as informações de um arrendamento existente e editar essas informações, conforme necessário para criar um novo arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-106">After at least one lease has been set up, you might find it easier to copy the information from an existing lease and then edit that information as you require to create a new lease.</span></span>

## <a name="create-a-lease"></a><span data-ttu-id="7aa8a-107">Criar um arrendamento</span><span class="sxs-lookup"><span data-stu-id="7aa8a-107">Create a lease</span></span>

<span data-ttu-id="7aa8a-108">Siga estas etapas para criar um arrendamento no arrendamento do ativo.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-108">Follow these steps to create a lease in Asset leasing.</span></span>

1. <span data-ttu-id="7aa8a-109">Na página **Resumo de arrendamento**, no Painel de Ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-109">On the **Lease summary** page, on the Action Pane, select **New**.</span></span>
2. <span data-ttu-id="7aa8a-110">Insira as informações sobre o arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-110">Enter the lease information.</span></span> <span data-ttu-id="7aa8a-111">Os campos necessários têm bordas vermelhas.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-111">Fields that are required have red borders.</span></span>

## <a name="create-a-lease-schedule"></a><span data-ttu-id="7aa8a-112">Crie uma agenda de arrendamento</span><span class="sxs-lookup"><span data-stu-id="7aa8a-112">Create a lease schedule</span></span>

<span data-ttu-id="7aa8a-113">Depois de concluir a inserção das informações para o arrendamento, siga estas etapas para criar uma agenda de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-113">After you've finished entering information for the lease, follow these steps to create a lease schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="7aa8a-114">As dimensões financeiras podem ser alteradas com base em quaisquer dimensões financeiras personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-114">The financial dimensions might change based on any custom financial dimensions.</span></span>

1. <span data-ttu-id="7aa8a-115">Selecione **Criar agendas** para gerar os registros de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-115">Select **Create schedules** to generate the lease books.</span></span> <span data-ttu-id="7aa8a-116">Os registros de arrendamento incluem pagamento, amortização, depreciação e agendas de despesas.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-116">The lease books include the payment, amortization, depreciation, and expense schedules.</span></span>
2. <span data-ttu-id="7aa8a-117">Para acessar os registros de leasing e exibir os agendamentos recém-criados, selecione a guia **Livros**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-117">To access the lease books and view the newly created schedules, select the **Books** tab.</span></span>

    <span data-ttu-id="7aa8a-118">A página **Detalhes do registro** mostra como o arrendamento é contabilizado pelos livros que foram alocados para ele.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-118">The **Book details** page shows how the lease is accounted for by the books that have been allocated to it.</span></span> <span data-ttu-id="7aa8a-119">A partir daqui, você pode exibir as agendas de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-119">From here, you can view the lease schedules.</span></span>

    <span data-ttu-id="7aa8a-120">A agenda de pagamento contém as entradas da guia **Linhas da agenda de pagamento** na página **Adicionar arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-120">The payment schedule contains the inputs from the **Payment schedule lines** tab on the **Add lease** page.</span></span> <span data-ttu-id="7aa8a-121">Você ainda pode alterar cada valor do pagamento e pagamento variável.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-121">You can still change each payment amount and variable payment.</span></span> <span data-ttu-id="7aa8a-122">A responsabilidade com o arrendamento é calculada com base na agenda de pagamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-122">The lease liability is calculated based on the modified payment schedule.</span></span>

4. <span data-ttu-id="7aa8a-123">Depois de concluir a revisão da agenda de pagamento, selecione **Confirmar agenda**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-123">After you've finished reviewing the payment schedule, select **Confirm schedule**.</span></span> <span data-ttu-id="7aa8a-124">Depois que a agenda for confirmada, o arrendamento não estará mais disponível para edição.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-124">After the schedule is confirmed, the lease is no longer available for editing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7aa8a-125">O sistema calcula automaticamente o prazo de arrendamento das linhas da agenda de pagamento na página **Adicionar arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-125">The system automatically calculates the lease term from the payment schedule lines on the **Add lease** page.</span></span>
    >
    > <span data-ttu-id="7aa8a-126">Para calcular o prazo de arrendamento em meses, o sistema encontra a diferença entre a data inicial e a data final de uma linha específica da agenda de pagamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-126">To calculate the lease term in months, the system finds the difference between the start date and the end date for a specific payment schedule line.</span></span> <span data-ttu-id="7aa8a-127">Em seguida, ele passa para a próxima linha da agenda de pagamento e localiza a diferença novamente.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-127">It then moves to the next payment schedule line and finds the difference again.</span></span> <span data-ttu-id="7aa8a-128">Finalmente, o sistema soma todos os valores para determinar o prazo de arrendamento em meses.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-128">Finally, the system sums all the amounts to determine the lease term in months.</span></span>

5. <span data-ttu-id="7aa8a-129">Para exibir as despesas de juros do período calculado, abra a página **Agenda amortização de passivo**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-129">To view the calculated period interest expenses, open the **Liability amortization schedule** page.</span></span> <span data-ttu-id="7aa8a-130">Para exibir a depreciação de linha reta calculada, abra a página **Agenda de depreciação de ativo**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-130">To view calculated straight-line depreciation, open the **Asset depreciation schedule** page.</span></span>
6. <span data-ttu-id="7aa8a-131">Depois de concluir a revisão do valor calculado, você pode criar a entrada do diário de reconhecimento inicial na página **Reconhecimento inicial**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-131">After you've finished reviewing the calculated amount, you can create the initial recognition journal entry on the **Initial recognition** page.</span></span> <span data-ttu-id="7aa8a-132">Você recebe uma mensagem que declara que o diário foi criado.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-132">You receive a message that states that the journal has been created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7aa8a-133">A entrada de diário não é lançada na contabilidade até que você coloque manualmente a entrada.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-133">The journal entry isn't posted to General ledger until you manually post the entry.</span></span>

7. <span data-ttu-id="7aa8a-134">Para revisar a entrada de reconhecimento inicial proposta antes de lançá-la, selecione **Diário de arrendamento de ativo**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-134">To review the proposed initial recognition entry before you post it, select **Asset leasing journal**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7aa8a-135">O diário de arrendamento de ativo não pode ser criado manualmente.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-135">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="7aa8a-136">Ele é criado automaticamente quando as agendas de arrendamento são criadas.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-136">It's automatically created when lease schedules are created.</span></span>

8. <span data-ttu-id="7aa8a-137">Quando terminar de revisar a entrada do diário de reconhecimento inicial e estiver pronto para lançá-la, selecione **Lançar** para reconhecer o ativo de direito de uso (DDU) e a responsabilidade com arrendamento na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-137">When you've finished reviewing the initial recognition journal entry and are ready to post it, select **Post** to recognize the right-of-use (ROU) asset and lease liability in General ledger.</span></span>

## <a name="copy-a-lease"></a><span data-ttu-id="7aa8a-138">Copiar um arrendamento</span><span class="sxs-lookup"><span data-stu-id="7aa8a-138">Copy a lease</span></span>

<span data-ttu-id="7aa8a-139">O arrendamento de ativos permite copiar os detalhes de um arrendamento para criar uma novo arrendamento com as mesmas informações.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-139">Asset leasing lets you copy the details of a lease to create a new lease that has the same information.</span></span> <span data-ttu-id="7aa8a-140">Em seguida, você poderá alterar os campos de arrendamento antes de criar os planos para o arrendamento copiado.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-140">You can then change the lease fields before you create the schedules for the copied lease.</span></span>

1. <span data-ttu-id="7aa8a-141">Na página **Resumo de arrendamento**, selecione o arrendamento a ser copiado e, no Painel de Ação, selecione **Copiar arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-141">On the **Lease summary** page, select the lease to copy, and then, on the Action Pane, select **Copy lease**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7aa8a-142">Se o parâmetro **Manual** estiver desativado para a sequência numérica das IDs de arrendamento, o próximo número na sequência será gerado automaticamente como a ID do arrendamento copiado.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-142">If the **Manual** parameter is turned off for the number sequence for lease IDs, the next number in the sequence is automatically generated as the lease ID of the copied lease.</span></span> <span data-ttu-id="7aa8a-143">Se o parâmetro **Manual** estiver ativado, você receberá uma mensagem solicitando que você insira a ID de arrendamento antes de continuar a copiar o arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-143">If the **Manual** parameter is turned on, you receive a message that prompts you to enter the lease ID before you proceed to copy the lease.</span></span>

2. <span data-ttu-id="7aa8a-144">Selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-144">Select **Copy**.</span></span> <span data-ttu-id="7aa8a-145">Os detalhes do arrendamento selecionado são copiados para um novo arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-145">The lease details from the selected lease are copied to a new lease.</span></span> <span data-ttu-id="7aa8a-146">Em seguida, você poderá editar os detalhes do novo arrendamento antes de salvá-la e criar os prazos de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-146">You can then edit the details of the new lease before you save it and create the lease schedules.</span></span>

## <a name="asset-leasing-journal"></a><span data-ttu-id="7aa8a-147">Diário de arrendamento de ativo</span><span class="sxs-lookup"><span data-stu-id="7aa8a-147">Asset leasing journal</span></span>

<span data-ttu-id="7aa8a-148">Todas as entradas de diário criadas no arrendamento de ativos estão contidas no diário de arrendamento de ativo.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-148">All journal entries that are created in Asset leasing are contained in the Asset leasing journal.</span></span> <span data-ttu-id="7aa8a-149">Na página **Diário de arrendamento de ativo** (**Arrendamento de ativo \> Lançamentos \> Diário de leasing do ativo**), você pode filtrar por status de lançamento, exibir entradas de diário específicas e comprovantes, e lançar entradas de diário não lançadas.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-149">On the **Asset leasing journal** page (**Asset leasing \> Journal entries \> Asset leasing journal**), you can filter by posting status, view specific journal entries and the vouchers, and post unposted journal entries.</span></span>

> [!NOTE]
> <span data-ttu-id="7aa8a-150">O diário de arrendamento de ativo não pode ser criado manualmente.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-150">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="7aa8a-151">Ele é criado automaticamente quando as agendas de arrendamento são criadas.</span><span class="sxs-lookup"><span data-stu-id="7aa8a-151">It's automatically created when lease schedules are created.</span></span>
