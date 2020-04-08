---
title: Configurar faturamento de projeto intercompanhia
description: Este tópico mostra como configurar o faturamento de projeto entre duas empresas na sua organização.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 31dbae2d37aefe1841fe85cb6caf185c78596e55
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144270"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="3bbe6-103">Configurar faturamento de projeto intercompanhia</span><span class="sxs-lookup"><span data-stu-id="3bbe6-103">Configure intercompany project invoicing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3bbe6-104">Este tópico mostra como configurar o faturamento de projeto entre duas empresas na sua organização.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="3bbe6-105">Essa tarefa usa o conjunto de dados de USSI.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="3bbe6-106">No Painel de Navegação, vá para **Módulos > Contas a pagar > Fornecedores > Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="3bbe6-107">Na lista **Todos os fornecedores**, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="3bbe6-108">No Painel de Ação, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="3bbe6-109">Selecione **Intercompanhia**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="3bbe6-110">Defina **Ativa** como **Sim** para habilitar comercial intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="3bbe6-111">No campo **Empresa do cliente**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="3bbe6-112">No campo **Minha conta**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="3bbe6-113">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-113">Select **Save**.</span></span>
9. <span data-ttu-id="3bbe6-114">Feche as páginas para voltar à home page.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="3bbe6-115">No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Parâmetros de gerenciamento e contabilidade de projetos**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="3bbe6-116">Selecione a guia **Intercompanhia**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="3bbe6-117">Mova o controle deslizante para **Sim** para habilitar folhas de ponto e agendamento de recursos intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="3bbe6-118">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="3bbe6-119">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-119">Select **New**.</span></span>
15. <span data-ttu-id="3bbe6-120">No campo **Entidade legal que toma o empréstimo**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="3bbe6-121">Marque a caixa de seleção **Acumular receita**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="3bbe6-122">No campo **Categoria de folha de ponto padrão**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="3bbe6-123">No campo **Categoria de despesa padrão**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="3bbe6-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-124">Select **Save**.</span></span>
20. <span data-ttu-id="3bbe6-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-125">Close the page.</span></span>
21. <span data-ttu-id="3bbe6-126">No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Lançamento > Configuração de lançamento contábil**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="3bbe6-127">No campo **Tipos de conta contábil**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="3bbe6-128">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-128">Select **New**.</span></span>
24. <span data-ttu-id="3bbe6-129">No campo **Conta principal** da nova linha, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="3bbe6-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-130">Select **Save**.</span></span>
26. <span data-ttu-id="3bbe6-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-131">Close the page.</span></span>
27. <span data-ttu-id="3bbe6-132">No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de transferência**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="3bbe6-133">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-133">Select **New**.</span></span>
29. <span data-ttu-id="3bbe6-134">No campo **Data efetiva**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="3bbe6-135">No campo **Entidade legal que toma o empréstimo**, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="3bbe6-136">No campo **Modelo de preço de transferência**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="3bbe6-137">No campo **Definição de preços**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="3bbe6-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe6-138">Select **Save**.</span></span>

