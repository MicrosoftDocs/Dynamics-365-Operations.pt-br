---
title: Registrar e lançar um cheque pré-datado para um cliente
description: É possível registrar os detalhes de um cheque pré-datado recebido de um cliente.
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f27675a2aa2160619bf78eea33bba2ce0b7bd81
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188087"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="5a404-103">Registrar e lançar um cheque pré-datado para um cliente</span><span class="sxs-lookup"><span data-stu-id="5a404-103">Register and post a postdated check for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5a404-104">É possível registrar os detalhes de um cheque pré-datado recebido de um cliente.</span><span class="sxs-lookup"><span data-stu-id="5a404-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="5a404-105">Você também pode lançar o cheque pré-datado e gerar transações financeiras.</span><span class="sxs-lookup"><span data-stu-id="5a404-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="5a404-106">Conclua as seguintes tarefas antes de registrar e lançar um cheque pré-datado recebido de um cliente:  • Configurar cheque pré-datado na página de Gerenciamento de dinheiro e banco • Configurar um método de pagamento para cheques pré-datados   A função para esse procedimento é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="5a404-106">Complete the following tasks before you register and post a postdated check received from a customer:   • Set up postdated check in the Cash and bank management page • Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="5a404-107">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="5a404-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="5a404-108">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="5a404-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="5a404-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5a404-109">Click New.</span></span>
3. <span data-ttu-id="5a404-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5a404-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="5a404-111">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="5a404-111">Click Lines.</span></span>
5. <span data-ttu-id="5a404-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5a404-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="5a404-113">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="5a404-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="5a404-114">No campo Crédito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="5a404-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="5a404-115">Insira o valor especificado pelo cheque pré-datado.</span><span class="sxs-lookup"><span data-stu-id="5a404-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="5a404-116">Clique na aba Pagamento.</span><span class="sxs-lookup"><span data-stu-id="5a404-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="5a404-117">No campo Método de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5a404-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="5a404-118">Selecione o método de pagamento para o cheque pré-datado.</span><span class="sxs-lookup"><span data-stu-id="5a404-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="5a404-119">Clique na aba Cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="5a404-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="5a404-120">No campo Data de vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="5a404-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="5a404-121">Insira a data em que o cheque pré-datado será pago.</span><span class="sxs-lookup"><span data-stu-id="5a404-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="5a404-122">No campo Agência bancária emissora, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5a404-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="5a404-123">Insira os detalhes bancários do cheque pré-datado.</span><span class="sxs-lookup"><span data-stu-id="5a404-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="5a404-124">No campo número do cheque, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5a404-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="5a404-125">No campo Nome do banco emissor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5a404-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="5a404-126">Insira os detalhes bancários do cheque pré-datado.</span><span class="sxs-lookup"><span data-stu-id="5a404-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="5a404-127">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="5a404-127">Click Post.</span></span>
16. <span data-ttu-id="5a404-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5a404-128">Close the page.</span></span>

