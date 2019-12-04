---
title: Configurar descrições padrão para lançamento automático
description: Este tópico explica como configurar o texto padrão que é usado para descrever entradas de contabilidade lançadas automaticamente na contabilidade. Você pode configurar o texto padrão de descrição usando o texto livre ou selecionando variáveis fixas.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: eb89f50a3d227cad80226ce30f71c4f210129245
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622680"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a><span data-ttu-id="35809-104">Configurar descrições padrão para lançamento automático</span><span class="sxs-lookup"><span data-stu-id="35809-104">Set up default descriptions for automatic posting</span></span>

<span data-ttu-id="35809-105">Este tópico explica como configurar o texto padrão que é usado para descrever entradas de contabilidade lançadas automaticamente na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="35809-105">This topic explains how to set up default text that is used to describe accounting entries that are posted automatically to the general ledger.</span></span> <span data-ttu-id="35809-106">Você pode configurar o texto padrão de descrição usando o texto livre ou selecionando variáveis fixas.</span><span class="sxs-lookup"><span data-stu-id="35809-106">You can set up default description text by using free-form text or by selecting fixed variables.</span></span>

> [!NOTE]
> <span data-ttu-id="35809-107">Para determinados tipos de transação em alguns países ou regiões, também é possível incluir o texto dos campos no banco de dados Microsoft Dynamics AX que estão relacionados a esses tipos de transação.</span><span class="sxs-lookup"><span data-stu-id="35809-107">For some transaction types in some countries or regions, you can also include text from fields in the Microsoft Dynamics AX database that are related to those transaction types.</span></span> <span data-ttu-id="35809-108">Para obter uma lista de tipos de transação, além de países e regiões, consulte a seção [Opcional: adicionar texto às descrições padrão](#optional-add-other-text-to-default-descriptions) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="35809-108">For a list of the transaction types, and the countries and regions, see the [Optional: Add other text to default descriptions](#optional-add-other-text-to-default-descriptions) section later in this topic.</span></span>

## <a name="set-up-default-descriptions"></a><span data-ttu-id="35809-109">Configurar descrições padrão</span><span class="sxs-lookup"><span data-stu-id="35809-109">Set up default descriptions</span></span>

1. <span data-ttu-id="35809-110">Vá para **Administração da organização** \> **Configuração** \> **Descrições padrão**.</span><span class="sxs-lookup"><span data-stu-id="35809-110">Go to **Organization administration** \> **Setup** \> **Default descriptions**.</span></span>
2. <span data-ttu-id="35809-111">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="35809-111">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="35809-112">No campo **Descrição**, selecione o tipo de transação para o qual uma descrição padrão será criada.</span><span class="sxs-lookup"><span data-stu-id="35809-112">In the **Description** field, select the type of transaction to create a default description for.</span></span>
4. <span data-ttu-id="35809-113">No campo **Idioma**, selecione o idioma para o qual esta descrição será aplicada.</span><span class="sxs-lookup"><span data-stu-id="35809-113">In the **Language** field, select the language that the description applies to.</span></span>
5. <span data-ttu-id="35809-114">No campo **Texto**, insira uma descrição padrão.</span><span class="sxs-lookup"><span data-stu-id="35809-114">In the **Text** field, enter the default description.</span></span> <span data-ttu-id="35809-115">Você pode digitar o texto no campo ou usar uma ou mais das seguintes variáveis de texto livre:</span><span class="sxs-lookup"><span data-stu-id="35809-115">You can type text in the field, or you can use one or more of the following free-text variables:</span></span>

    - <span data-ttu-id="35809-116">**%1** – adicione a data de transação.</span><span class="sxs-lookup"><span data-stu-id="35809-116">**%1** – Add the transaction date.</span></span>
    - <span data-ttu-id="35809-117">**%2** – adiciona um identificador que corresponde ao tipo de documento que está sendo lançado na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="35809-117">**%2** – Add an identifier that corresponds to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="35809-118">Por exemplo, para os tipos de transação relacionados a faturas, a variável **%2** adiciona o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="35809-118">For example, for transaction types that are related to invoices, the **%2** variable adds the invoice number.</span></span>
    - <span data-ttu-id="35809-119">**%3** – adicione um identificador relacionado ao tipo de documento que está sendo lançado na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="35809-119">**%3** – Add an identifier that is related to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="35809-120">Por exemplo, para os tipos de transação relacionados a faturas, a variável **%3** adiciona o número de conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="35809-120">For example, for transaction types that are related to invoices, the **%3** variable adds the customer account number.</span></span>

## <a name="optional-add-other-text-to-default-descriptions"></a><span data-ttu-id="35809-121">Opcional: Adicionar outro texto para descrições padrão</span><span class="sxs-lookup"><span data-stu-id="35809-121">Optional: Add other text to default descriptions</span></span>

<span data-ttu-id="35809-122">Para determinados tipos de transação em alguns países ou algumas regiões, é possível incluir o texto em suas descrições padrão que vem dos campos no seus dados que estão relacionados a esses tipos de transação.</span><span class="sxs-lookup"><span data-stu-id="35809-122">For some transaction types in some countries or regions, default descriptions can include text that comes from fields in your data that are related to those transaction types.</span></span> <span data-ttu-id="35809-123">As listas a seguir mostram os tipos de transação, os países e as regiões para os quais esta opção está disponível.</span><span class="sxs-lookup"><span data-stu-id="35809-123">The following lists show the transaction types, and the countries and regions, that this option is available for.</span></span>

<span data-ttu-id="35809-124">**Tipos de transação**</span><span class="sxs-lookup"><span data-stu-id="35809-124">**Transaction types**</span></span>

<span data-ttu-id="35809-125">Você pode adicionar outras descrições de texto padrão para os tipos de transação relacionados aos seguintes tipos de documento:</span><span class="sxs-lookup"><span data-stu-id="35809-125">You can add other text to default descriptions for transaction types that are related to the following document types:</span></span>

- <span data-ttu-id="35809-126">Faturas de clientes</span><span class="sxs-lookup"><span data-stu-id="35809-126">Customer invoices</span></span>
- <span data-ttu-id="35809-127">Notas de crédito de clientes</span><span class="sxs-lookup"><span data-stu-id="35809-127">Customer credit notes</span></span>
- <span data-ttu-id="35809-128">Pagamentos à vista de clientes</span><span class="sxs-lookup"><span data-stu-id="35809-128">Customer cash payments</span></span>
- <span data-ttu-id="35809-129">Pagamentos de fornecedores</span><span class="sxs-lookup"><span data-stu-id="35809-129">Vendor payments</span></span>
- <span data-ttu-id="35809-130">Ordens de venda</span><span class="sxs-lookup"><span data-stu-id="35809-130">Sales orders</span></span>
- <span data-ttu-id="35809-131">Ordens de compra</span><span class="sxs-lookup"><span data-stu-id="35809-131">Purchase orders</span></span>
- <span data-ttu-id="35809-132">Diários de estoque</span><span class="sxs-lookup"><span data-stu-id="35809-132">Inventory journals</span></span>
- <span data-ttu-id="35809-133">Planejamento mestre (MRP)</span><span class="sxs-lookup"><span data-stu-id="35809-133">Master planning (MRP)</span></span>
- <span data-ttu-id="35809-134">Ativos fixos</span><span class="sxs-lookup"><span data-stu-id="35809-134">Fixed assets</span></span>

<span data-ttu-id="35809-135">**Países e regiões**</span><span class="sxs-lookup"><span data-stu-id="35809-135">**Countries and regions**</span></span>

<span data-ttu-id="35809-136">Essa opção está disponível somente para os seguintes países e regiões:</span><span class="sxs-lookup"><span data-stu-id="35809-136">This option is available for the following countries and regions:</span></span>

- <span data-ttu-id="35809-137">Brasil</span><span class="sxs-lookup"><span data-stu-id="35809-137">Brazil</span></span>
- <span data-ttu-id="35809-138">China</span><span class="sxs-lookup"><span data-stu-id="35809-138">China</span></span>
- <span data-ttu-id="35809-139">República Tcheca</span><span class="sxs-lookup"><span data-stu-id="35809-139">Czech Republic</span></span>
- <span data-ttu-id="35809-140">Leste Europeu</span><span class="sxs-lookup"><span data-stu-id="35809-140">Eastern Europe</span></span>
- <span data-ttu-id="35809-141">Hungria</span><span class="sxs-lookup"><span data-stu-id="35809-141">Hungary</span></span>
- <span data-ttu-id="35809-142">Índia</span><span class="sxs-lookup"><span data-stu-id="35809-142">India</span></span>
- <span data-ttu-id="35809-143">Japão</span><span class="sxs-lookup"><span data-stu-id="35809-143">Japan</span></span>
- <span data-ttu-id="35809-144">Lituânia</span><span class="sxs-lookup"><span data-stu-id="35809-144">Lithuania</span></span>
- <span data-ttu-id="35809-145">Letônia</span><span class="sxs-lookup"><span data-stu-id="35809-145">Latvia</span></span>
- <span data-ttu-id="35809-146">Polônia</span><span class="sxs-lookup"><span data-stu-id="35809-146">Poland</span></span>
- <span data-ttu-id="35809-147">Rússia</span><span class="sxs-lookup"><span data-stu-id="35809-147">Russia</span></span>

### <a name="add-text-to-default-descriptions"></a><span data-ttu-id="35809-148">Adicionar texto às descrições padrão</span><span class="sxs-lookup"><span data-stu-id="35809-148">Add text to default descriptions</span></span>

<span data-ttu-id="35809-149">Depois de concluir as etapas na seção [Definir descrições padrão](#set-up-default-descriptions), anteriormente neste tópico, siga estas etapas para adicionar outro texto para as descrições padrão.</span><span class="sxs-lookup"><span data-stu-id="35809-149">After you complete the steps in the [Set up default descriptions](#set-up-default-descriptions) section earlier in this topic, follow these steps to add other text to the default descriptions.</span></span>

1. <span data-ttu-id="35809-150">Na Guia Rápida **Parâmetros**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="35809-150">On the **Parameters** FastTab, select **Add**.</span></span>
2. <span data-ttu-id="35809-151">No campo **Tabela de referência**, selecione a tabela de banco de dados da qual os dados de parâmetros serão adicionados à descrição.</span><span class="sxs-lookup"><span data-stu-id="35809-151">In the **Reference table** field, select the database table from which to add parameter data to the description.</span></span>
3. <span data-ttu-id="35809-152">No campo **Tabela de referência**, selecione o campo do qual os dados de parâmetros serão adicionados à descrição.</span><span class="sxs-lookup"><span data-stu-id="35809-152">In the **Reference field** field, select the field from which to add parameter data to the description.</span></span>
4. <span data-ttu-id="35809-153">Repita as etapas 1 a 3 para adicionar mais parâmetros.</span><span class="sxs-lookup"><span data-stu-id="35809-153">Repeat steps 1 through 3 to add more parameters.</span></span>