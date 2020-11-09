---
title: Versão do lote de ordens de transferência parcialmente reservadas
description: Este tópico descreve como configurar e aplicar liberação de lote das ordens de transferência reservadas parcialmente de um dispositivo móvel.
author: pjacobse
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7807ae109a4a708f3530112feed1a4fb210a30ef
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016277"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a><span data-ttu-id="786d3-103">Versão do lote de ordens de transferência parcialmente reservadas</span><span class="sxs-lookup"><span data-stu-id="786d3-103">Batch release of partially reserved transfer orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="786d3-104">A funcionalidade de liberação de lote de ordens de transferência reservada parcialmente permite que você libere as ordens se transferência parcialmente para um depósito usando um trabalho de lote.</span><span class="sxs-lookup"><span data-stu-id="786d3-104">The functionality for batch release of partially reserved transfer orders lets you partially release transfer orders to a warehouse by using a batch job.</span></span>
<span data-ttu-id="786d3-105">Como você tem a opção de liberar uma quantidade parcial, você não terá que esperar a quantidade total da ordem ficar disponível no depósito antes de liberar uma ordem.</span><span class="sxs-lookup"><span data-stu-id="786d3-105">Because you have the option to release a partial quantity, you don’t have to wait for the whole order quantity to be available in the warehouse before you release an order.</span></span>

<span data-ttu-id="786d3-106">A liberação de ordens para um depósito é um processo de gerenciamento de depósito avançado.</span><span class="sxs-lookup"><span data-stu-id="786d3-106">The release of orders to a warehouse is an advanced warehouse management process.</span></span> <span data-ttu-id="786d3-107">Este processo envolve atividades como separação, embalagem e entrega que um trabalhador do depósito pode executar usando um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="786d3-107">This process involves activities, such as picking, packing, and shipping, that a warehouse worker can perform by using a mobile device.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="786d3-108">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="786d3-108">Where it applies</span></span>

<span data-ttu-id="786d3-109">Para esta funcionalidade, as ordens de transferência são liberadas para um depósito usando um trabalho de lote.</span><span class="sxs-lookup"><span data-stu-id="786d3-109">For this functionality, transfer orders are released to a warehouse by using a batch job.</span></span> <span data-ttu-id="786d3-110">Essa funcionalidade será útil quando não houver estoque suficiente no depósito, mas você ainda queira transferir itens de um depósito para outro.</span><span class="sxs-lookup"><span data-stu-id="786d3-110">This functionality is useful when you don’t have enough inventory in the warehouse, but you still want to transfer items from one warehouse to another.</span></span>

## <a name="how-it-is-set-up"></a><span data-ttu-id="786d3-111">Como é configurada</span><span class="sxs-lookup"><span data-stu-id="786d3-111">How it is set up</span></span>

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="786d3-112">Especificar critérios de atendimento para ordens de venda e ordens de transferência</span><span class="sxs-lookup"><span data-stu-id="786d3-112">Specify fulfillment criteria for transfer orders and sales orders</span></span>

<span data-ttu-id="786d3-113">Antes que uma ordem possa ser liberada parcialmente para um depósito em um lote, os critérios de atendimento devem ser atendidos.</span><span class="sxs-lookup"><span data-stu-id="786d3-113">Before an order can be partially released to a warehouse in a batch, the fulfillment criteria must be met.</span></span> <span data-ttu-id="786d3-114">Esses critérios de atendimento são determinados pela política de atendimento.</span><span class="sxs-lookup"><span data-stu-id="786d3-114">These fulfillment criteria are determined by the fulfillment policy.</span></span>

<span data-ttu-id="786d3-115">As políticas de atendimento para ordens de venda e ordens de transferência são especificadas na empresa.</span><span class="sxs-lookup"><span data-stu-id="786d3-115">Fulfillment policies for transfer orders and sales orders are specified at the company level.</span></span> <span data-ttu-id="786d3-116">Dependendo da instalação da política de atendimento, a liberação de ordens em um lote será aceita ou rejeitada.</span><span class="sxs-lookup"><span data-stu-id="786d3-116">Depending on the setup of the fulfillment policy, the release of orders in a batch will be accepted or rejected.</span></span> <span data-ttu-id="786d3-117">As ordens serão processados apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="786d3-117">The orders will then be processed accordingly.</span></span>

-   <span data-ttu-id="786d3-118">Para criar políticas de atendimento para ordens de transferência e ordens de venda, clique em **Gerenciamento de depósito** \> **Configuração** \> **Liberar para o depósito** \> **Política de atendimento** e, em seguida, crie uma política de atendimento inserindo um nome e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="786d3-118">To create fulfillment policies for transfer orders and sales orders, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy** , and then create a fulfillment policy by entering a name and a description.</span></span>

-   <span data-ttu-id="786d3-119">Para especificar uma taxa de atendimento, um tipo de valor e a mensagem que é mostrada, se a política de atendimento for violada, clique em **Gerenciamento de depósito** \> **Configurar** \> **Liberar para o depósito** \> **Política de atendimento** e, em seguida, defina os campos **Taxa de atendimento** , **Tipo de valor** e **Mensagem de violação de atendimento**.</span><span class="sxs-lookup"><span data-stu-id="786d3-119">To specify a fulfillment rate, a value type, and the message that is shown if the fulfillment policy is violated, click **Warehouse management** \> **Setup** \> **Release to warehouse** \> **Fulfillment policy** , and then set the **Fulfillment rate** , **Value type** , and **Fulfillment violation message** fields.</span></span>

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a><span data-ttu-id="786d3-120">Defina as políticas de atendimento para ordens de venda e ordens de transferência</span><span class="sxs-lookup"><span data-stu-id="786d3-120">Set the fulfillment policies for transfer orders and sales orders</span></span>

-   <span data-ttu-id="786d3-121">Para definir as políticas de atendimento para ordens de transferência, clique em **Gerenciamento de estoque** \> **Configurar** \> **Parâmetros de gerenciamento de depósito e estoque.** \> **Ordens de transferência** \> **Gerenciamento de depósito** e, em seguida, selecione uma política de atendimento da ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="786d3-121">To set the fulfillment policies for transfer orders, click **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters** \> **Transfer orders** \> **Warehouse management** , and then select a transfer order fulfillment policy.</span></span>

-   <span data-ttu-id="786d3-122">Para definir as políticas de atendimento das ordens de venda, clique em **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber** \> **Gerenciamento de depósito** e selecione uma política de atendimento da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="786d3-122">To set the fulfillment policies for sales orders, click **Accounts receivable** \> **Setup** \> **Accounts receivable parameters** \> **Warehouse management** , and then select a sales order fulfillment policy.</span></span>

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a><span data-ttu-id="786d3-123">Permitir a liberação em um lote e especificar a quantidade que deve ser liberada em um lote</span><span class="sxs-lookup"><span data-stu-id="786d3-123">Allow release in a batch and specify the quantity that should be release in a batch</span></span>

<span data-ttu-id="786d3-124">Um trabalho em lotes é usado para liberar ordens para um depósito em um lote.</span><span class="sxs-lookup"><span data-stu-id="786d3-124">A batch job is used to release orders to a warehouse in a batch.</span></span> <span data-ttu-id="786d3-125">Os parâmetros que distinguem ordens que devem ser executadas em um trabalho em lotes são definidos no próprio trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="786d3-125">The parameters that distinguish the orders that should be run in a batch job are set on the batch job itself.</span></span>

<span data-ttu-id="786d3-126">O parâmetro **Quantidade** especifica se toda a quantidade ou a quantidade fisicamente reservada deve ser liberada em lote.</span><span class="sxs-lookup"><span data-stu-id="786d3-126">The **Quantity** parameter specifies whether the whole quantity or the physically reserved quantity should be released in the batch.</span></span> <span data-ttu-id="786d3-127">O parâmetro **Permitir a liberação de ordens parcialmente liberadas** determina se as ordens em lote devem ser aceitas ou rejeitada, caso tenham sido liberadas parcialmente anteriormente.</span><span class="sxs-lookup"><span data-stu-id="786d3-127">The **Allow release of partially released orders** parameter determines whether orders in the batch should be accepted or rejected if they were partially released earlier.</span></span>

-   <span data-ttu-id="786d3-128">Para definir parâmetros **Quantidade** e **Permitir a liberação de ordens parcialmente liberada** para ordens de transferência, clique em **Permitir a liberação de ordens parcialmente liberada** \> **Liberar para o depósito** \> **Liberação automática de ordens de transferência**.</span><span class="sxs-lookup"><span data-stu-id="786d3-128">To set the **Quantity** and **Allow release of partially released orders** parameters for transfer orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of transfer orders**.</span></span>

-   <span data-ttu-id="786d3-129">Para definir os parâmetros **Quantidade** e **Permitir a liberação de ordens parcialmente liberadas** para ordens de venda, clique em **Gerenciamento de depósito** \> **Liberar para o depósito** \> **Liberação automática de ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="786d3-129">To set the **Quantity** and **Allow release of partially released orders** parameters for sales orders, click **Warehouse management** \> **Release to warehouse** \> **Automatic release of sales orders**.</span></span>
