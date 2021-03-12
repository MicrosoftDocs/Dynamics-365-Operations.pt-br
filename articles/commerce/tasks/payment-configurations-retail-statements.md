---
title: Configurações de pagamento para obter demonstrativos de varejo
description: Este procedimento demonstra configurações para os métodos de pagamento da loja do Commerce que afetam como as instruções são criadas e lançadas.
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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b1fc042bff4d801ae893b0370b67cd8e11ba95f6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982304"
---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="c7cd0-103">Configurações de pagamento para obter demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="c7cd0-103">Payment configurations for Retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7cd0-104">Este procedimento demonstra configurações para os métodos de pagamento da loja do Commerce que afetam como as instruções são criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-104">This procedure demonstrates configurations for Commerce store payment methods, which affect how statements get created and posted.</span></span>

<span data-ttu-id="c7cd0-105">Este registro usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="c7cd0-106">Vá para Retail e Commerce > Canais > Lojas > Todas as lojas.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-106">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="c7cd0-107">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c7cd0-108">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c7cd0-109">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="c7cd0-110">Clique em Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-110">Click Payment methods.</span></span>
6. <span data-ttu-id="c7cd0-111">Expandir ou recolher a seção Lançamento.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="c7cd0-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-112">Click Edit.</span></span>
    * <span data-ttu-id="c7cd0-113">Selecione se os valores recebidos para o método de pagamento devem ser lançados em uma conta contábil ou em uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="c7cd0-114">Selecione a conta na qual os valores recebidos para o método de pagamento devem ser lançados.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="c7cd0-115">Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado para este método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="c7cd0-116">Neste campo é possível inserir um valor para controlar quando o valor da diferença deverá ser lançado em outra conta de diferença.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="c7cd0-117">Você pode usar isso para rastrear as diferenças grandes.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="c7cd0-118">Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado, quando ele excede o valor definido no campo "Valor de diferença máximo".</span><span class="sxs-lookup"><span data-stu-id="c7cd0-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="c7cd0-119">Selecione "Sim" para lançar valores de depósito bancário em uma conta separada.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="c7cd0-120">Neste campo você pode selecionar se os valores de depósito bancário devem ser lançados para uma conta contábil ou para uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="c7cd0-121">Selecione a conta para lançar valores de depósito bancário.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="c7cd0-122">Selecione o tipo de transação bancária a ser usado ao lançar valores de depósito bancário para a conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="c7cd0-123">Selecione "Sim" para lançar valores de depósito bancário protegidos em uma conta separada.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="c7cd0-124">Selecione se os valores de depósito bancário protegidos devem ser lançados em uma conta contábil ou na conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="c7cd0-125">Selecione a conta para lançar valores de depósito bancário protegidos.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="c7cd0-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c7cd0-126">Click Save.</span></span>

