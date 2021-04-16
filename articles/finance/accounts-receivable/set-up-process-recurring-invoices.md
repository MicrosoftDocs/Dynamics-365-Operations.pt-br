---
title: Configurar e processar notas ficais recorrentes
description: Este artigo explica como configurar e processar notas fiscais recorrentes. Você pode usar notas fiscais recorrentes se você deve cobrar clientes para a mesma quantidade regularmente.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76dd6b21207b61dfb96e4d9538b5e6ffc1c6b02d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835115"
---
# <a name="set-up-and-process-recurring-invoices"></a><span data-ttu-id="250df-104">Configurar e processar notas ficais recorrentes</span><span class="sxs-lookup"><span data-stu-id="250df-104">Set up and process recurring invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="250df-105">Este artigo explica como configurar e processar notas fiscais recorrentes.</span><span class="sxs-lookup"><span data-stu-id="250df-105">This article explains how to set up and process recurring invoices.</span></span> <span data-ttu-id="250df-106">Você pode usar notas fiscais recorrentes se você deve cobrar clientes para a mesma quantidade regularmente.</span><span class="sxs-lookup"><span data-stu-id="250df-106">You can use recurring invoices if you must invoice customers for the same amount on a regular basis.</span></span>

<a name="create-a-recurring-free-text-invoice-template"></a><span data-ttu-id="250df-107">Criar um modelo de fatura de texto livre recorrente</span><span class="sxs-lookup"><span data-stu-id="250df-107">Create a recurring free text invoice template</span></span>
---------------------------------------------

<span data-ttu-id="250df-108">Para cobrar clientes sobre os mesmos serviços regularmente, você deve definir um modelo de fatura de texto livre que pode ser reutilizado para criar faturas.</span><span class="sxs-lookup"><span data-stu-id="250df-108">To invoice customers for the same services on a regular basis, you must define a free text invoice template that can be reused to create the invoices.</span></span> <span data-ttu-id="250df-109">Este modelo contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="250df-109">This template contains the following information:</span></span>

-   <span data-ttu-id="250df-110">Informações do cabeçalho, como grupos de impostos, termos de pagamentos e métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="250df-110">Header information, such as tax groups, terms of payment, and the method of payment</span></span>
-   <span data-ttu-id="250df-111">Informações da linha, como descrição do serviço, contas da receita, preço unitário e valor da fatura</span><span class="sxs-lookup"><span data-stu-id="250df-111">Line information, such as the service description, revenue accounts, unit price, and invoice amount</span></span>
-   <span data-ttu-id="250df-112">Encargos de envio e manipulação</span><span class="sxs-lookup"><span data-stu-id="250df-112">Charges for shipping or handling</span></span>
-   <span data-ttu-id="250df-113">Distribuições contábeis com informações de dimensão financeira, como centros de custo e unidades de negócios</span><span class="sxs-lookup"><span data-stu-id="250df-113">Accounting distributions together with financial dimension information, such as cost centers and business units</span></span>

<span data-ttu-id="250df-114">Na verdade, você está criando uma fatura e inteira e salvando como modelo.</span><span class="sxs-lookup"><span data-stu-id="250df-114">In effect, you're creating an entire invoice and saving it as a template.</span></span> <span data-ttu-id="250df-115">Você pode configurar o modelos usando a página **Faturas recorrentes**.</span><span class="sxs-lookup"><span data-stu-id="250df-115">You can set up the templates using the **Recurring invoices** page.</span></span>

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a><span data-ttu-id="250df-116">Atribuir um modelo de fatura de texto livre para um cliente e inserir os detalhes de recorrência</span><span class="sxs-lookup"><span data-stu-id="250df-116">Assign a free text invoice template to a customer and enter recurrence details</span></span>
<span data-ttu-id="250df-117">Depois que o modelo é criado, você deve atribuir o modelo aos clientes que você deseja cobrar.</span><span class="sxs-lookup"><span data-stu-id="250df-117">After the template is created, you must assign the template to the customers that you want to invoice.</span></span> <span data-ttu-id="250df-118">Além disso, você deve especificar quando e como a fatura será usada.</span><span class="sxs-lookup"><span data-stu-id="250df-118">Additionally, you must specify when and how often the invoice will be used.</span></span> <span data-ttu-id="250df-119">Você pode atribuir os modelos na guia **fatura** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="250df-119">You can assign the templates on the **Invoice** tab of the **Customers** page.</span></span> <span data-ttu-id="250df-120">Adicione o modelo à lista e atualize as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="250df-120">Add the template to the list, and update the following information:</span></span>

-   <span data-ttu-id="250df-121">A data de início e, opcionalmente, a data final para a cobrança recorrente</span><span class="sxs-lookup"><span data-stu-id="250df-121">The start date and, optionally, the end date for the recurring billing</span></span>
-   <span data-ttu-id="250df-122">A frequência de faturamento recorrente (por exemplo, cada dia ou uma vez por mês)</span><span class="sxs-lookup"><span data-stu-id="250df-122">The frequency of the recurring billing (for example, every day or once a month)</span></span>
-   <span data-ttu-id="250df-123">O valor máximo de cobrança (se essa informação for necessária)</span><span class="sxs-lookup"><span data-stu-id="250df-123">The maximum billing amount (if this information is required)</span></span>

<span data-ttu-id="250df-124">Um cliente pode ter vários modelos que têm frequências diferentes.</span><span class="sxs-lookup"><span data-stu-id="250df-124">A customer can have multiple templates that have different frequencies.</span></span>

## <a name="generate-the-recurring-invoices"></a><span data-ttu-id="250df-125">Gerar as faturas recorrentes</span><span class="sxs-lookup"><span data-stu-id="250df-125">Generate the recurring invoices</span></span>
<span data-ttu-id="250df-126">Na página **Faturas recorrentes**, há uma tarefa que processa modelos da fatura recorrente.</span><span class="sxs-lookup"><span data-stu-id="250df-126">On the **Recurring invoices** page, there is a task that processes recurring invoice templates.</span></span> <span data-ttu-id="250df-127">Especifique a data da fatura e o modelo para gerar faturas.</span><span class="sxs-lookup"><span data-stu-id="250df-127">You specify the invoice date and the template to generate the invoices from.</span></span> <span data-ttu-id="250df-128">As faturas serão geradas e atribuídas a um único número de identificação de recorrência para cada grupo de faturas que é processado.</span><span class="sxs-lookup"><span data-stu-id="250df-128">Invoices will be generated and assigned a single recurrence ID number for each group of invoices that is processed.</span></span>

<a name="post-recurring-free-text-invoices"></a><span data-ttu-id="250df-129">Lançar faturas de texto livre recorrentes</span><span class="sxs-lookup"><span data-stu-id="250df-129">Post recurring free text invoices</span></span>
---------------------------------

<span data-ttu-id="250df-130">Depois que as faturas recorrentes são geradas, as IDs de recorrência da fatura aparecem em uma tarefa de lançamentos na página **Faturas recorrentes**.</span><span class="sxs-lookup"><span data-stu-id="250df-130">After recurring invoices are generated, the invoice recurrence IDs appear in a posting task on the **Recurring invoices** page.</span></span> <span data-ttu-id="250df-131">Você pode exibir todas as faturas para um ID de recorrência se você clicar no link.</span><span class="sxs-lookup"><span data-stu-id="250df-131">You can view all of the invoices for a recurrence ID by clicking the link.</span></span> <span data-ttu-id="250df-132">Durante a revisão de faturas para o ID de recorrência, você pode excluir faturas individuais.</span><span class="sxs-lookup"><span data-stu-id="250df-132">During your review of the invoices for the recurrence ID, you can delete individual invoices.</span></span> <span data-ttu-id="250df-133">As configurações de recorrência do cliente serão redefinidas para esse modelo, de modo que possa ser gerado novamente depois.</span><span class="sxs-lookup"><span data-stu-id="250df-133">The customer's recurrence settings will be reset for that template, so that it can be regenerated later.</span></span> <span data-ttu-id="250df-134">Você pode lançar uma, muitas ou todas as faturas para uma ID de recorrência.</span><span class="sxs-lookup"><span data-stu-id="250df-134">You can post one, many, or all of the invoices for a recurrence ID.</span></span> <span data-ttu-id="250df-135">Se os fluxos de trabalho estiverem habilitados, você deverá clicar em **Enviar** antes de lançar as faturas.</span><span class="sxs-lookup"><span data-stu-id="250df-135">If workflows are enabled, you must click **Submit** before you can post the invoices.</span></span>

<a name="print-recurring-free-text-invoices"></a><span data-ttu-id="250df-136">Imprimir faturas de texto livre recorrentes</span><span class="sxs-lookup"><span data-stu-id="250df-136">Print recurring free text invoices</span></span>
----------------------------------

<span data-ttu-id="250df-137">Depois que as faturas recorrentes são lançadas, você pode imprimir as faturas da página de listagem de faturas de texto livre.</span><span class="sxs-lookup"><span data-stu-id="250df-137">After recurring invoices are posted, you can print the invoices from the free text invoice list page.</span></span> <span data-ttu-id="250df-138">Você pode imprimir as faturas selecionadas ou pode selecionar um intervalo de faturas para imprimir.</span><span class="sxs-lookup"><span data-stu-id="250df-138">You can print the invoices that are selected, or you can select a range of invoices to print.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]