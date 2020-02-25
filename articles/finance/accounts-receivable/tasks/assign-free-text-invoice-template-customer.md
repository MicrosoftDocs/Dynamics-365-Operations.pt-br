---
title: Atribuir um modelo de fatura de texto livre a um cliente
description: Essa tarefa demonstra como atribuir um modelo de nota fiscal de texto livre a um cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9c64a00a839522ea14fc5fcdaca08ab17748f894
ms.sourcegitcommit: 9168621ca9b5061c65f3e05dbc5918b6a11d53d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2020
ms.locfileid: "3000015"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="8fd51-103">Atribuir um modelo de fatura de texto livre a um cliente</span><span class="sxs-lookup"><span data-stu-id="8fd51-103">Assign a free text invoice template to a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8fd51-104">Essa tarefa demonstra como atribuir um modelo de nota fiscal de texto livre a um cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="8fd51-105">Esta tarefa usa a empresa de demonstração USMF e é direcionada para o usuário responsável por gerenciar e processar faturas A/R.</span><span class="sxs-lookup"><span data-stu-id="8fd51-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="8fd51-106">No **Painel de Navegação**, vá para **Módulos > Contas a receber > Clientes > Todos os clientes**.</span><span class="sxs-lookup"><span data-stu-id="8fd51-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="8fd51-107">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="8fd51-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8fd51-108">No **Painel de Ações**, clique em **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="8fd51-108">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="8fd51-109">Clique em **Faturas recorrentes**.</span><span class="sxs-lookup"><span data-stu-id="8fd51-109">Click **Recurring invoices**.</span></span> <span data-ttu-id="8fd51-110">Use esta página para atribuir modelos de fatura de texto livre para clientes e especificar quão frequentemente as faturas serão enviadas ao cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="8fd51-111">Clique em **Novo** para atribuir um novo modelo ao cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-111">Click **New** to assign a new template to the customer.</span></span>
6. <span data-ttu-id="8fd51-112">No campo **Modelo**, selecione o modelo de fatura de texto livre que você deseja atribuir ao cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-112">In the **Template** field, select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="8fd51-113">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="8fd51-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8fd51-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8fd51-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8fd51-115">No campo **Data de início de faturamento**, insira a data em que a primeira fatura será gerada.</span><span class="sxs-lookup"><span data-stu-id="8fd51-115">In the **Billing start date** field, enter the date when the first invoice will be generated.</span></span>
10. <span data-ttu-id="8fd51-116">Na seção **Final da recorrência**, insira uma data final recorrente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-116">In the **Recurrence end** section, enter a recurring end date.</span></span>  
    * <span data-ttu-id="8fd51-117">Selecione uma das seguintes opções: Nenhuma data final – as notas fiscais serão geradas indefinidamente até que o modelo seja removido da conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>
    * <span data-ttu-id="8fd51-118">Data de término da cobrança - Selecione esta opção e insira a última data em que a fatura pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="8fd51-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
11. <span data-ttu-id="8fd51-119">No campo **Valor cumulativo máximo**, insira o valor cumulativo máximo após o qual a geração da fatura será interrompida.</span><span class="sxs-lookup"><span data-stu-id="8fd51-119">In the **Maximum cummulative amount** field, enter the maximum cumulative amount after which invoice generation will stop.</span></span> <span data-ttu-id="8fd51-120">Insira o valor cumulativo máximo que pode ser alcançado usando o modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8fd51-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="8fd51-121">Por exemplo, se você inserir 1.000,00 e gerar notas fiscais mensais para cada 100,00, as notas fiscais encerrarão a produção após a décima nota fiscal gerada.</span><span class="sxs-lookup"><span data-stu-id="8fd51-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
12. <span data-ttu-id="8fd51-122">Na seção **Gerar faturas recorrentes usando os valores padrão de**, selecione o modelo de fatura de texto livre ou a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-122">In the **Generate recurring invoices by using the default values from** section, select either free text invoice template or the customer account.</span></span> <span data-ttu-id="8fd51-123">Opte por usar o modelo de fatura de texto livre ou a conta do cliente para determinar os valores padrão para o idioma, o perfil de lançamentos, o grupo de impostos, o grupo de impostos do item, o código de lista, o país/região para entrega, a moeda, as condições de pagamento, o método de pagamento, as especificações de pagamento, o plano de pagamento, o desconto à vista, as dimensões financeiras e a guia de transferência de dinheiro por débito direto quando as faturas são criadas.</span><span class="sxs-lookup"><span data-stu-id="8fd51-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
13. <span data-ttu-id="8fd51-124">No campo **Padrão de recorrência**, selecione o padrão de recorrência.</span><span class="sxs-lookup"><span data-stu-id="8fd51-124">In the **Recurrence pattern** field, select the recurrence pattern.</span></span>
    + <span data-ttu-id="8fd51-125">Diário – Escolha esta opção e insira o número de dias no campo Por.</span><span class="sxs-lookup"><span data-stu-id="8fd51-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="8fd51-126">Por exemplo, se você inserir 15, uma fatura será gerada a cada 15 dias para esse cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>
    + <span data-ttu-id="8fd51-127">Semanal - Escolha essa opção e insira o número de semanas no campo Por.</span><span class="sxs-lookup"><span data-stu-id="8fd51-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="8fd51-128">Por exemplo, se você inserir 2, uma fatura será gerada a cada duas semanas para esse cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>
    + <span data-ttu-id="8fd51-129">Mensal - Escolha essa opção e insira o número de meses no campo Por.</span><span class="sxs-lookup"><span data-stu-id="8fd51-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="8fd51-130">Por exemplo, se você inserir 6, uma fatura será gerada a cada seis meses para esse cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>
    + <span data-ttu-id="8fd51-131">Anual - Escolha essa opção e insira o número de anos no campo Por.</span><span class="sxs-lookup"><span data-stu-id="8fd51-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="8fd51-132">Por exemplo, se você inserir 2, uma fatura será gerada a cada dois anos para esse cliente.</span><span class="sxs-lookup"><span data-stu-id="8fd51-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
14. <span data-ttu-id="8fd51-133">No campo **Por**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8fd51-133">In the **Per** field, enter a number.</span></span>

