---
title: Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022
description: Este procedimento mostra como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamento de fornecedor usando o exemplo de Transferência de Crédito ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1df738e3925dc23e7723d93f33acf6a9d811b113
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964532"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="9f09f-103">Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022</span><span class="sxs-lookup"><span data-stu-id="9f09f-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9f09f-104">Este tópico explica como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamentos do fornecedor usando o exemplo de transferência de crédito ISO2022.</span><span class="sxs-lookup"><span data-stu-id="9f09f-104">This topic explains how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span>

<span data-ttu-id="9f09f-105">Este é o quinto dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9f09f-105">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="9f09f-106">Use os dados de demonstração DEMF para completar este exemplo.</span><span class="sxs-lookup"><span data-stu-id="9f09f-106">Use the DEMF demo data to complete this example.</span></span>

## <a name="example"></a><span data-ttu-id="9f09f-107">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9f09f-107">Example</span></span>

1.    <span data-ttu-id="9f09f-108">Vá para **Contas a pagar > Pagamentos > Diário de pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-108">Go to **Accounts payable > Payments > Payment journal**.</span></span>
2.    <span data-ttu-id="9f09f-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-109">Click **New**.</span></span>
3.    <span data-ttu-id="9f09f-110">No campo **Nome**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9f09f-110">In the **Name** field, enter or select a value.</span></span>
4.    <span data-ttu-id="9f09f-111">Clique em **Linhas > Proposta de pagamento > Criar proposta de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-111">Click **Lines > Payment proposal > Create payment proposal**.</span></span>
5.    <span data-ttu-id="9f09f-112">Expanda a seção **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-112">Expand the **Records to include** section.</span></span>
6.    <span data-ttu-id="9f09f-113">Clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-113">Click **Filter**.</span></span>
7.    <span data-ttu-id="9f09f-114">Na lista, selecione a linha para a **tabela Fornecedores** e o **campo Conta de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-114">In the list, select the row for **Vendors table** and **Vendor account field**.</span></span>
8.    <span data-ttu-id="9f09f-115">No campo **Critérios**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9f09f-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="9f09f-116">Você pode aplicar quaisquer critérios para selecionar transações de fornecedor para pagamento. Neste exemplo, use DE-001 como conta de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="9f09f-116">You can apply any criteria for selecting vendor transactions to pay, for this example, use DE-001 as a vendor account.</span></span>
12.    <span data-ttu-id="9f09f-117">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-117">Click **OK**.</span></span>
13.    <span data-ttu-id="9f09f-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-118">Click **OK**.</span></span>
14.    <span data-ttu-id="9f09f-119">Clique em **Criar pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-119">Click **Create payments**.</span></span>
15. <span data-ttu-id="9f09f-120">Gere um arquivo de pagamento ISO20022.</span><span class="sxs-lookup"><span data-stu-id="9f09f-120">Generate an ISO20022 payment file.</span></span>
    1.    <span data-ttu-id="9f09f-121">Clique em **Gerar pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="9f09f-121">Click **Generate payments**.</span></span>
    2.    <span data-ttu-id="9f09f-122">No campo **Método de pagamento**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9f09f-122">In the **Method of payment** field, enter or select a value.</span></span>
    3.    <span data-ttu-id="9f09f-123">No campo **Nome do arquivo**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9f09f-123">In the **File name** field, type a value.</span></span> <span data-ttu-id="9f09f-124">Por exemplo, devido a um pagamento em euros, o arquivo gerado será compatível com SEPA.</span><span class="sxs-lookup"><span data-stu-id="9f09f-124">For this example, because of the EUR payment, the generated file will be SEPA compliant.</span></span> <span data-ttu-id="9f09f-125">A transferência de crédito ISO20022 e outros formatos de pagamento de fornecedor também podem ser usados para gerar pagamentos em outras moedas.</span><span class="sxs-lookup"><span data-stu-id="9f09f-125">ISO20022 credit transfer as well as other vendor payment formats can also be used for generating payments in other currencies.</span></span>
    4.    <span data-ttu-id="9f09f-126">No campo **Conta bancária**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9f09f-126">In the **Bank account** field, enter or select a value.</span></span>

