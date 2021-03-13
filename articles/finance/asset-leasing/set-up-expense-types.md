---
title: Configurar tipos de despesa
description: Este tópico explica como configurar tipos de despesa em Arrendamento de ativos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3ab31b16c6ae07466d7655832701e71092064fe1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969494"
---
# <a name="set-up-expense-types"></a><span data-ttu-id="ee8ad-103">Configurar tipos de despesa</span><span class="sxs-lookup"><span data-stu-id="ee8ad-103">Set up expense types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee8ad-104">Este tópico explica como configurar tipos de despesa em Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-104">This topic explains how to set up expense types in Asset leasing.</span></span> <span data-ttu-id="ee8ad-105">Os custos que não são representados pela agenda de pagamento são conhecidos como *custos de despesas*.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-105">Costs that aren't represented by the payment schedule are known as *expense costs*.</span></span> <span data-ttu-id="ee8ad-106">Exemplos desses custos incluem impostos sobre propriedades, custos de manutenção de área comum e despesas de seguro.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-106">Examples of these costs include property taxes, common area maintenance costs, and insurance expenses.</span></span>

## <a name="add-an-administrative-expense-type"></a><span data-ttu-id="ee8ad-107">Adicionar um tipo de despesa administrativa</span><span class="sxs-lookup"><span data-stu-id="ee8ad-107">Add an administrative expense type</span></span>

1. <span data-ttu-id="ee8ad-108">Acesse **Arrendamento de ativo \> Configuração \> Tipos de despesa**.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-108">Go to **Asset leasing \> Setup \> Expense types**.</span></span>
2. <span data-ttu-id="ee8ad-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-109">Select **New**.</span></span>
3. <span data-ttu-id="ee8ad-110">Nos campos apropriados, insira o novo tipo de despesa e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-110">In the appropriate fields, enter the new expense type and a description.</span></span>

## <a name="assign-accounts-to-administrative-costs"></a><span data-ttu-id="ee8ad-111">Atribuir contas a custos administrativos</span><span class="sxs-lookup"><span data-stu-id="ee8ad-111">Assign accounts to administrative costs</span></span>

<span data-ttu-id="ee8ad-112">Em seguida, você deverá associar contas aos tipos de despesa.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-112">Next, you should associate accounts with the expense types.</span></span> <span data-ttu-id="ee8ad-113">Essas contas serão debitadas quando as entradas da agenda de despesas forem lançadas.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-113">These accounts will be debited when expense schedule entries are posted.</span></span> <span data-ttu-id="ee8ad-114">A contrapartida é especificada nas linhas da **Agenda de pagamento de custos de execução** em cada arrendamento.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-114">The offset account is specified on the **Executory costs payment schedule** lines on each lease.</span></span>

1. <span data-ttu-id="ee8ad-115">Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-115">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="ee8ad-116">Na guia **Contas**, na Guia Rápida **Custos de execução**, no campo **Tipo de despesa**, selecione o tipo de despesa.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-116">On the **Accounts** tab, on the **Executory costs** FastTab, in the **Expense type** field, select the expense type.</span></span>
3. <span data-ttu-id="ee8ad-117">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-117">Select **Add**.</span></span>
4. <span data-ttu-id="ee8ad-118">No campo **Tipo de registro**, selecione o tipo de registro a ser vinculado aos custos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-118">In the **Book type** field, select the book type to link to the administrative costs.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee8ad-119">Vários tipos de registro podem ser vinculados à mesma conta de despesa.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-119">Multiple book types can be linked to the same expense account.</span></span>

5. <span data-ttu-id="ee8ad-120">No campo **Código da conta**, especifique a quais arrendamentos o registro deve ser aplicado:</span><span class="sxs-lookup"><span data-stu-id="ee8ad-120">In the **Account code** field, specify which leases the book should be applied to:</span></span>

    - <span data-ttu-id="ee8ad-121">**Todos** – aplique o registro a todos os arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-121">**All** – Apply the book to all leases.</span></span>
    - <span data-ttu-id="ee8ad-122">**Grupo** – aplique o registro a um grupo específico de arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-122">**Group** – Apply the book to a specific group of leases.</span></span>
    - <span data-ttu-id="ee8ad-123">**Tabela** – aplique o registro a arrendamentos específicos.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-123">**Table** – Apply the book to specific leases.</span></span>

6. <span data-ttu-id="ee8ad-124">Se você tiver selecionado **Grupo** ou **Tabela** no campo **Código de conta**, selecione um número da conta ou número do grupo no campo **Número da Conta/Grupo**.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-124">If you selected **Group** or **Table** in the **Account code** field, select an account number or group number in the **Account/Group number** field.</span></span>
7. <span data-ttu-id="ee8ad-125">Nos campos apropriados, selecione a conta principal do arrendamento mercantil e a conta principal do arrendamento operacional.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-125">In the appropriate fields, select the finance lease main account and the operating lease main account.</span></span>

<span data-ttu-id="ee8ad-126">Depois de concluir estas etapas, você poderá adicionar despesas por meio das linhas de **Agenda de pagamento de custos de execução** na página **Detalhes do arrendamento** de um arrendamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-126">When you've completed these steps, you can add expenses through the **Executory costs payment schedule** lines on the **Lease details** page of a selected lease.</span></span> <span data-ttu-id="ee8ad-127">Como alternativa, você pode adicionar despesas ao criar um novo arrendamento.</span><span class="sxs-lookup"><span data-stu-id="ee8ad-127">Alternatively, you can add expenses when you create a new lease.</span></span>