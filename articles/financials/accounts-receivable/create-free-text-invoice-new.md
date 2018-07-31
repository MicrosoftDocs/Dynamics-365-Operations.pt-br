--- 
title: Criar uma fatura de texto livre
description: Este artigo demonstra como criar uma fatura de texto livre.
author: mikefalkner
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f69505f0c6137121cae92d42d052b244326c8436
ms.openlocfilehash: 2a611bdd4dd97109709ed355eb80471e27413744
ms.contentlocale: pt-br
ms.lasthandoff: 06/28/2018

---

# <a name="create-a-free-text-invoice"></a><span data-ttu-id="f7379-103">Criar uma fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="f7379-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7379-104">Este artigo demonstra como criar uma fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="f7379-104">This article demonstrates how to create a free text invoice.</span></span> <span data-ttu-id="f7379-105">Para este procedimento, use a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="f7379-105">For this procedure, use the USMF demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="f7379-106">Criar uma fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="f7379-106">Create a free text invoice</span></span>

1. <span data-ttu-id="f7379-107">Vá para Contas recebíveis > Faturas > Todas faturas de texto livre.</span><span class="sxs-lookup"><span data-stu-id="f7379-107">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="f7379-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f7379-108">Click New.</span></span>
3. <span data-ttu-id="f7379-109">No campo Conta de cliente, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f7379-109">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="f7379-110">A conta de fatura usará como padrão a mesma conta usada para a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="f7379-110">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="f7379-111">O status contábil inicia com Em processo se a fatura não for lançada.</span><span class="sxs-lookup"><span data-stu-id="f7379-111">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="f7379-112">O número da fatura será atribuído quando ela for lançada.</span><span class="sxs-lookup"><span data-stu-id="f7379-112">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="f7379-113">Se você estiver usando cartas de ordem de SEPA, a carta da ordem de débito direto será preenchida automaticamente com uma carta da ordem quando você selecionar a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="f7379-113">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="f7379-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7379-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f7379-115">No campo de conta principal, especifique um número de conta sem dimensões.</span><span class="sxs-lookup"><span data-stu-id="f7379-115">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="f7379-116">Você também pode inserir um ou mais caracteres para a conta principal e usar a pesquisa para localizar a conta.</span><span class="sxs-lookup"><span data-stu-id="f7379-116">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="f7379-117">Insira dimensões posteriormente neste guia.</span><span class="sxs-lookup"><span data-stu-id="f7379-117">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="f7379-118">Expanda a guia rápida Detalhes da linha para poder adicionar dimensões à sua conta principal.</span><span class="sxs-lookup"><span data-stu-id="f7379-118">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="f7379-119">Clique na guia Linha de dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="f7379-119">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="f7379-120">As dimensões são somente para a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f7379-120">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="f7379-121">O grupo de impostos sobre vendas é preenchido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="f7379-121">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="f7379-122">Se o cliente não tiver um grupo de impostos sobre vendas, o grupo de impostos sobre vendas da conta principal será usado.</span><span class="sxs-lookup"><span data-stu-id="f7379-122">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="f7379-123">O grupo de impostos dos itens é preenchido pela conta principal.</span><span class="sxs-lookup"><span data-stu-id="f7379-123">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="f7379-124">Se a conta principal não tiver um grupo de impostos do item, será usado o grupo de impostos do item nos parâmetros de impostos da Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="f7379-124">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="f7379-125">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f7379-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="f7379-126">A quantidade é opcional.</span><span class="sxs-lookup"><span data-stu-id="f7379-126">The quantity is optional.</span></span>  
9. <span data-ttu-id="f7379-127">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f7379-127">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="f7379-128">O preço unitário é opcional.</span><span class="sxs-lookup"><span data-stu-id="f7379-128">The unit price is optional.</span></span>  
    * <span data-ttu-id="f7379-129">O valor é calculado como a quantidade vezes o preço unitário.</span><span class="sxs-lookup"><span data-stu-id="f7379-129">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="f7379-130">No entanto, você pode substituir o cálculo e inserir um valor.</span><span class="sxs-lookup"><span data-stu-id="f7379-130">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="f7379-131">Clique em Imposto para ver os impostos calculados para sua fatura.</span><span class="sxs-lookup"><span data-stu-id="f7379-131">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="f7379-132">Exiba os valores dos impostos nesta página ou substitua os valores na guia Ajuste.</span><span class="sxs-lookup"><span data-stu-id="f7379-132">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="f7379-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f7379-133">Click OK.</span></span>
12. <span data-ttu-id="f7379-134">Clique em Encargos para adicionar um encargo a sua fatura.</span><span class="sxs-lookup"><span data-stu-id="f7379-134">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="f7379-135">No campo Código de encargo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7379-135">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="f7379-136">No campo Valor de encargo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f7379-136">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="f7379-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f7379-137">Close the page.</span></span>
16. <span data-ttu-id="f7379-138">Clique em Totais para ver o resumo dos detalhes da fatura e os totais.</span><span class="sxs-lookup"><span data-stu-id="f7379-138">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="f7379-139">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="f7379-139">Click Close.</span></span>
18. <span data-ttu-id="f7379-140">Clique em Lançar para lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="f7379-140">Click Post to post the invoice.</span></span> <span data-ttu-id="f7379-141">É possível cancelar antes de lançar.</span><span class="sxs-lookup"><span data-stu-id="f7379-141">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="f7379-142">Para alterar o cronograma de impressão de faturas: selecione Atual para imprimir cada fatura conforme elas são atualizadas ou selecione Depois para imprimir depois de todas as faturas serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f7379-142">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="f7379-143">Se desejar alterar como o limite de crédito do cliente será verificado antes de lançar, altere o tipo de limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="f7379-143">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="f7379-144">Se desejar imprimir a fatura, selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="f7379-144">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="f7379-145">Se desejar lançar a fatura, selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="f7379-145">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="f7379-146">Você pode imprimir a nota fiscal sem lançá-las.</span><span class="sxs-lookup"><span data-stu-id="f7379-146">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="f7379-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f7379-147">Click OK.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="f7379-148">Copiar linhas</span><span class="sxs-lookup"><span data-stu-id="f7379-148">Copy lines</span></span>
<span data-ttu-id="f7379-149">Para copiar linhas na fatura de texto livre, selecione uma ou mais linhas e clique em Copiar linhas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="f7379-149">To copy lines on the free text invoice, select one or more lines and then click Copy selected lines.</span></span> <span data-ttu-id="f7379-150">Você pode especificar o número de cópias que deseja fazer e também pode copiar observações e anexos.</span><span class="sxs-lookup"><span data-stu-id="f7379-150">You can specify the number of copies that you want to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="f7379-151">Você pode copiar as distribuições ou permitir que sejam recriadas quando fizer o lançamento.</span><span class="sxs-lookup"><span data-stu-id="f7379-151">You can copy the distributions or allow them to be recreated when you post.</span></span> <span data-ttu-id="f7379-152">Depois de copiar as linhas, você poderá editar as informações conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f7379-152">Once you copy the lines, you can edit the information as needed.</span></span> 

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="f7379-153">Criar uma fatura de texto livre a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="f7379-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="f7379-154">Você pode criar uma fatura de texto livre a partir de um modelo.</span><span class="sxs-lookup"><span data-stu-id="f7379-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="f7379-155">Quando selecionar Novo a partir do modelo na guia Fatura, selecione um nome de modelo e a conta do cliente para nova fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="f7379-155">When you select New from template from the Invoice tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="f7379-156">Você também pode escolher os valores padrão, como as condições de pagamento e método de pagamento do cliente, ou usar os valores que foram salvos com o modelo.</span><span class="sxs-lookup"><span data-stu-id="f7379-156">You can also choose to default values such as the terms of payment and method of payment from the customer or use the values that were saved with the template.</span></span> <span data-ttu-id="f7379-157">Uma nova fatura de texto livre será criada e você poderá editar os valores nela.</span><span class="sxs-lookup"><span data-stu-id="f7379-157">A new free text invoice will be created and you can edit the values in that invoice.</span></span> 


