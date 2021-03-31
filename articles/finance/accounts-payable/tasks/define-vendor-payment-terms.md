---
title: Definir condições de pagamento de fornecedor
description: Este tópico explica como configurar condições de pagamento para faturas de fornecedor.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6a37272694609be14b566dae3c6cf561d4c6d2f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227223"
---
# <a name="define-vendor-payment-terms"></a><span data-ttu-id="a459e-103">Definir condições de pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="a459e-103">Define vendor payment terms</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a459e-104">Este tópico explica como configurar condições de pagamento para faturas de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a459e-104">This topic explains how to set up payment terms for vendor invoices.</span></span> <span data-ttu-id="a459e-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="a459e-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a459e-106">Vá para **Painel de navegação > Módulos > Contas a pagar > Configuração de pagamento > Condições de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a459e-106">Go to **Navigation pane > Modules > Accounts payable > Payment setup > Terms of payment**.</span></span>
2. <span data-ttu-id="a459e-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a459e-107">Select **New**.</span></span> <span data-ttu-id="a459e-108">A página de condições de pagamento é usada para definir como a data de vencimento será calculada.</span><span class="sxs-lookup"><span data-stu-id="a459e-108">The Terms of payment page is used to define how the due date will be calculated.</span></span> <span data-ttu-id="a459e-109">Não é usada para definir como a data de desconto à vista será calculada.</span><span class="sxs-lookup"><span data-stu-id="a459e-109">It is not used to define how the cash discount date will be calculated.</span></span>  
3. <span data-ttu-id="a459e-110">No campo **Condições de pagamento**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a459e-110">In the **Terms of payment** field, type a value.</span></span>
4. <span data-ttu-id="a459e-111">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a459e-111">In the **Description field**, type a value.</span></span>
5. <span data-ttu-id="a459e-112">No campo **Dias**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a459e-112">In the **Days** field, enter a number.</span></span> <span data-ttu-id="a459e-113">O número inserido aqui será usado para adicionar à data de vencimento, ou ao final do período identificado no método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a459e-113">The number entered here will be used to add to the due date, or to the end of the period identified in the Payment method.</span></span> <span data-ttu-id="a459e-114">Por exemplo, se você selecionar **Rede**, o número será adicionado à data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="a459e-114">For example, if you select **Net**, the number will be added to the due date.</span></span> <span data-ttu-id="a459e-115">Se você selecionar **Mês atual**, ele adicionará o número ao último dia do mês atual para calcular a data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="a459e-115">If you select **Current month**, it will add the number to the last day of the current month to calculate the due date.</span></span>  
6. <span data-ttu-id="a459e-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a459e-116">Select **Save**.</span></span>
7. <span data-ttu-id="a459e-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a459e-117">Close the page.</span></span>
8. <span data-ttu-id="a459e-118">Vá para **Contas a pagar > Configuração de pagamento > Descontos à vista**.</span><span class="sxs-lookup"><span data-stu-id="a459e-118">Go to **Accounts payable > Payment setup > Cash discounts**.</span></span>
9. <span data-ttu-id="a459e-119">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a459e-119">Select **New**.</span></span>
10. <span data-ttu-id="a459e-120">No campo **Desconto à vista**, insira uma ID.</span><span class="sxs-lookup"><span data-stu-id="a459e-120">In the **Cash discount** field, enter an ID.</span></span>
11. <span data-ttu-id="a459e-121">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a459e-121">In the **Description** field, type a value.</span></span>
12. <span data-ttu-id="a459e-122">Se o fornecedor oferece um desconto estratificado, selecione o próximo desconto à vista após o atual ter vencido.</span><span class="sxs-lookup"><span data-stu-id="a459e-122">If the vendor offers a tiered discount, select the next cash discount after the current one is expired.</span></span>
13. <span data-ttu-id="a459e-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a459e-123">Close the page.</span></span>
14. <span data-ttu-id="a459e-124">No campo **Dias**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a459e-124">In the **Days** field, enter a number.</span></span> <span data-ttu-id="a459e-125">A quantidade inserida no campo **Dias** será usada para calcular a Data do desconto à vista, com base na opção selecionada no campo **Líquido/atual**.</span><span class="sxs-lookup"><span data-stu-id="a459e-125">The quantity entered in the **Days** field will be used to calculate the Cash discount date, based on what option was selected in the **Net/Current** field.</span></span> <span data-ttu-id="a459e-126">Se **Líquido** foi selecionado, a quantidade será adicionada à data da fatura para determinar a data do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="a459e-126">If **Net** was selected, the quantity will be added to the invoice date to determine the cash discount date.</span></span> <span data-ttu-id="a459e-127">Se **Mês atual** foi selecionado, a quantidade será adicionada à data final do mês atual para determinar a data do desconto à vista.</span><span class="sxs-lookup"><span data-stu-id="a459e-127">If **Current month** was selected, the quantity will be added to the end of the currency month to determine the cash discount date.</span></span>  
15. <span data-ttu-id="a459e-128">Insira a porcentagem do desconto à vista no campo **Desconto**.</span><span class="sxs-lookup"><span data-stu-id="a459e-128">Enter the percentage of the cash discount in the **Discount** field.</span></span> 
16. <span data-ttu-id="a459e-129">Insira a conta principal na qual o desconto à vista será lançado para faturas de clientes. Depois, insira a conta principal na qual o desconto à vista será lançado para faturas de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a459e-129">Enter the main account to which the cash discount will be posted for customer invoices, then enter the main account to which the cash discount will be posted for vendor invoices.</span></span> <span data-ttu-id="a459e-130">Se **Contas de contrapartida de desconto** estiver definida como **Usar conta principal para desconto do fornecedor**, a conta principal será usada.</span><span class="sxs-lookup"><span data-stu-id="a459e-130">If **Discount offset accounts** is set to **Use main account for vendor discount**, then the Main account will be used.</span></span> <span data-ttu-id="a459e-131">Se a opção estiver definida como **Contas nas linhas de fatura**, o desconto à vista será lançado nas contas de ativo/despesas nas linhas da fatura.</span><span class="sxs-lookup"><span data-stu-id="a459e-131">If the option is set to **Accounts on the invoice lines**, the cash discount will be posted to the asset/expense accounts on the invoice's lines.</span></span>  
17. <span data-ttu-id="a459e-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a459e-132">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]