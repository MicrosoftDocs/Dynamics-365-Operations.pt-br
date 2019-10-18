---
title: Configurar cheques pré-datados
description: Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 035f6e3b0268f8ee4c9006ca5f0527133cf2771c
ms.sourcegitcommit: 69f8233e86b32347474a25d83b4ac5920f60407d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "2538469"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="76a75-103">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="76a75-103">Set up postdated checks</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76a75-104">Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="76a75-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="76a75-105">Também é possível especificar as contas de compensação para cheques emitidos, cheques recebidos, e a retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="76a75-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="76a75-106">Cheques pré-datados que são emitidos com a finalidade de realizar e receber pagamentos em uma data futura.</span><span class="sxs-lookup"><span data-stu-id="76a75-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="76a75-107">É possível especificar se o cheque deve ser refletido nos registros de contabilidade antes da data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="76a75-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="76a75-108">A função deste procedimento é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="76a75-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="76a75-109">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="76a75-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="76a75-110">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="76a75-110">Set up postdated checks</span></span>
1. <span data-ttu-id="76a75-111">Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.</span><span class="sxs-lookup"><span data-stu-id="76a75-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="76a75-112">Clique na aba Cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="76a75-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="76a75-113">Marque ou desmarque a caixa de seleção Habilitar cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="76a75-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="76a75-114">Marque ou desmarque a caixa de seleção Lançar entradas de diário para cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="76a75-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="76a75-115">No campo Conta de compensação para cheques emitidos, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="76a75-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="76a75-116">No campo Conta de compensação para cheques recebidos, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="76a75-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="76a75-117">No campo Diário geral para entradas de compensação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76a75-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="76a75-118">No campo Transferir cheques pré-datados para este diário de pagamento de fornecedor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76a75-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="76a75-119">No campo Conta de compensação de imposto retido na fonte, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="76a75-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="76a75-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76a75-120">Click Save.</span></span>
11. <span data-ttu-id="76a75-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76a75-121">Close the page.</span></span>
12. <span data-ttu-id="76a75-122">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="76a75-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="76a75-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="76a75-123">Click New.</span></span>
14. <span data-ttu-id="76a75-124">No campo Método de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76a75-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="76a75-125">Selecione a opção de lançamento Compensação de cheque pré-datado para indicar que o valor do cheque está lançado em uma conta de compensação.</span><span class="sxs-lookup"><span data-stu-id="76a75-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="76a75-126">No campo Tipo de conta, selecione 'Banco'.</span><span class="sxs-lookup"><span data-stu-id="76a75-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="76a75-127">A conta de contrapartida do método de pagamento será um banco.</span><span class="sxs-lookup"><span data-stu-id="76a75-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="76a75-128">No campo Conta de pagamento, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="76a75-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="76a75-129">Selecione a conta bancária utilizada para deduzir o valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="76a75-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="76a75-130">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76a75-130">Click Save.</span></span>
19. <span data-ttu-id="76a75-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76a75-131">Close the page.</span></span>

