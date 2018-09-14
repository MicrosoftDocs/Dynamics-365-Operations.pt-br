--- 
title: "Configurar clientes e contas bancárias de cliente para débitos diretos de ISO20022"
description: "Essa tarefa orienta como configurar uma conta bancária do cliente e uma carta de ordem de débito direto do cliente que são necessárias para gerar o arquivo de pagamento do cliente, como o débito direto ISO20022."
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e7d7d79b1d496223b027d800beca105ecaa0bd4c
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="c0ba0-103">Configurar clientes e contas bancárias de cliente para débitos diretos de ISO20022</span><span class="sxs-lookup"><span data-stu-id="c0ba0-103">Set up customers and customer bank accounts for ISO20022 direct debits</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c0ba0-104">Essa tarefa orienta como configurar uma conta bancária do cliente e uma carta de ordem de débito direto do cliente que são necessárias para gerar o arquivo de pagamento do cliente, como o débito direto ISO20022.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-104">This task walks you through setting up a customer bank account and a customer direct debit mandate which are required to generate the customer payment file like ISO20022 direct debit.</span></span> <span data-ttu-id="c0ba0-105">Dependendo dos formatos de pagamento de cliente que estiverem configurados, podem ser necessárias informações adicionais de um cliente ou de uma conta bancária do cliente que não estão cobertas neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-105">Depending on the customer payment formats tha are set up, additional information, not covered in this procedure, might be required for a customer or a customer bank account.</span></span> 

<span data-ttu-id="c0ba0-106">Esta tarefa foi criada usando a empresa DEMF de dados de demonstração com uma entidade legal primária na Alemanha.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-106">This task was created using the demo data company DEMF with a legal entity primary address in Germany.</span></span>



<span data-ttu-id="c0ba0-107">Este é o quarto dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-107">This is the fourth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-a-customer-bank-account"></a><span data-ttu-id="c0ba0-108">Configurar uma conta bancária de cliente</span><span class="sxs-lookup"><span data-stu-id="c0ba0-108">Set up a customer bank account</span></span>
1. <span data-ttu-id="c0ba0-109">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-109">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="c0ba0-110">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c0ba0-111">Por exemplo, no campo Conta, filtre com um valor de 'DE-010'.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-111">For example, filter on the Account field with a value of 'DE-010 '.</span></span>
3. <span data-ttu-id="c0ba0-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c0ba0-113">No Painel de Ação, clique em Cliente.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-113">On the Action Pane, click Customer.</span></span>
5. <span data-ttu-id="c0ba0-114">Clique em Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="c0ba0-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-115">Click New.</span></span>
7. <span data-ttu-id="c0ba0-116">No campo Conta bancária, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-116">In the Bank account field, type a value.</span></span>
8. <span data-ttu-id="c0ba0-117">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-117">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c0ba0-118">Por exemplo, insira "EUR bank".</span><span class="sxs-lookup"><span data-stu-id="c0ba0-118">For example, enter 'EUR bank'.</span></span>  
9. <span data-ttu-id="c0ba0-119">No campo Grupos de banco, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-119">In the Bank groups field, enter or select a value.</span></span>
10. <span data-ttu-id="c0ba0-120">No campo IBAN, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-120">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="c0ba0-121">Por exemplo, insira "DE36200400000628808808".</span><span class="sxs-lookup"><span data-stu-id="c0ba0-121">For example, enter 'DE36200400000628808808'.</span></span>  
11. <span data-ttu-id="c0ba0-122">No campo Código SWIFT, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-122">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="c0ba0-123">Por exemplo, insira 'COBADEFFXXX'.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-123">For example: Enter 'COBADEFFXXX'.</span></span>  <span data-ttu-id="c0ba0-124">Observe que o SWIFT\BIC não é obrigatório para vários formatos de pagamento, no entanto, é recomendável registrá-lo em uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-124">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
12. <span data-ttu-id="c0ba0-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-125">Click Save.</span></span>
13. <span data-ttu-id="c0ba0-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-126">Close the page.</span></span>
14. <span data-ttu-id="c0ba0-127">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-127">Click Edit.</span></span>
15. <span data-ttu-id="c0ba0-128">Expanda a seção de padrões de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-128">Expand the Payment defaults section.</span></span>
16. <span data-ttu-id="c0ba0-129">No campo Conta bancária, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-129">In the Bank account field, enter or select a value.</span></span>

## <a name="add-a-direct-debit-mandate"></a><span data-ttu-id="c0ba0-130">Adicionar uma carta de ordem de débito direto</span><span class="sxs-lookup"><span data-stu-id="c0ba0-130">Add a direct debit mandate</span></span>
1. <span data-ttu-id="c0ba0-131">Expanda a seção de cartas da ordem de débito direto.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-131">Expand the Direct debit mandates section.</span></span>
2. <span data-ttu-id="c0ba0-132">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-132">Click Add.</span></span>
3. <span data-ttu-id="c0ba0-133">No campo Conta bancária do credor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-133">In the Creditor bank account field, enter or select a value.</span></span>
    * <span data-ttu-id="c0ba0-134">Por exemplo, selecione DEMF OPER.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-134">For example, select DEMF OPER.</span></span>  
4. <span data-ttu-id="c0ba0-135">No campo Data de assinatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-135">In the Signature date field, enter a date.</span></span>
5. <span data-ttu-id="c0ba0-136">Clique em Sim para confirmar a atualização de data.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-136">Click Yes to confirm the date update.</span></span>
6. <span data-ttu-id="c0ba0-137">No campo Local de assinatura, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-137">In the Signature location field, enter or select a value.</span></span>
7. <span data-ttu-id="c0ba0-138">No campo Número esperado de pagamentos, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-138">In the Expected number of payments field, enter a number.</span></span>
8. <span data-ttu-id="c0ba0-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-139">Click OK.</span></span>
9. <span data-ttu-id="c0ba0-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c0ba0-140">Click Save.</span></span>


