---
title: Especificar a taxa cruzada
description: Este tópico fornece informações sobre taxas cruzadas no Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146794557a3a6ba1801598fe6b814e209d9f5fc6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440194"
---
# <a name="specify-the-cross-rate"></a><span data-ttu-id="6f0ec-103">Especificar a taxa cruzada</span><span class="sxs-lookup"><span data-stu-id="6f0ec-103">Specify the cross rate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f0ec-104">Este tópico explica a finalidade de uma taxa cruzada, e como especificar a taxa cruzada ao liquidar um pagamento com uma fatura.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-104">This topic explains the purpose of a cross rate, and how to specify the cross rate when you settle a payment with an invoice.</span></span> <span data-ttu-id="6f0ec-105">Use uma taxa cruzada quando todos os critérios a seguir se aplicarem:</span><span class="sxs-lookup"><span data-stu-id="6f0ec-105">Use a cross rate when all of the following criteria apply:</span></span> 
-   <span data-ttu-id="6f0ec-106">Você está liquidando um pagamento com uma fatura.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-106">You are settling a payment with an invoice.</span></span> 
-   <span data-ttu-id="6f0ec-107">A linha de pagamento e a linha da fatura usam moedas diferentes.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-107">The payment line and the invoice line use different currencies.</span></span> 
-   <span data-ttu-id="6f0ec-108">Nenhuma das duas é a moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-108">Neither currency is the accounting currency.</span></span> 

<span data-ttu-id="6f0ec-109">A taxa cruzada não é usada para calcular a conversão da moeda de transação de pagamento na moeda contábil de pagamento.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-109">The cross rate is not used to calculate the payment transaction currency translation to the payment accounting currency.</span></span> <span data-ttu-id="6f0ec-110">Em vez disso, as taxas de câmbio das tabelas de taxa de câmbio são recuperadas para calcular o valor monetário da transação de pagamento e o valor monetário contábil de pagamento.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-110">Instead, the exchange rates from the exchange rate tables are retrieved to calculate the value of the payment transaction currency amount and the payment accounting currency amount.</span></span> 

<span data-ttu-id="6f0ec-111">Por exemplo, a moeda contábil é USD, a moeda da fatura é CAD e a moeda do pagamento é EUR.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-111">For example, the accounting currency is USD, the invoice currency is CAD, and the payment currency is EUR.</span></span> <span data-ttu-id="6f0ec-112">A taxa cruzada permite que você insira uma taxa de câmbio para traduzir diretamente entre CAD e EUR, e não seja preciso traduzir USD.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-112">The cross rate lets you enter an exchange rate to translate directly between CAD and EUR, and not have to translate through USD.</span></span> <span data-ttu-id="6f0ec-113">Ao selecionar uma nota fiscal e um pagamento principal, você poderá inserir uma taxa cruzada para a linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-113">When you select an invoice and a primary payment, you can enter a cross rate for the invoice line.</span></span> <span data-ttu-id="6f0ec-114">A taxa cruzada é a taxa de câmbio entre as moedas para as transações, a partir da data de liquidação.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-114">The cross rate is the exchange rate between the currencies for those transactions, as of the settlement date.</span></span>

1.  <span data-ttu-id="6f0ec-115">Vá para uma das seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="6f0ec-115">Go to one of the following pages:</span></span>
- <span data-ttu-id="6f0ec-116">**Contas a receber > Comum > Clientes > Todos os clientes**</span><span class="sxs-lookup"><span data-stu-id="6f0ec-116">**Accounts receivable > Common > Customers > All customers**</span></span> 
- <span data-ttu-id="6f0ec-117">**Contas a pagar > Comum > Fornecedores > Todos os fornecedores**</span><span class="sxs-lookup"><span data-stu-id="6f0ec-117">**Accounts payable > Common > Vendors > All vendors**</span></span> 
- <span data-ttu-id="6f0ec-118">**Compras > Comum > Fornecedores > Todos os fornecedores**</span><span class="sxs-lookup"><span data-stu-id="6f0ec-118">**Procurement and sourcing > Common > Vendors > All vendors**</span></span>
2.  <span data-ttu-id="6f0ec-119">Selecione o cliente ou o fornecedor cujas transações abertas você está liquidando.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-119">Select the customer or vendor whose open transactions you are settling.</span></span> 
3.  <span data-ttu-id="6f0ec-120">Para um cliente, na página de listagem **Todos os clientes**, vá para **Coletar > Liquidar transações abertas**.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-120">For a customer, on the **All customers** list page, go to **Collect > Settle open transactions**.</span></span> <span data-ttu-id="6f0ec-121">Para um fornecedor, na página de listagem **Todos os fornecedores**, vá para **Fatura > Liquidar transações abertas**.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-121">For a vendor, on the **All vendors** list page, go to **Invoice > Settle open transactions**.</span></span> 
4.  <span data-ttu-id="6f0ec-122">Selecione a transação que é o pagamento principal e clique em **Marcar pagamento**.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-122">Select the transaction that is the primary payment, and then click **Mark payment**.</span></span> <span data-ttu-id="6f0ec-123">A caixa de seleção na coluna **Marcar** será marcada e um ícone de informações aparecerá na coluna **Pagamento principal**.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-123">The check box in the **Mark** column is selected, and an information icon is shown in the **Primary payment** column.</span></span> 
5.  <span data-ttu-id="6f0ec-124">No campo **Taxa cruzada**, insira a taxa de câmbio entre a moeda da fatura e a moeda do pagamento, a partir da data de liquidação.</span><span class="sxs-lookup"><span data-stu-id="6f0ec-124">In the **Cross rate** field, enter the exchange rate between the invoice currency and the payment currency, as of the settlement date.</span></span> 
