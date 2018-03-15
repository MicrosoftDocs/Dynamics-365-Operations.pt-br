--- 
title: "Configurações de pagamento para obter demonstrativos de varejo"
description: "Este procedimento demonstra configurações para os métodos de pagamento da loja de varejo que afetam como as instruções de varejo foram criadas e lançadas."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 0ffd6dc5fff6d27ec3cfdcd68c53b2299c4100b9
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="f6299-103">Configurações de pagamento para obter demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="f6299-103">Payment configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f6299-104">Este procedimento demonstra configurações para os métodos de pagamento da loja de varejo que afetam como as instruções de varejo foram criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="f6299-104">This procedure demonstrates configurations for Retail store payment methods, which affect how Retail statements get created and posted.</span></span>

<span data-ttu-id="f6299-105">Este registro usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="f6299-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="f6299-106">Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="f6299-106">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="f6299-107">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f6299-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="f6299-108">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f6299-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f6299-109">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="f6299-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="f6299-110">Clique em Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f6299-110">Click Payment methods.</span></span>
6. <span data-ttu-id="f6299-111">Expandir ou recolher a seção Lançamento.</span><span class="sxs-lookup"><span data-stu-id="f6299-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="f6299-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f6299-112">Click Edit.</span></span>
    * <span data-ttu-id="f6299-113">Selecione se os valores recebidos para o método de pagamento devem ser lançados em uma conta contábil ou em uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="f6299-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="f6299-114">Selecione a conta na qual os valores recebidos para o método de pagamento devem ser lançados.</span><span class="sxs-lookup"><span data-stu-id="f6299-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="f6299-115">Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado para este método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f6299-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="f6299-116">Neste campo é possível inserir um valor para controlar quando o valor da diferença deverá ser lançado em outra conta de diferença.</span><span class="sxs-lookup"><span data-stu-id="f6299-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="f6299-117">Você pode usar isso para rastrear as diferenças grandes.</span><span class="sxs-lookup"><span data-stu-id="f6299-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="f6299-118">Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado, quando ele excede o valor definido no campo "Valor de diferença máximo".</span><span class="sxs-lookup"><span data-stu-id="f6299-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="f6299-119">Selecione "Sim" para lançar valores de depósito bancário em uma conta separada.</span><span class="sxs-lookup"><span data-stu-id="f6299-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="f6299-120">Neste campo você pode selecionar se os valores de depósito bancário devem ser lançados para uma conta contábil ou para uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="f6299-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="f6299-121">Selecione a conta para lançar valores de depósito bancário.</span><span class="sxs-lookup"><span data-stu-id="f6299-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="f6299-122">Selecione o tipo de transação bancária a ser usado ao lançar valores de depósito bancário para a conta bancária.</span><span class="sxs-lookup"><span data-stu-id="f6299-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="f6299-123">Selecione "Sim" para lançar valores de depósito bancário protegidos em uma conta separada.</span><span class="sxs-lookup"><span data-stu-id="f6299-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="f6299-124">Selecione se os valores de depósito bancário protegidos devem ser lançados em uma conta contábil ou na conta bancária.</span><span class="sxs-lookup"><span data-stu-id="f6299-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="f6299-125">Selecione a conta para lançar valores de depósito bancário protegidos.</span><span class="sxs-lookup"><span data-stu-id="f6299-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="f6299-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f6299-126">Click Save.</span></span>


