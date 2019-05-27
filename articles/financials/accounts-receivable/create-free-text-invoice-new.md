---
title: Criar faturas de texto livre
description: Este tópico explica como criar faturas de texto livre.
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: f6ee6fda0b52b8af7c253b7d22e470345a8a421f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559425"
---
# <a name="create-free-text-invoices"></a><span data-ttu-id="3e893-103">Criar faturas de texto livre</span><span class="sxs-lookup"><span data-stu-id="3e893-103">Create free text invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e893-104">Este tópico explica como criar faturas de texto livre.</span><span class="sxs-lookup"><span data-stu-id="3e893-104">This topic explains how to create free text invoices.</span></span> <span data-ttu-id="3e893-105">Para o procedimento, use a empresa de demonstração **USMF**.</span><span class="sxs-lookup"><span data-stu-id="3e893-105">For the procedure, use the **USMF** demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="3e893-106">Criar uma fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="3e893-106">Create a free text invoice</span></span>

1. <span data-ttu-id="3e893-107">Vá para **Contas recebíveis \> Faturas \> Todas faturas de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="3e893-107">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2. <span data-ttu-id="3e893-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3e893-108">Select **New**.</span></span>
3. <span data-ttu-id="3e893-109">No campo **Conta de cliente**, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3e893-109">In the **Customer account** field, select a value.</span></span>

    * <span data-ttu-id="3e893-110">Por padrão, a conta selecionada como a conta do cliente é usada como a conta da fatura.</span><span class="sxs-lookup"><span data-stu-id="3e893-110">By default, the account that is selected as the customer account is used as the invoice account.</span></span>
    * <span data-ttu-id="3e893-111">Se a fatura não for lançada, o status contábil inicia com **Em processo**.</span><span class="sxs-lookup"><span data-stu-id="3e893-111">If the invoice isn't posted, the accounting status starts with **In process**.</span></span>
    * <span data-ttu-id="3e893-112">O número da fatura será atribuído quando ela for lançada.</span><span class="sxs-lookup"><span data-stu-id="3e893-112">The invoice number will be assigned when the invoice is posted.</span></span>
    * <span data-ttu-id="3e893-113">Se você estiver usando cartas de ordem de Área Única de Pagamentos em Euros (SEPA), a carta da ordem de débito direto será inserida automaticamente quando você selecionar a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="3e893-113">If you're using Single Euro Payments Area (SEPA) mandates, the direct debit mandate is automatically entered when you select the customer account.</span></span>

4. <span data-ttu-id="3e893-114">No campo **Descrição**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="3e893-114">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="3e893-115">No campo **Conta principal**, especifique um número de conta sem dimensões.</span><span class="sxs-lookup"><span data-stu-id="3e893-115">In the **Main account** field, specify an account number that doesn't have dimensions.</span></span> <span data-ttu-id="3e893-116">As dimensões serão inseridas posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3e893-116">You will enter dimensions later in this topic.</span></span>

    <span data-ttu-id="3e893-117">Você também pode inserir um ou mais caracteres para a conta principal e usar a pesquisa para localizar a conta.</span><span class="sxs-lookup"><span data-stu-id="3e893-117">You can also enter one or more characters for the main account, and use the lookup to find the account.</span></span>

6. <span data-ttu-id="3e893-118">Selecione a Guia Rápida **Detalhes da linha** para adicionar dimensões à conta principal.</span><span class="sxs-lookup"><span data-stu-id="3e893-118">Select the **Line details** FastTab to add dimensions to the main account.</span></span>
7. <span data-ttu-id="3e893-119">Selecione a guia **Linha de dimensões financeiras**.</span><span class="sxs-lookup"><span data-stu-id="3e893-119">Select the **Financial dimensions line** tab.</span></span>

    * <span data-ttu-id="3e893-120">As dimensões são somente para a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3e893-120">The dimensions are for the selected line only.</span></span>
    * <span data-ttu-id="3e893-121">O grupo de impostos é preenchido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="3e893-121">The sales tax group is filled in from the customer.</span></span> <span data-ttu-id="3e893-122">Se o cliente não tiver um grupo de impostos, o grupo de impostos da conta principal será usado.</span><span class="sxs-lookup"><span data-stu-id="3e893-122">If the customer doesn't have a sales tax group, the sales tax group from the main account is used.</span></span>
    * <span data-ttu-id="3e893-123">O grupo de impostos dos itens é preenchido pela conta principal.</span><span class="sxs-lookup"><span data-stu-id="3e893-123">The items sales tax group is filled in from the main account.</span></span> <span data-ttu-id="3e893-124">Se a conta principal não tiver um grupo de impostos dos itens, o grupo de impostos dos itens especificado nos parâmetros de impostos na Contabilidade será usado.</span><span class="sxs-lookup"><span data-stu-id="3e893-124">If the main account doesn't have an item sales tax group, the item sales tax group that is specified in the sales tax parameters in General ledger is used.</span></span>

8. <span data-ttu-id="3e893-125">Opcional: no campo **Quantidade**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="3e893-125">Optional: In the **Quantity** field, enter a number.</span></span>
9. <span data-ttu-id="3e893-126">Opcional: no campo **Preço unitário**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="3e893-126">Optional: In the **Unit price** field, enter a number.</span></span>

    <span data-ttu-id="3e893-127">O valor é calculado como a quantidade vezes o preço unitário.</span><span class="sxs-lookup"><span data-stu-id="3e893-127">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="3e893-128">No entanto, você pode substituir o cálculo inserindo um valor.</span><span class="sxs-lookup"><span data-stu-id="3e893-128">However, you can override that calculation by entering an amount.</span></span>

10. <span data-ttu-id="3e893-129">Selecione **Imposto** para ver os impostos calculados para a fatura.</span><span class="sxs-lookup"><span data-stu-id="3e893-129">Select **Sales tax** to view the sales tax that is calculated for the invoice.</span></span>

    <span data-ttu-id="3e893-130">É possível exibir os valores dos impostos nesta página ou substitua os valores na guia **Ajuste**.</span><span class="sxs-lookup"><span data-stu-id="3e893-130">You can view the sales tax amounts on this page, or you can override the amounts on the **Adjustment** tab.</span></span>

11. <span data-ttu-id="3e893-131">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e893-131">Select **OK**.</span></span>
12. <span data-ttu-id="3e893-132">Selecione **Encargos** para adicionar um encargo à fatura.</span><span class="sxs-lookup"><span data-stu-id="3e893-132">Select **Charges** to add a charge to the invoice.</span></span>
13. <span data-ttu-id="3e893-133">No campo **Código de encargo**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="3e893-133">In the **Charges code** field, enter a value.</span></span>
14. <span data-ttu-id="3e893-134">No campo **Valor de encargo**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="3e893-134">In the **Charges value** field, enter a number.</span></span>
15. <span data-ttu-id="3e893-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3e893-135">Close the page.</span></span>
16. <span data-ttu-id="3e893-136">Selecione **Totais** para ver um resumo dos detalhes da fatura e os totais.</span><span class="sxs-lookup"><span data-stu-id="3e893-136">Select **Totals** to view a summary of the invoice details and totals.</span></span>
17. <span data-ttu-id="3e893-137">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="3e893-137">Select **Close**.</span></span>
18. <span data-ttu-id="3e893-138">Selecione **Lançar** para lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="3e893-138">Select **Post** to post the invoice.</span></span> <span data-ttu-id="3e893-139">Você ainda terá a oportunidade de cancelar antes de lançar.</span><span class="sxs-lookup"><span data-stu-id="3e893-139">You will still have an opportunity to cancel before you actually post.</span></span>

    * <span data-ttu-id="3e893-140">Você pode alterar a hora da impressão da fatura.</span><span class="sxs-lookup"><span data-stu-id="3e893-140">You can change the timing of invoice printing.</span></span> <span data-ttu-id="3e893-141">Selecione **Atual** para imprimir cada fatura, conforme for atualizada.</span><span class="sxs-lookup"><span data-stu-id="3e893-141">Select **Current** to print each invoice as it's updated.</span></span> <span data-ttu-id="3e893-142">Selecione **Depois** para imprimir depois todas as faturas que foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="3e893-142">Select **After** to print after all invoices have been updated.</span></span>
    * <span data-ttu-id="3e893-143">Para alterar como o limite de crédito do cliente é verificado antes de a fatura ser lançada, altere o valor no campo **Tipo de limite de crédito**.</span><span class="sxs-lookup"><span data-stu-id="3e893-143">To change how the customer's credit limit is verified before the invoice is posted, change the value in the **Credit limit type** field.</span></span>
    * <span data-ttu-id="3e893-144">Para imprimir a fatura, defina a opção como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3e893-144">To print the invoice, set the option to **Yes**.</span></span>
    * <span data-ttu-id="3e893-145">Para lançar a fatura, defina a opção como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3e893-145">To post the invoice, set the option to **Yes**.</span></span> <span data-ttu-id="3e893-146">Você pode imprimir a fatura sem lançá-la.</span><span class="sxs-lookup"><span data-stu-id="3e893-146">You can print the invoice without posting it.</span></span>

19. <span data-ttu-id="3e893-147">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e893-147">Select **OK**.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="3e893-148">Copiar linhas</span><span class="sxs-lookup"><span data-stu-id="3e893-148">Copy lines</span></span>
<span data-ttu-id="3e893-149">Para copiar linhas em uma fatura de texto livre, selecione uma ou mais linhas e depois selecione **Copiar linhas selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="3e893-149">To copy lines on a free text invoice, select one or more lines, and then select **Copy selected lines**.</span></span> <span data-ttu-id="3e893-150">Você pode especificar o número de cópias a serem feitas e também pode copiar observações e anexos.</span><span class="sxs-lookup"><span data-stu-id="3e893-150">You can specify the number of copies to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="3e893-151">Você pode copiar as distribuições ou permitir que sejam recriadas quando fizer o lançamento.</span><span class="sxs-lookup"><span data-stu-id="3e893-151">You can either copy the distributions or let them be re-created when you post.</span></span>

<span data-ttu-id="3e893-152">Depois de copiar as linhas, você poderá editar as informações conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e893-152">After you copy lines, you can edit the information as you require.</span></span>

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="3e893-153">Criar uma fatura de texto livre a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="3e893-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="3e893-154">Você pode criar uma fatura de texto livre a partir de um modelo.</span><span class="sxs-lookup"><span data-stu-id="3e893-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="3e893-155">Quando selecionar **Novo a partir do modelo** na guia **Fatura**, selecione um nome de modelo e a conta do cliente para nova fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="3e893-155">When you select **New from template** on the **Invoice** tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="3e893-156">Os valores padrão, como as condições de pagamento e método de pagamento, podem ser preenchidos automaticamente ou você pode usar os valores que foram salvos no modelo.</span><span class="sxs-lookup"><span data-stu-id="3e893-156">Default values, such as the terms of payment and method of payment, can be automatically filled in from the customer, or you can use the values that were saved in the template.</span></span>

<span data-ttu-id="3e893-157">Uma nova fatura de texto livre é criada e você pode editar os valores conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e893-157">A new free text invoice is created, and you can edit the values as you require.</span></span>
