---
title: Adicionar falha à ordem de serviço
description: Este tópico descreve como adicionar registros de falha a ordens de serviço no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e82026f1d73e7368d93109bc0b895b7368ac84d4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215185"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="f4dc0-103">Adicionar falha à ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="f4dc0-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="f4dc0-104">É possível adicionar falhas que foram configuradas no designer de falhas a uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-104">You can add faults that were set up in the fault designer to a work order.</span></span> <span data-ttu-id="f4dc0-105">Um ou mais registros de falha devem estar conectados aos tipos de ativo usados para o ativo selecionado na ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-105">One or more fault records must be connected to the asset types that are used for the asset that is selected in the work order.</span></span> <span data-ttu-id="f4dc0-106">Para obter mais informações sobre a configuração, consulte [Gerenciamento de falhas](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="f4dc0-106">For more information about the setup, see [Fault management](../setup-for-work-orders/fault-management.md).</span></span>

1. <span data-ttu-id="f4dc0-107">Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-107">Select **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="f4dc0-108">Selecione a ordem de serviço para a qual será criado um registro de falha e, em seguida, no Painel de Ação, na guia **Ordem de serviço**, no grupo **Ativo**, selecione **Falha de ativo**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-108">Select the work order to make a fault registration on, and then, on the Action Pane, on the **Work order** tab, in the **Asset** group, select **Asset fault**.</span></span>

3. <span data-ttu-id="f4dc0-109">Na Guia Rápida **Sintomas**, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-109">On the **Symptoms** FastTab, select **Add line**.</span></span> <span data-ttu-id="f4dc0-110">Um número de falha sequencial é inserido automaticamente no campo **Falha**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-110">A sequential fault number is automatically entered in the **Fault** field.</span></span>

4. <span data-ttu-id="f4dc0-111">No campo **Sintoma de falha**, selecione o sintoma relevante.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-111">In the **Fault symptom** field, select the relevant symptom.</span></span>

5. <span data-ttu-id="f4dc0-112">Nos campos **Área de falha** e **Tipo de falha**, selecione os valores apropriados.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-112">In the **Fault area** and **Fault type** fields, select the appropriate values.</span></span>

6. <span data-ttu-id="f4dc0-113">No campo **Data da falha**, a data atual é inserida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="f4dc0-114">Você pode selecionar uma data diferente conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-114">You can select a different date as you require.</span></span>

7. <span data-ttu-id="f4dc0-115">Na Guia Rápida **Causas do sintoma selecionado**, adicione uma linha para descrever a causa do problema.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-115">On the **Causes for selected symptom** FastTab, add a line to describe the cause of the issue.</span></span>

8. <span data-ttu-id="f4dc0-116">Na Guia Rápida **Recursos para o sintoma selecionado**, adicione uma linha para descrever uma possível solução para o problema.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-116">On the **Remedies for selected symptom** FastTab, add a line to describe a possible solution to the issue.</span></span>

9. <span data-ttu-id="f4dc0-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-117">Select **Save**.</span></span>

<span data-ttu-id="f4dc0-118">A ilustração a seguir mostra um exemplo de um registro de falha.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-118">The illustration below shows an example of a fault registration.</span></span>

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="f4dc0-120">Exibir falhas de ativos</span><span class="sxs-lookup"><span data-stu-id="f4dc0-120">View asset faults</span></span>

<span data-ttu-id="f4dc0-121">Na lista **Falhas de ativo**, é possível obter uma visão geral de todas as falhas registradas nos ativos.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-121">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="f4dc0-122">Na página de listagem **Falhas de ativo**, é possível obter uma visão geral de todas as falhas registradas nos ativos.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-122">On the **Asset faults** list page, you can get an overview of all faults that have been registered on assets.</span></span> <span data-ttu-id="f4dc0-123">Para abrir a página, selecione **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Falhas de ativo**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-123">To open the page, select **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="f4dc0-124">Imprimir relatório de falha de ativo</span><span class="sxs-lookup"><span data-stu-id="f4dc0-124">Print asset fault report</span></span>

<span data-ttu-id="f4dc0-125">Na página de listagem **Todos os ativos**, você pode imprimir um relatório de falhas de ativos que mostre todos os registros de falha e uma visão geral gráfica das estatísticas de falhas.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-125">From the **All assets** list page, you can print an asset fault report that shows all fault registrations and a graphical overview of fault statistics.</span></span>

1. <span data-ttu-id="f4dc0-126">Selecione **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-126">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="f4dc0-127">Selecione o ativo para o qual será impresso um relatório de falha.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-127">Select the asset to print a fault report for.</span></span>

3. <span data-ttu-id="f4dc0-128">No Painel de Ação, na guia **Geral**, no grupo **Relatórios**, selecione **Falha de ativo**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-128">On the Action Pane, on the **General** tab, in the **Reports** group, select **Asset fault**.</span></span>

4. <span data-ttu-id="f4dc0-129">Insira um período específico ou selecione um tipo de falha.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-129">Enter a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="f4dc0-130">Selecione **OK** para imprimir o relatório.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-130">Select **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="f4dc0-131">Para imprimir um relatório de falhas para vários ativos ou tipos de ativos, selecione **Gerenciamento de ativos** > **Relatórios** > **Ativos** > **Falha de ativo**.</span><span class="sxs-lookup"><span data-stu-id="f4dc0-131">To print a fault report for several assets or asset types, select **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

