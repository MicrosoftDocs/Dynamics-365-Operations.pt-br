---
title: O desempenho do cálculo de impostos afeta as transações
description: Este tópico fornece informações sobre como solucionar problemas relacionados ao desempenho do cálculo de impostos e seu efeito nas transações.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6fce4e2cb8c5507769533a875e23ccc4531abf51
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020130"
---
# <a name="tax-calculation-performance-affects-transactions"></a><span data-ttu-id="59620-103">O desempenho do cálculo de impostos afeta as transações</span><span class="sxs-lookup"><span data-stu-id="59620-103">Tax calculation performance affects transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59620-104">Às vezes, uma transação é afetada por problemas de desempenho que o cálculo de impostos está tendo.</span><span class="sxs-lookup"><span data-stu-id="59620-104">Sometimes, a transaction is affected by performance issues that tax calculation is having.</span></span> <span data-ttu-id="59620-105">Para solucionar esse problema, siga as etapas nas seguintes seções, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="59620-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="review-the-transaction-line-count"></a><span data-ttu-id="59620-106">Revisar a contagem de linhas da transação</span><span class="sxs-lookup"><span data-stu-id="59620-106">Review the transaction line count</span></span>

<span data-ttu-id="59620-107">Determine se a transação tem um grande número de linhas (por exemplo, mais de várias centenas).</span><span class="sxs-lookup"><span data-stu-id="59620-107">Determine whether the transaction has a large number of lines (for example, more than several hundred).</span></span> <span data-ttu-id="59620-108">Se não tiver, vá para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="59620-108">If it doesn't, move on to the next section.</span></span> <span data-ttu-id="59620-109">Se a transação tiver várias centenas de linhas, adie o cálculo de impostos.</span><span class="sxs-lookup"><span data-stu-id="59620-109">If the transaction does have several hundred lines, delay the tax calculation.</span></span> <span data-ttu-id="59620-110">Para obter mais informações, consulte [Habilitar o cálculo de impostos atrasados nos diários](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="59620-110">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span> 

<span data-ttu-id="59620-111">Em seguida, você pode determinar se alguma das seguintes condições é atendida:</span><span class="sxs-lookup"><span data-stu-id="59620-111">Next, you can determine whether any of the following conditions are met:</span></span>

- <span data-ttu-id="59620-112">Há transações de importação de arquivos grandes.</span><span class="sxs-lookup"><span data-stu-id="59620-112">There are import transactions from large files.</span></span>
- <span data-ttu-id="59620-113">Várias sessões processam o mesmo cálculo de impostos de transação ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="59620-113">Multiple sessions process the same transaction tax calculation at the same time.</span></span>
- <span data-ttu-id="59620-114">A transação tem várias linhas, e as exibições são atualizadas em tempo real.</span><span class="sxs-lookup"><span data-stu-id="59620-114">The transaction has multiple lines, and the views are updated in real time.</span></span> <span data-ttu-id="59620-115">Por exemplo, o campo **Valor do imposto calculado** na página **Diário geral** é atualizado em tempo real quando os campos de uma linha são alterados.</span><span class="sxs-lookup"><span data-stu-id="59620-115">For example, the **Calculated sales tax amount** field on the **General journal** page is updated in real time when a line's fields are changed.</span></span>

   <span data-ttu-id="59620-116">[![Campo Valor do imposto calculado na página Comprovante de diário](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="59620-116">[![Calculated sales tax amount field on the Jounal voucher page](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span></span>

<span data-ttu-id="59620-117">Se qualquer uma dessas condições for atendida, adie o cálculo de impostos.</span><span class="sxs-lookup"><span data-stu-id="59620-117">If any of these conditions are met, delay the tax calculation.</span></span>

## <a name="review-the-call-stack"></a><span data-ttu-id="59620-118">Revisar a pilha de chamadas</span><span class="sxs-lookup"><span data-stu-id="59620-118">Review the call stack</span></span>

<span data-ttu-id="59620-119">Revise a pilha de chamadas para determinar se o cálculo de impostos é chamado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="59620-119">Review the call stack to determine whether tax calculation is called multiple times.</span></span> <span data-ttu-id="59620-120">Se não for, vá para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="59620-120">If it isn't, move on to the next section.</span></span> <span data-ttu-id="59620-121">Se a pilha de chamadas for chamada várias vezes, siga estas etapas para ajudar a reduzir os tempos de cálculo de impostos.</span><span class="sxs-lookup"><span data-stu-id="59620-121">If the call stack is called multiple times, follow these steps to help reduce the tax calculation times.</span></span>

1. <span data-ttu-id="59620-122">Se o diário tiver considerado a transação, adie o cálculo de impostos.</span><span class="sxs-lookup"><span data-stu-id="59620-122">If the journal has considered the transaction, delay the tax calculation.</span></span> <span data-ttu-id="59620-123">Para obter mais informações, consulte [Habilitar o cálculo de impostos atrasados nos diários](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="59620-123">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span>
2. <span data-ttu-id="59620-124">Se a transação for uma ordem de compra e a versão do aplicativo for posterior a 10.0.15, você poderá adiar o cálculo de impostos até o cálculo final habilitando a liberação de versões para **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span><span class="sxs-lookup"><span data-stu-id="59620-124">If the transaction is a purchase order, and the application version is later than 10.0.15, you can delay the tax calculation until the final calculation by enabling the flighting for **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span></span>

## <a name="review-the-call-stack-timeline"></a><span data-ttu-id="59620-125">Revisar a linha do tempo da pilha de chamadas</span><span class="sxs-lookup"><span data-stu-id="59620-125">Review the call stack timeline</span></span>

<span data-ttu-id="59620-126">Revise a linha do tempo da pilha de chamadas para determinar se os seguintes problemas existem.</span><span class="sxs-lookup"><span data-stu-id="59620-126">Review the call stack timeline to determine whether the following issues exist.</span></span> <span data-ttu-id="59620-127">Se existirem, habilite a liberação de versões para **TaxUncommittedDoIsolateScopeFlighting** a fim de corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="59620-127">If they do, enable the flighting for **TaxUncommittedDoIsolateScopeFlighting** to fix the issue.</span></span>

- <span data-ttu-id="59620-128">A transação faz com que o sistema pare de responder até que a sessão seja finalizada.</span><span class="sxs-lookup"><span data-stu-id="59620-128">The transaction causes the system to stop responding until the session ends.</span></span> <span data-ttu-id="59620-129">Portanto, a transação não pode calcular o resultado do imposto.</span><span class="sxs-lookup"><span data-stu-id="59620-129">Therefore, the transaction can't calculate the tax result.</span></span> <span data-ttu-id="59620-130">A ilustração a seguir mostra a caixa de mensagem "Sessão finalizada" que você recebe.</span><span class="sxs-lookup"><span data-stu-id="59620-130">The following illustration shows the "Session ended" message box that you receive.</span></span>

    <span data-ttu-id="59620-131">[![Mensagem Sessão finalizada](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="59620-131">[![Session ended message](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span></span>

- <span data-ttu-id="59620-132">Os métodos **TaxUncommitted** levam mais tempo do que outros métodos.</span><span class="sxs-lookup"><span data-stu-id="59620-132">The **TaxUncommitted** methods take more time than other methods.</span></span> <span data-ttu-id="59620-133">Por exemplo, na ilustração a seguir, o método **TaxUncommitted::updateTaxUncommitted()** leva 43.347,42 segundos, mas outros métodos levam 0,09 segundo.</span><span class="sxs-lookup"><span data-stu-id="59620-133">For example, in the following illustration, the **TaxUncommitted::updateTaxUncommitted()** method takes 43,347.42 seconds, but other methods take 0.09 seconds.</span></span>

    <span data-ttu-id="59620-134">[![Durações dos métodos](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="59620-134">[![Method durations](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span></span>

## <a name="customizing-and-calling-tax-calculation"></a><span data-ttu-id="59620-135">Personalizar e chamar o cálculo de impostos</span><span class="sxs-lookup"><span data-stu-id="59620-135">Customizing and calling tax calculation</span></span>

<span data-ttu-id="59620-136">Ao personalizar, não chame o cálculo de impostos no método **insert()** ou **update()** para cada linha.</span><span class="sxs-lookup"><span data-stu-id="59620-136">When you customize, don't call tax calculation at the **insert()** or **update()** method for each line.</span></span> <span data-ttu-id="59620-137">O cálculo de impostos deve ser chamado no nível da transação.</span><span class="sxs-lookup"><span data-stu-id="59620-137">Tax calculation should be called at the transaction level.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="59620-138">Determinar se há personalização</span><span class="sxs-lookup"><span data-stu-id="59620-138">Determine whether customization exists</span></span>

<span data-ttu-id="59620-139">Se você concluiu as etapas nas seções anteriores, mas não encontrou nenhum problema, determine se há personalização.</span><span class="sxs-lookup"><span data-stu-id="59620-139">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="59620-140">Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.</span><span class="sxs-lookup"><span data-stu-id="59620-140">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
