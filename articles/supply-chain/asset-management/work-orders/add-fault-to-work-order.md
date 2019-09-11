---
title: Adicionar falha à ordem de serviço
description: Este tópico descreve como adicionar registros de falha a ordens de serviço no Gerenciamento de Ativos.
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7c86973ca44d9113d14e180e27cc51343da5d2c0
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875509"
---
# <a name="add-fault-to-work-order"></a><span data-ttu-id="6c8c9-103">Adicionar falha à ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="6c8c9-103">Add fault to work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="6c8c9-104">É possível adicionar falhas configuradas no designer de falhas a uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-104">You can add faults set up in the fault designer to a work order.</span></span> <span data-ttu-id="6c8c9-105">O ativo selecionado na ordem de serviço deve conter tipos de ativos que possuem um ou mais registros de falhas conectados a ele.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-105">The asset selected in the work order must contain asset types that have one or more fault records connected to it.</span></span> <span data-ttu-id="6c8c9-106">Leia mais sobre a instalação na seção [Gerenciamento de falhas](../setup-for-work-orders/fault-management.md).</span><span class="sxs-lookup"><span data-stu-id="6c8c9-106">Read more about setup in the [Fault management](../setup-for-work-orders/fault-management.md) section.</span></span>

1. <span data-ttu-id="6c8c9-107">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-107">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="6c8c9-108">Na lista, selecione a ordem de serviço na qual deseja registrar uma falha e clique em **Falha de ativo**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-108">In the list, select the work order on which you want to make a fault registration and click **Asset fault**.</span></span>

3. <span data-ttu-id="6c8c9-109">Na Guia Rápida **Sintomas**, clique em **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-109">On the **Symptoms** FastTab, click **Add line**.</span></span> <span data-ttu-id="6c8c9-110">Um número de falha sequencial é inserido automaticamente no campo **Falha**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-110">A sequential fault number is automatically inserted in the **Fault** field.</span></span>

4. <span data-ttu-id="6c8c9-111">Selecione o sintoma relevante no campo **Sintoma de falha**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-111">Select the relevant symptom in the **Fault symptom** field.</span></span>

5. <span data-ttu-id="6c8c9-112">Selecione **Área com falha** e **Tipo de falha**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-112">Select **Fault area** and **Fault type**.</span></span>

6. <span data-ttu-id="6c8c9-113">No campo **Data da falha**, a data atual é inserida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-113">In the **Fault date** field, the current date is automatically inserted.</span></span> <span data-ttu-id="6c8c9-114">Você pode selecionar outra data, se necessário.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-114">You can select another date, if necessary.</span></span>

7. <span data-ttu-id="6c8c9-115">Na Guia Rápida **Causas do sintoma selecionado**, adicione uma linha descrevendo a causa do problema.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-115">On the **Causes for selected symptom** FastTab, add a line describing the cause of the problem.</span></span>

8. <span data-ttu-id="6c8c9-116">Na Guia Rápida **Recursos do sintoma selecionado**, adicione uma linha descrevendo uma possível solução para o problema.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-116">On the **Remedies for selected symptom** FastTab, add a line describing a possible solution to the problem.</span></span>

9. <span data-ttu-id="6c8c9-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-117">Click **Save**.</span></span>

![Figura 1](media/19-work-orders.png)


## <a name="view-asset-faults"></a><span data-ttu-id="6c8c9-119">Exibir falhas de ativos</span><span class="sxs-lookup"><span data-stu-id="6c8c9-119">View asset faults</span></span>

<span data-ttu-id="6c8c9-120">Na lista **Falhas de ativo**, é possível obter uma visão geral de todas as falhas registradas nos ativos.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-120">In the **Asset faults** list, you can get an overview of all faults registered on assets.</span></span>

<span data-ttu-id="6c8c9-121">Clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Falhas de ativo** para abrir a lista.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-121">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults** to open the list.</span></span>


## <a name="print-asset-fault-report"></a><span data-ttu-id="6c8c9-122">Imprimir relatório de falha de ativo</span><span class="sxs-lookup"><span data-stu-id="6c8c9-122">Print asset fault report</span></span>

<span data-ttu-id="6c8c9-123">Na página da lista **Todos os ativos**, você pode imprimir um relatório de falhas de ativos exibindo todos os registros de falhas, bem como uma visão geral gráfica das estatísticas de falhas.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-123">From the **All assets** list page, you can print an asset fault report displaying all fault registrations as well as a graphic overview of fault statistics.</span></span>

1. <span data-ttu-id="6c8c9-124">Clique em **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-124">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="6c8c9-125">Na lista **Ativos**, selecione o ativo para o qual você deseja imprimir um relatório de falhas.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-125">In the **Assets** list, select the asset for which you want to print a fault report.</span></span>

3. <span data-ttu-id="6c8c9-126">Na guia **Geral** > **seção Relatórios**, clique em **Falha de ativo**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-126">On the **General** tab > **Reports section**, click **Asset fault**.</span></span>

4. <span data-ttu-id="6c8c9-127">Insira um período específico ou selecione um tipo de falha.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-127">Insert a specific period, or select a fault type.</span></span>

5. <span data-ttu-id="6c8c9-128">Clique em **OK** para imprimir o relatório.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-128">Click **OK** to print the report.</span></span>

>[!NOTE]
><span data-ttu-id="6c8c9-129">Você também pode imprimir um relatório de falhas para vários ativos ou tipos de ativos clicando em **Gerenciamento de ativos** > **Relatórios** > **Ativos** > **Falha de ativo**.</span><span class="sxs-lookup"><span data-stu-id="6c8c9-129">You can also print a fault report for several assets or asset types by clicking **Asset management** > **Reports** > **Assets** > **Asset fault**.</span></span>

