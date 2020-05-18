---
title: Processar ajustes dos pontos de premiação de fidelidade
description: Este procedimento demonstra como procurar informações de cartão-fidelidade e ajustar pontos de recompensa de fidelidade.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdbd9fa60fe4d000359e4695a9fb034fae3ca1b0
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140711"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="d1818-103">Processar ajustes dos pontos de premiação de fidelidade</span><span class="sxs-lookup"><span data-stu-id="d1818-103">Process loyalty reward point adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d1818-104">Este procedimento demonstra como procurar informações de cartão-fidelidade e ajustar pontos de recompensa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="d1818-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="d1818-105">A empresa de dados de demonstração usada para criar esta tarefa é USRT.</span><span class="sxs-lookup"><span data-stu-id="d1818-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="d1818-106">Esta tarefa se destina à função Gerente de operações de comércio ou a uma função Gerente de atendimento ao consumidor.</span><span class="sxs-lookup"><span data-stu-id="d1818-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="d1818-107">Vá para Cartões-fidelidade.</span><span class="sxs-lookup"><span data-stu-id="d1818-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="d1818-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d1818-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d1818-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d1818-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d1818-110">Clique em Transações de cartão.</span><span class="sxs-lookup"><span data-stu-id="d1818-110">Click Card transactions.</span></span>
    * <span data-ttu-id="d1818-111">Nessa página você pode exibir todas as transações de fidelidade para o cartão-fidelidade selecionado.</span><span class="sxs-lookup"><span data-stu-id="d1818-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="d1818-112">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d1818-112">Close the page.</span></span>
6. <span data-ttu-id="d1818-113">Clique em Ajustes de cartão.</span><span class="sxs-lookup"><span data-stu-id="d1818-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="d1818-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d1818-114">Click New.</span></span>
8. <span data-ttu-id="d1818-115">No campo Recompensa, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d1818-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="d1818-116">No campo Valor ou quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d1818-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="d1818-117">Você pode adicionar ou remover pontos do cartão-fidelidade usando valores positivo ou negativo.</span><span class="sxs-lookup"><span data-stu-id="d1818-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="d1818-118">No campo programa de Fidelidade, informe ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d1818-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="d1818-119">No campo Comentário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d1818-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="d1818-120">Clique em Lançar ajuste.</span><span class="sxs-lookup"><span data-stu-id="d1818-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="d1818-121">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="d1818-121">Click Yes.</span></span>
14. <span data-ttu-id="d1818-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d1818-122">Close the page.</span></span>
    * <span data-ttu-id="d1818-123">Normalmente, neste ponto você atualizaria a página para ver o resultado do ajuste dos pontos de premiação na guia Resumo do ponto de premiação. Mas se você estiver executando isso como uma guia de tarefas não atualiza agora, pois se você fizer isso, a guia de tarefas será interrompida.</span><span class="sxs-lookup"><span data-stu-id="d1818-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="d1818-124">Clique em Transações de cartão.</span><span class="sxs-lookup"><span data-stu-id="d1818-124">Click Card transactions.</span></span>
16. <span data-ttu-id="d1818-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d1818-125">Close the page.</span></span>
