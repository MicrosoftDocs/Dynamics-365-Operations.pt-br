---
title: Configurações de pagamento para obter demonstrativos de varejo
description: Este procedimento demonstra configurações para os métodos de pagamento da loja de varejo que afetam como as instruções de varejo foram criadas e lançadas.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f49a3ae05d35b0f0ca6a08007f5b05321c1f5ab
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564261"
---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="ba575-103">Configurações de pagamento para obter demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="ba575-103">Payment configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ba575-104">Este procedimento demonstra configurações para os métodos de pagamento da loja de varejo que afetam como as instruções de varejo foram criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="ba575-104">This procedure demonstrates configurations for Retail store payment methods, which affect how Retail statements get created and posted.</span></span>

<span data-ttu-id="ba575-105">Este registro usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="ba575-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="ba575-106">Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="ba575-106">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="ba575-107">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ba575-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="ba575-108">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ba575-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="ba575-109">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="ba575-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="ba575-110">Clique em Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="ba575-110">Click Payment methods.</span></span>
6. <span data-ttu-id="ba575-111">Expandir ou recolher a seção Lançamento.</span><span class="sxs-lookup"><span data-stu-id="ba575-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="ba575-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="ba575-112">Click Edit.</span></span>
    * <span data-ttu-id="ba575-113">Selecione se os valores recebidos para o método de pagamento devem ser lançados em uma conta contábil ou em uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="ba575-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="ba575-114">Selecione a conta na qual os valores recebidos para o método de pagamento devem ser lançados.</span><span class="sxs-lookup"><span data-stu-id="ba575-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="ba575-115">Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado para este método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="ba575-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="ba575-116">Neste campo é possível inserir um valor para controlar quando o valor da diferença deverá ser lançado em outra conta de diferença.</span><span class="sxs-lookup"><span data-stu-id="ba575-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="ba575-117">Você pode usar isso para rastrear as diferenças grandes.</span><span class="sxs-lookup"><span data-stu-id="ba575-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="ba575-118">Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado, quando ele excede o valor definido no campo "Valor de diferença máximo".</span><span class="sxs-lookup"><span data-stu-id="ba575-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="ba575-119">Selecione "Sim" para lançar valores de depósito bancário em uma conta separada.</span><span class="sxs-lookup"><span data-stu-id="ba575-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="ba575-120">Neste campo você pode selecionar se os valores de depósito bancário devem ser lançados para uma conta contábil ou para uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="ba575-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="ba575-121">Selecione a conta para lançar valores de depósito bancário.</span><span class="sxs-lookup"><span data-stu-id="ba575-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="ba575-122">Selecione o tipo de transação bancária a ser usado ao lançar valores de depósito bancário para a conta bancária.</span><span class="sxs-lookup"><span data-stu-id="ba575-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="ba575-123">Selecione "Sim" para lançar valores de depósito bancário protegidos em uma conta separada.</span><span class="sxs-lookup"><span data-stu-id="ba575-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="ba575-124">Selecione se os valores de depósito bancário protegidos devem ser lançados em uma conta contábil ou na conta bancária.</span><span class="sxs-lookup"><span data-stu-id="ba575-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="ba575-125">Selecione a conta para lançar valores de depósito bancário protegidos.</span><span class="sxs-lookup"><span data-stu-id="ba575-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="ba575-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ba575-126">Click Save.</span></span>

