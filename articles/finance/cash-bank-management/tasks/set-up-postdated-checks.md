---
title: Configurar cheques pré-datados
description: Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d4afd74f9a0f9018629fa92ab6595bfa94f973
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026196"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="ca547-103">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="ca547-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca547-104">Este tópico explica como especificar se deseja lançar entradas de diário para cheques pré-datados e quais diários de lançamento a serem usados para limpar as entradas e os pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ca547-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="ca547-105">Também é possível especificar as contas de compensação para cheques emitidos, cheques recebidos, e a retenção de imposto.</span><span class="sxs-lookup"><span data-stu-id="ca547-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="ca547-106">Cheques pré-datados que são emitidos com a finalidade de realizar e receber pagamentos em uma data futura.</span><span class="sxs-lookup"><span data-stu-id="ca547-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="ca547-107">É possível especificar se o cheque deve ser refletido nos registros de contabilidade antes da data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="ca547-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="ca547-108">A função deste procedimento é Tesoureiro.</span><span class="sxs-lookup"><span data-stu-id="ca547-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="ca547-109">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="ca547-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="ca547-110">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="ca547-110">Set up postdated checks</span></span>
1. <span data-ttu-id="ca547-111">Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.</span><span class="sxs-lookup"><span data-stu-id="ca547-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="ca547-112">Clique na aba Cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="ca547-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="ca547-113">Marque ou desmarque a caixa de seleção Habilitar cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="ca547-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="ca547-114">Marque ou desmarque a caixa de seleção Lançar entradas de diário para cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="ca547-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="ca547-115">No campo Conta de compensação para cheques emitidos, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="ca547-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="ca547-116">No campo Conta de compensação para cheques recebidos, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="ca547-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="ca547-117">No campo Diário geral para entradas de compensação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ca547-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="ca547-118">No campo Transferir cheques pré-datados para este diário de pagamento de fornecedor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ca547-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="ca547-119">No campo Conta de compensação de imposto retido na fonte, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="ca547-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="ca547-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ca547-120">Click Save.</span></span>
11. <span data-ttu-id="ca547-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ca547-121">Close the page.</span></span>
12. <span data-ttu-id="ca547-122">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="ca547-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="ca547-123">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ca547-123">Click New.</span></span>
14. <span data-ttu-id="ca547-124">No campo Método de pagamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ca547-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="ca547-125">Selecione a opção de lançamento Compensação de cheque pré-datado para indicar que o valor do cheque está lançado em uma conta de compensação.</span><span class="sxs-lookup"><span data-stu-id="ca547-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="ca547-126">No campo Tipo de conta, selecione 'Banco'.</span><span class="sxs-lookup"><span data-stu-id="ca547-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="ca547-127">A conta de contrapartida do método de pagamento será um banco.</span><span class="sxs-lookup"><span data-stu-id="ca547-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="ca547-128">No campo Conta de pagamento, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="ca547-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="ca547-129">Selecione a conta bancária utilizada para deduzir o valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="ca547-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="ca547-130">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ca547-130">Click Save.</span></span>
19. <span data-ttu-id="ca547-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ca547-131">Close the page.</span></span>
> [!NOTE]
> <span data-ttu-id="ca547-132">Para conseguir postar um cheque prédatado para uma conta bancária quando a data da sessão for superior ou igual à data de vencimento, você deve habilitar o recurso **Validação de data de validade do diário de pagamento de postagem com cheques prédatados para a conta bancária**.</span><span class="sxs-lookup"><span data-stu-id="ca547-132">To be able to post a postdated check to a bank account when the session date is greater than or equal to the maturity date, you must enable the feature **Maturity date validation of posting payment journal with postdated checks to bank account**.</span></span> <span data-ttu-id="ca547-133">Este recurso permite que você poste diários de pagamento para fornecedores ou clientes com cheques prédatados, quando a data da sessão for superior ou igual à data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="ca547-133">This feature allows you to post payment journals for vendors or customers with postdated checks, when the session date is greater than or equal to the maturity date.</span></span>
> 
> <span data-ttu-id="ca547-134">Ao configurar o **Método de pagamento** (**Contas a pagar > Configuração de pagamento > Métodos de pagamento**), não preencha **Conta de ponte**.</span><span class="sxs-lookup"><span data-stu-id="ca547-134">When setting the **Method of payment** (**Accounts payable > Payment setup > Methods of payment**), do not fill in **Bridging account**.</span></span> <span data-ttu-id="ca547-135">Nesse caso, a conta de compensação é preenchida com a conta bancária, que é configurada no **Método de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="ca547-135">In this case, the offset account is filled in with the bank account, which is set up in the **Method of payment**.</span></span>
>  
> <span data-ttu-id="ca547-136">Quando o recurso é habilitado e a data da sessão é inferior à data de vencimento, a seguinte mensagem de erro é exibida ao postar um diário de pagamento, "A data de vencimento deve ser inferior ou igual à data da sessão se o tipo de conta de compensação for Banco".</span><span class="sxs-lookup"><span data-stu-id="ca547-136">When the feature is enabled and the session date is less than the maturity date, the following error message is displayed when posting a payment journal, "Maturity date must be less or equal to the session date if offset account type is Bank".</span></span> <span data-ttu-id="ca547-137">Se o recurso não estiver habilitado, você pode postar um diário de pagamento com um cheque prédatado quando a data da sessão for inferior à data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="ca547-137">If the feature is not enabled, you can post a payment journal with a postdated check when the session date is less than the maturity date.</span></span>    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
