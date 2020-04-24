---
title: Criar ordens de serviço automaticamente
description: É possível criar ordens de serviço para um ou vários contratos de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4ba2cf115faacda14e25838a488fc54c53f48f3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202712"
---
# <a name="create-service-orders-automatically"></a><span data-ttu-id="c64fe-103">Criar ordens de serviço automaticamente</span><span class="sxs-lookup"><span data-stu-id="c64fe-103">Create service orders automatically</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c64fe-104">É possível criar ordens de serviço para um ou vários contratos de serviço.</span><span class="sxs-lookup"><span data-stu-id="c64fe-104">You can create service orders for one service agreement or for several service agreements.</span></span> <span data-ttu-id="c64fe-105">Depois de criá-los, exiba os contratos de serviço no formulário **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-105">When they are created, you can view your service orders in the **Service orders** form.</span></span>

<span data-ttu-id="c64fe-106">As ordens de serviço são criadas apenas pelo período válido do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="c64fe-106">Service orders are created only for the valid period of the service agreement.</span></span> <span data-ttu-id="c64fe-107">Se o intervalo especificado na caixa no formulário **Criar ordens de serviço** for anterior à data inicial ou posterior à data final do contrato de serviço, as ordens de serviço serão criadas apenas para a parte do intervalo que está dentro das datas do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="c64fe-107">If the interval that you specify in the **Create service orders** form is before the starting date or after the ending date of the service agreement, service orders are created only for the part of the interval that is within the service agreement dates.</span></span>

<span data-ttu-id="c64fe-108">Ao criar ordens de serviço manual ou automaticamente a partir da linha de contrato de serviço, a ordem de serviço deve estar dentro do intervalo de tempo definido pelas datas inicial e final da linha, a menos que você não especifique uma data final na linha.</span><span class="sxs-lookup"><span data-stu-id="c64fe-108">When you create service orders manually or automatically from the service agreement line, the service order must be in the time interval that is defined by the starting and ending dates for the line, unless you do not specify an ending date on the line.</span></span>

## <a name="create-service-orders-automatically-for-a-service-agreement"></a><span data-ttu-id="c64fe-109">Criar ordens de serviço automaticamente para um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="c64fe-109">Create service orders automatically for a service agreement</span></span>

1.  <span data-ttu-id="c64fe-110">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-110">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="c64fe-111">Selecione um contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="c64fe-111">Select a service agreement.</span></span>

3.  <span data-ttu-id="c64fe-112">Clique na guia **Entregar** e depois clique em **Ordens de serviço planejadas**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-112">Click the **Deliver** tab, and then click **Planned service orders**.</span></span>

4.  <span data-ttu-id="c64fe-113">Especifique as datas nos campos **Data inicial** e **Data final** para definir o período de serviço.</span><span class="sxs-lookup"><span data-stu-id="c64fe-113">Specify dates in the **From date** and **To date** fields to define the service period.</span></span>

5.  <span data-ttu-id="c64fe-114">Marque a caixa de seleção **Mostrar Log de Informações** para exibir uma lista de ordens de serviço criadas.</span><span class="sxs-lookup"><span data-stu-id="c64fe-114">Select the **Show Infolog** check box to display a list of the service orders that are created.</span></span>

6.  <span data-ttu-id="c64fe-115">Selecione os tipos de transação no grupo de campo **Incluir tipos de transação**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-115">Select transaction types in the **Include transaction types** field group.</span></span> <span data-ttu-id="c64fe-116">Os tipos de transação representam as linhas criadas no contrato de serviço, e cada tipo de transação selecionada gera várias ordens de serviço, dependendo do intervalo de serviço especificado na linha do contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="c64fe-116">The transaction types represent the lines that are created in the service agreement, and each transaction type that you select generates several service orders, depending on the service interval that is specified on the service agreement line.</span></span>

7.  <span data-ttu-id="c64fe-117">Para criar todas as ordens de serviço ausentes da série contínua de ordens de serviço, marque a caixa de seleção **Contínuo**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-117">To create any service orders that are missing from continuous series of service orders, select the **Continuous** check box.</span></span>

8.  <span data-ttu-id="c64fe-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-118">Click **OK**.</span></span>

## <a name="create-service-orders-automatically-for-several-service-agreements"></a><span data-ttu-id="c64fe-119">Criar ordens de serviço automaticamente para vários contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="c64fe-119">Create service orders automatically for several service agreements</span></span>

1.  <span data-ttu-id="c64fe-120">Clique em **Gerenciamento de serviço** \> **Periódico** \> **Ordens de serviço** \> **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-120">Click **Service management** \> **Periodic** \> **Service orders** \> **Create service orders**.</span></span>

2.  <span data-ttu-id="c64fe-121">Clique em **Selecionar** para fazer seleções para adicionar ou remover critérios usados para criar ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="c64fe-121">Click **Select** to make selections to add or remove criteria to use to create service orders.</span></span>

3.  <span data-ttu-id="c64fe-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c64fe-122">Click **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c64fe-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c64fe-123">See also</span></span>

[<span data-ttu-id="c64fe-124">Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="c64fe-124">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="c64fe-125">Criar automaticamente ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="c64fe-125">Automatically create service orders</span></span>](auto-create-service-orders.md)

  


